# GetGenesisProducts.php

Returns information about your existing products and lets you save the information to the `config` file.

For information about when to run `GetGenesisProducts.php`, see Step 5 in [Implementation](c_sample_integration_implement.md#).

```
<?
/**
* @file
* GenesisSoapApp.class.php
*
* Copyright © 2009-2011 Adobe, Inc. All rights reserved.
**/
require_once 'nusoap-0.7.3/lib/nusoap.php';
class GenesisSoapApp
{
  private $_username	 = '';
  private $_password	 = '';
  private $_working_dir	 = '';
  private $_int_wsdl	 = '';
  private $_con_wsdl	 = '';
  private $_product_code	 = '';
  private $_integration_code	= '';
  private $_wsdl_locations	= array('integration'=>'', 'config'=>'');
  private $_debug	 = 0;
  function __construct()
  {
    $config_params = parse_ini_file("config");
    $this->_username = $config_params['username'];
    $this->_password = $config_params['password'];
    $this->_working_dir = $config_params['workingDir'];
    $this->_int_wsdl = $config_params['integrationWSDL'];
    $this->_con_wsdl = $config_params['configWSDL'];
    $this->_product_code = $config_params['productCode'];
    $this->_integration_code = $config_params['integrationCode'];
    $this->_wsdl_locations['integration'] = $config_params['workingDir'] . "/" . $config_params['integrationWSDL'];
    $this->_wsdl_locations['config'] = $config_params['workingDir'] . "/" . $config_params['configWSDL'];
  }
  function sendRequest($functionName, $params, $wsdlType, $debug) {
    // Create nuSOAP client
    $client = new nusoap_client($this->_wsdl_locations[$wsdlType], 'wsdl');
    $client->debugLevel = 1; //Debug level 0-9, where 0 turns off

	// handle client setup error
    if($err = $client->getError()) {
      echo "ERROR:".$err."\n";
      exit();
    }
    $client->setUseCurl(true);

	// call a Web Services method
    $result = $client->call($functionName, // function name
      $params, // parameters
      'http://omniture.com', // namespace
      '', // SOAP Action
      $this->getHeader($this->_username, $this->_password)); // security header

	  if ($debug > 0 ) {
        switch ($debug) {
          case 1:
            // Display results
            echo "\nAPI called: " . $functionName . "\n";
            echo "RESULTS: \n";
            var_dump($result);
            echo "\n";
            break;
          case 2:
            var_dump($client->request);
            break;
          case 3:
            var_dump($client->responseData);
            break;
          default:
            var_dump($client->getDebug());
            break;
        }
    }
  return ($result);
}
function getHeader($username, $password)
{
  // Create a unique identifier, a.k.a. nonce.
  // This example is used for simplicity in demonstration. A method
  // that guarantees uniqueness should be used in a production environment.
  $nonce = md5(rand());
  $created = date("Y-m-d H:i:s");
  $combo_string = $nonce . $created . $password;

  // Note: the sha1 command is not available in all versions of PHP.
  // If your version of PHP does not support this command, you
  // can use openssl directly with the command:
  // echo -n <string> | openssl dgst -sha1
  $sha1_string = sha1($combo_string);
  $password_hash = base64_encode($sha1_string);

  $headers =
    '<wsse:Security SOAP-ENV:mustUnderstand="1">
      <wsse:UsernameToken wsu:Id="User">
        <wsse:Username>' . $username . '</wsse:Username>
        <wsse:Password Type= "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0#PasswordDigest">'.$password_hash.'</wsse:Password>
        <wsse:Nonce>' . $nonce . '</wsse:Nonce>
        <wsu:Created>' . $created . '</wsu:Created>
      </wsse:UsernameToken>
    </wsse:Security>';
  return $headers;
}
// Getters
  function getUsername()
  {
    return $this->_username;
  }
  function getPassword()
  {
    return $this->_password;
  }
  function getWorkingDir()
  {
    return $this->_working_dir;
  }
  function getConfigWSDL()
  {
    return $this->_con_wsdl;
  }
  function getIntegrationWSDL()
  {
    return $this->_int_wsdl;
  }
  function getProductCode()
  {
    return $this->_product_code;
  }
  function getIntegrationCode()
  {
    return $this->_integration_code;
  }
}
?>
```

**Parent topic:** [Integration Code](../../code_samples/integration/c_sample_integration_code.md)

