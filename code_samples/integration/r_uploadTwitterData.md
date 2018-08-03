# UploadTwitterData.php

Manages the transfer of Twitter data to Analytics servers.

For information about when to run `UploadTwitterData.php`, see Step 10 in [Implementation](c_sample_integration_implement.md#).

```
#!/usr/bin/php5
<?
/**
* @file
* UploadTwitterData.php
*
* Copyright © 2009 Adobe, Inc. All rights reserved.
**/

require_once "GenesisSoapApp.class.php";

define('DOCUMENT_NODE', 0);
define('ELEMENT_NODE', 1);
define('ATTRIBUTE_NODE', 2);
define('TEXT_NODE', 3);

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
  echo "Usage: UploadTwitterData.php [-d debug level]\n\n";
  exit();
}

$workingDir = $soapApp->getWorkingDir();
if (!file_exists($workingDir)) {
  mkdir($workingDir);
}
if (!file_exists($workingDir . '/tweetIds')) {
  mkdir($workingDir . '/tweetIds');
}

$functionName = 'Partner.GetIntegrations';
$integrationCode = $soapApp->getIntegrationCode();
if (!empty($integrationCode)) {
  $params = array('filter'=>"integrationCode==\"$integrationCode\"");
} else {
    $params = array();
  }
$wsdlType = 'integration';
$mdyToday = date("m/d/Y/H/i/s");

// used for Twitter API call
$today = date("Y-m-d");

$result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
if (!empty($result)) {
  foreach ($result as $integrationArray) {
    $totalTwitterUsers = 0;
    $tweetData = array();
    $classifications = array(); // array of tweeter names
    $integrationCode = $integrationArray['integrationCode'];	 // Data Connectors integration identifier
    $dataSourceId = $integrationArray['dataSourceIds'][0];	 // Needed for UploadMetrics call

    // Get stored tweet id
    $tweetFile = $workingDir . '/tweetIds/' . $integrationCode;
    if (file_exists($tweetFile)) {
      $fp = fopen($tweetFile, 'r');
      $size = filesize($tweetFile);
      if ($size > 0) {
        $tweetId = fread($fp, filesize($tweetFile));
      }
      fclose($fp);
    } else {
        $tweetId = '';
      }
    foreach ($integrationArray['integrationValues'] as $customVal) {
      if ($customVal['name'] == 'Saved Search Term' && !empty($customVal['value'])) {

	    // Get search terms from comma separated string
        $searchTerms = explode(",", $customVal['value']);
        $aRows = array();
        $propTweetIds = array();
        $index =0;
        $firstTweetId = "";
        foreach ($searchTerms as $searchTerm) {
          $tweeters = array(); // array of tweeters and number of tweets
          $twitterSearchTerm = str_replace(" ", "+", $searchTerm);
          $curl = curl_init();
          $url = "http://search.twitter.com/search.atom?q=$twitterSearchTerm&cache=true&since=$today&since_id=$tweetId&rpp=100";
          
		  curl_setopt ($curl, CURLOPT_URL, $url);
          curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);

          $result = curl_exec ($curl);
          curl_close ($curl);

		  // Get tweeter and number of tweets from document
          $dom = new DomDocument();
          $dom->loadXML($result);
          foreach ($dom->documentElement->childNodes as $child) {
            if ($child->nodeType == ELEMENT_NODE && $child->nodeName === "entry") {
            foreach ($child->childNodes as $data) {
              switch($data->nodeName) {
                case "id":
                  if ($data->nodeName === "id") {
                    $elements = explode(":", $data->textContent);
                    if (empty($firstTweetId) || $elements[2] > $firstTweetId) {
                      $firstTweetId = $elements[2];
                    }
                  }
                  break;
                case "author":
                  $raw_auth = trim($data->textContent);
                  $firstParen = strpos($raw_auth, '(');
                  $lastParen = strpos($raw_auth, ')');
                  $nameLen = $lastParen - $firstParen - 1;
                  $twitterUsername = substr($raw_auth, 0, $firstParen - 1);
                  $realName = substr($raw_auth, $firstParen + 1, $nameLen);
                  if (empty($tweeters[$twitterUsername])) {
                    $tweeters[$twitterUsername] = 1;
                  } else {
                      $tweeters[$twitterUsername]++;
                    }
                  $classifications[] = array($twitterUsername, $realName);
                  break;
              }
            }
          }
        }
        
		echo "Number of Twitter users uploaded for integration " . $integrationArray['integrationName'] . "(" . $searchTerm . "): " . count($tweeters) . "\n";

		$totalTwitterUsers += count($tweeters);
        foreach ($tweeters as $tweeter => $tweets) {
          $tweetData[] = array($mdyToday, $searchTerm, $tweeter, $tweets);
        }
      }

	  // Save most recent tweet id for next Twitter call
      if ($firstTweetId > 0) {
        $fp = fopen($tweetFile, 'w');
        fwrite($fp, $firstTweetId);;
        fclose($fp);
      }
    }
  }

  if ($totalTwitterUsers > 0) {
    // Upload the data to Analytics
    $functionName = 'Import.UploadMetrics';
    $params = array('integrationCode' => $integrationCode,
      'dataSourceID' => $dataSourceId,
      'endOfBlock' => 'y',
      'columnNames' => array(
      'Date',
      'Twitter Search Term',
      'Twitter',
      'Tweets'),
    'rows' => $tweetData);

  $result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
  if (array_key_exists('faultstring', $result)) {
    echo "Error-UploadMetrics: " . $result['faultstring'] . "\n";
  }

  // Upload the classifications to Analytics
  $functionName = 'Import.UploadClassifications';
  $params = array('integrationCode' => $integrationCode,
    'dataSourceID' => $dataSourceId,
    'metricName' => 'Twitter',
    'endOfBlock' => 'y',
    'columnNames' => array(
      'Key',
      'Twitter User'),
    'rows' => $classifications);

	$result = $soapApp->sendRequest($functionName, $params, $wsdlType, $debug);
    if (is_array($result) && array_key_exists('faultstring', $result)) {
      echo "Error-UploadClassifications: " . $result['faultstring'] . "\n";
    }
  }
 }
}
?>
```

