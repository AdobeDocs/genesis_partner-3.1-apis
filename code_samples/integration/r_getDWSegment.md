# GetDWSegment.php

Returns a Data Warehouse segment for the integration specified in the `config` file.

For information about when to run `GetDWSegment.php`, see Step 11 in [Implementation](c_sample_integration_implement.md#).

```
<?
/**
* @file
* GetDWSegment.php
*
* Copyright © 2009-2011 Adobe, Inc. All rights reserved.
**/

require_once "GenesisSoapApp.class.php";

define ('MAX_ITERATIONS',	 5);
define ('ITERATION_PAUSE',	 300);	 // in seconds

$soapApp = new GenesisSoapApp();

$debug = 0;
// Use debug level from command line
if($argc >= 2) {
  $arguments = getopt("d:");
  if (!empty($arguments['d'])) {
    $debug = $arguments['d'];
  }
}
if ($argc >= 4) {
  echo "Usage: GetDWSegment.php [-d debug level]\n\n";
  exit();
}

$integrationCode = $soapApp->getIntegrationCode();
if (empty($integrationCode)) {
  die("\nError: The integration code was not found in the configuration file!\n\n");
}

$wsdlType = 'integration';

$functionName = 'Export.RequestSegmentedData';
// change these parameters to suit your needs
$params = array('dateFrom' => '02/01/09',
  'dateGranularity' => 'none',
  'datePreset' => 'This month',
  'dateTo' => '07/08/09',
  'dateType' => 'range',
  'integrationCode' => $integrationCode,	 // Found in result of GetIntegrations call
  'segmentName' => 'Got a Tweet',	 // Found in CreateSegment call or by using GetIntegrations
  'breakdownNames' => array(
  'item' => 'Twitter'));	 // Name of metric for the evar used

$result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
if (is_array($result)) {
  if (array_key_exists('faultstring', $result)) {
    echo "Error-RequestSegmentedData: " . $result['faultstring'] . "\n";
  } else {
      $requestId = $result['requestId'];
    }
}

$functionName = 'Export.GetSegmentedData';
$params = array('requestId' => $requestId, 'integrationCode' => $integrationCode);

// Loop, pausing ITERATION_PAUSE seconds between each iteration until the segment request is found
$dataFound = false;
$count = 0;
while (!$dataFound) {
  sleep(ITERATION_PAUSE);
  $result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
  $count++;
  if (is_array($result)) {
    if (!array_key_exists('faultstring', $result) || strpos($result['faultstring'], 'Request data cannot be located') < 0) {
      $dataFound = true;
    }
  }

  if ( $count > MAX_ITERATIONS ) {
    continue;
  }
}
if (is_array($result)) {
  if (array_key_exists('faultstring', $result)) {
    echo "Error-GetSegmentedData: " . $result['faultstring'] . "\n";
  } else {
      var_dump($result);
      echo "\n" . $count . " iteration(s) needed to get segment.\n";
    }
}
?>
```

**Parent topic:** [Integration Code](../../code_samples/integration/c_sample_integration_code.md)

