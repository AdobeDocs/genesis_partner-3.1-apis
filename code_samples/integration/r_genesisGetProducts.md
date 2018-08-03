# GetGenesisProducts.php

Returns information about your existing products and lets you save the information to the `config` file.

For information about when to run `GetGenesisProducts.php`, see Step 5 in [Implementation](c_sample_integration_implement.md#).

```
<?
/**
* @file
* GetGenesisProducts.php
*
* Copyright © 2009 Adobe, Inc. All rights reserved.
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
  echo "Usage: GetGenesisProducts.php [-d debug level]\n\n";
  exit();
}

$wsdlType = 'integration';	 // Use Data Connectors Integration WSDL
$functionName = 'Partner.GetProducts';
$params = array();

$result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
if (is_array($result)) {
  if (array_key_exists('faultstring', $result)) {
    echo "Error-GetProducts: " . $result['faultstring'] . "\n";
  } else {
      fwrite(STDOUT, "\nWould you like to send the results to the configuration file? (y\\n) ");
      // Read input
      $response = fgets(STDIN);
      if (strpos($response, 'y') === 0 || strpos($response, 'Y') === 0) {
        fwrite(STDOUT, "\nAvailable products:\n");
        $index = 1;
        foreach($result as $product) {
          echo $index . '- ' . $product['name'] . "\n";
          $index++;
        }
        fwrite(STDOUT, "Please select a product number to use- ");
        $productIndex = fgets(STDIN);
        unlink('config');
        $outfile = fopen('config', 'w');
        $product = $result[$productIndex - 1];

	    // Write details to config file
        fwrite($outfile, 'username=' . $soapApp->getUsername() . "\n");
        fwrite($outfile, 'password=' . $soapApp->getPassword() . "\n");
        fwrite($outfile, 'workingDir=' . $soapApp->getWorkingDir() . "\n");
        fwrite($outfile, 'configWSDL=' . $soapApp->getConfigWSDL() . "\n");
        fwrite($outfile, 'integrationWSDL=' . $soapApp->getIntegrationWSDL() . "\n");
        fwrite($outfile, 'productCode=' . $product['productCode'] . "\n");
        fclose($outfile);

    	// Display product information
        var_dump($product);
      } else {
          var_dump($result);
        }
    }
}
?>
```

**Parent topic:** [Integration Code](../../code_samples/integration/c_sample_integration_code.md)

