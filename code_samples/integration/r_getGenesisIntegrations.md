# GetGenesisIntegrations.php

Returns information about your defined integrations and lets you save the information to the `config` file.

For information about when to run `GetGenesisIntegrations.php`, see Step 9 in [Implementation](c_sample_integration_implement.md#).

```
<?
/**
* @file
* GetGenesisIntegrations.php
*
* Copyright © 2009-2011 Adobe, Inc. All rights reserved.
**/

require_once "GenesisSoapApp.class.php";

$soapApp = new GenesisSoapApp();

$debug = 0;
// Override username and password if provided on command line
if($argc >= 2) {
  $arguments = getopt("d:");
  if (!empty($arguments['d'])) {
    $debug = $arguments['d'];
  }
}

if ($argc >= 4) {
  echo "Usage: GetGenesisIntegrations.php [-d debug level]\n\n";
  exit();
}

$wsdlType = 'integration';
$functionName = 'Partner.GetIntegrations';
$params = array();

$result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
if (is_array($result)) {
  if (array_key_exists('faultstring', $result)) {
    echo "Error-GetIntegrations: " . $result['faultstring'] . "\n";
  } else {
      fwrite(STDOUT, "\nWould you like to send the results to the configuration file? (y\\n) ");
      // Read input
      $response = fgets(STDIN);
      if (strpos($response, 'y') === 0 || strpos($response, 'Y') === 0) {
        fwrite(STDOUT, "\nAvailable integrations:\n");
        $index = 1;
        foreach($result as $integration) {
          echo $index . '- ' . $integration['integrationName'] . "\n";
          $index++;
        }
        fwrite(STDOUT, "Please select an integration number to use- ");
        $integrationIndex = fgets(STDIN);
        unlink('config');
        $outfile = fopen('config', 'w');
        $integration = $result[$integrationIndex - 1];

		// Write details to config file
        fwrite($outfile, 'username=' . $soapApp->getUsername() . "\n");
        fwrite($outfile, 'password=' . $soapApp->getPassword() . "\n");
        fwrite($outfile, 'workingDir=' . $soapApp->getWorkingDir() . "\n");
        fwrite($outfile, 'configWSDL=' . $soapApp->getConfigWSDL() . "\n");
        fwrite($outfile, 'integrationWSDL=' . $soapApp->getIntegrationWSDL() . "\n");
        fwrite($outfile, 'integrationCode=' . $integration['integrationCode'] . "\n");
        fwrite($outfile, 'integrationName=' . $integration['integrationName'] . "\n");
        fwrite($outfile, 'integrationEmail=' . $integration['integrationEmail'] . "\n");
        fwrite($outfile, 'productCode=' . $integration['productCode'] . "\n");
        fwrite($outfile, 'productName=' . $integration['productName'] . "\n");
        fwrite($outfile, 'reportSuiteId=' . $integration['reportSuiteId'] . "\n");
        fwrite($outfile, 'company=' . $integration['company'] . "\n");
        fwrite($outfile, 'creationDate=' . $integration['creationDate'] . "\n");
        fwrite($outfile, 'dataSourceId=' . $integration['dataSourceIds'][0] . "\n");
        fwrite($outfile, 'soapEndpoint=' . $integration['soapEndpoint'] . "\n");
        fclose($outfile);

		// Display integration information
        var_dump($integration);
      } else {
          var_dump($result);
        }
    }
}
?>
```

**Parent topic:** [Integration Code](../../code_samples/integration/c_sample_integration_code.md)

