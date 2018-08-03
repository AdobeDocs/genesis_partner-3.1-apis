# ConfigureTwitterApp.php

Configures the Twitter App Integration Wizard and the product script to run following the Integration Wizard.

For information about when to run `ConfigureTwitterApp.php`, see Step 7 in [Implementation](c_sample_integration_implement.md#).

```
<?
/**
* @file
* ConfigureTwitterApp.php
*
* Copyright © 2009-2011 Adobe, Inc. All rights reserved.
**/

require_once "GenesisSoapApp.class.php";

$soapApp = new GenesisSoapApp();

$debug = 0;
if($argc >= 2) {
  $arguments = getopt("d:");
  if (!empty($arguments['d'])) {
    $debug = $arguments['d'];
  }
}

if ($argc >= 4) {
  echo "Usage: ConfigureTwitterApp.php [-d debug level]\n\n";
  exit();
}

$productCode = $soapApp->getProductCode();	// Partner's product identifier
if (empty($productCode)) {
  die("\nError: The product code was not found in the configuration file!\n\n");
}

$wsdlType = 'config';	 // Use Data Connectors Config WSDL

$functionName = 'Product.AddVariableMappings';
$params = array('productCode' => $productCode,
  'variableMappings' => array(
    array('metric' => 'Twitter Search Term',
      'friendly_name' => 'Tracking code for Twitter',
      'om_variable' => 'evar',
      'type_flag' => array('custom', 'campaign'),
      'description' => 'This was created by OMTR engineering.',
      'required' => 'yes',
      'access' => 'import'),
    array('metric' => 'Twitter',
      'friendly_name' => 'Twitter evar',
      'om_variable' => 'evar',
      'type_flag' => array('custom'),
      'description' => 'This was created by OMTR engineering.',
      'required' => 'yes',
      'access' => 'import/export'),
    array('metric' => 'Tweets',
      'friendly_name' => 'Tweets event',
      'om_variable' => 'event',
      'type_flag' => array('custom', 'counter'),
      'description' => 'This was created by OMTR engineering.',
      'required' => 'yes',
      'access' => 'import'),
    array('metric' => 'Saved Search Term',
      'friendly_name' => 'Saved Search Term',
      'om_variable' => 'customval',
      'type_flag' => '',
      'description' => 'This was created by OMTR engineering.',
      'required' => 'yes',
      'access' => 'import')));

$result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
var_dump($result);
if (array_key_exists('faultstring', $result)) {
  echo "\nError-AddVariableMappings: " . $result['faultstring'] . "\n";
} else {
  echo "\nVariable mappings have been successfully added for product code " . $productCode . ".\n";
}

// The product script is used to run needed API calls after the Data Connectors wizard has run.
//
// If there are APIs that need to be run upon creation of the integration and other when the
// integration is edited, 2 scripts must be created, one for each.
//
// This product script will:
// 1-Create a calculated metric for the report suite
// 2-Create a classification for the Twitter evar
// 3-Create a datasource for use with the integration
// 4-Create a DataWarehouse segment
$functionName = 'Product.AddProductScript';
$params = array('productCode' => $productCode,
  'scriptName' => 'Twitter Create Script',
  'scriptDesc' => 'This script will only be run when creating a new integration.',
  'runOn' => 'integration_create',
  'script' => '
    <genesis version="3">
        <rsid_list>
          <item>{{RSID}}</item>
        </rsid_list>
      </ReportSuite.SaveCalculatedMetrics>
      <ReportSuite.SaveClassifications>
        <c_options/>
        <c_view>{{Twitter|classification}}</c_view>
        <name>Twitter User</name>
        <rsid_list>
          <item>{{RSID}}</item>
        </rsid_list>
      </ReportSuite.SaveClassifications>
      <DataSource.SetupGeneric>
        <dataSourceID></dataSourceID>
        <dataSourceSettingseve>
          <dataSourceName>{{INT_NAME}}</dataSourceName>
          <dataSourceEmail>{{EMAIL}}</dataSourceEmail>
        </dataSourceSettings>
        <dataSourceType>12</dataSourceType>
          <reportSuiteID>{{RSID}}</reportSuiteID>
      </DataSource.SetupGeneric>
      <DataWarehouse.CreateSegment>
        <rsid>{{RSID}}</rsid>
        <segment>
          <name>Got a Tweet</name>
          <group_include>
            <type>ROOT</type>
            <name>Include</name>
            <group_operator>UNKNOWN</group_operator>
            <rule_operator>AND</rule_operator>
            <rule_list/>
            <group_list>
              <item>
                <type>VISIT</type>
                <name>Visit</name>
                <group_operator>UNKNOWN</group_operator>
                <rule_operator>AND</rule_operator>
                <rule_list/>
                <group_list>
                  <item>
                    <type>EVENT</type>
                    <name>Tweets</name>
                    <group_operator>UNKNOWN</group_operator>
                    <rule_operator>AND</rule_operator>
                    <rule_list>
                      <item>
                        <operator>></operator>
                        <item>{{Twitter|api_code}}</item>
                        <value>!</value>
                        <event/>
                      </item>
                      <item>
                        <operator/>
                        <item/>
                        <value/>
                        <event>{{Tweets|mod_stat}}</event>
                      </item>
                    </rule_list>
                <group_list/>
              </item>
            </group_list>
          </item>
        </group_list>
      </group_include>
      <group_exclude>
        <type>ROOT</type>
        <name>Exclude</name>
        <group_operator>UNKNOWN</group_operator>
        <rule_operator>AND</rule_operator>
        <rule_list/>
        <group_list/>
      </group_exclude>
    </segment>
  </DataWarehouse.CreateSegment>
</genesis>');

$result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
if (array_key_exists('faultstring', $result)) {
  echo "\nError-AddProductScript: " . $result['faultstring'] . "\n";
} else {
  echo "\nProduct script for creating integrations has been successfully uploaded for product code " . $productCode . ".\n\n";
}

//
// This product script will:
// 1-Create a calculated metric for the report suite
// 2-Create a classification for the Twitter evar
$params = array('productCode' => $productCode,
  'scriptName' => 'Twitter Edit Script',
  'scriptDesc' => 'This script will only be run when editing an integration.',
  'runOn' => 'integration_edit',
  'script' => '
    <genesis>
      <ReportSuite.SaveCalculatedMetrics>
        <calculated_metrics>
          <item>
            <name>Tweets per hour</name>
            <formula>{{[Tweets]}} / 24</formula>
            <friendly_formula>[Tweets] / 24</friendly_formula>
            <metric_type>2</metric_type>
            <metric_type_string>Percent (%)</metric_type_string>
            <decimal_places>2</decimal_places>
            <in_queue>0</in_queue>
            <status>0</status>
          </item>
        </calculated_metrics>
        <rsid_list>
          <item>{{RSID}}</item>
        </rsid_list>
      </ReportSuite.SaveCalculatedMetrics>
      <ReportSuite.SaveClassifications>
        <c_options/>
        <c_view>{{Twitter|classification}}</c_view>
        <name>Twitter User</name>
        <rsid_list>
          <item>{{RSID}}</item>
        </rsid_list>
      </ReportSuite.SaveClassifications>
    </genesis>');

$result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
if (array_key_exists('faultstring', $result)) {
  echo "\nError-AddProductScript: " . $result['faultstring'] . "\n";
} else {
  echo "\nProduct script for editing integrations has been successfully uploaded for product code " . $productCode . ".\n\n";
}
?>
```

**Parent topic:** [Integration Code](../../code_samples/integration/c_sample_integration_code.md)

