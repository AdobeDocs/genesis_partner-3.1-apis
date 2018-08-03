# REST Service

 

Before May 2014, the Data Connectors REST service contained two REST APIs that provided a more efficient option for downloading large data segments \(\>10MB\), which are not available through the [Export.GetSegmentedData](../Genesis_API/integration_api/r_getSegmentedData.md#) method.

After May 2014, REST APIs are now available for all Data Connectors APIs. These APIs have the same method names, parameters list, and the same responses as the SOAP APIs.

REST APIs are hosted on a new endpoint, though the two previously supported REST APIs, Partner.StreamSegmentedData and Partner.StreamClassificationData will continue to use their original endpoint \(https://api.omniture.com/genesis/i/3.1/export/index.html\).

The REST API endpoint for all other APIs is:

```
https://api.omniture.com/genesis/rest/3.1/index.html
```

Both the configuration and integration REST APIs share the same endpoint.

The parameters can be appended to request URL as query parameters or added to HTTP body. The method name should always be added to URL similar to the following:

```
https://api.omniture.com/genesis/rest/3.1/index.html?method=Partner.GetProducts
```

User name and password should be passed by X-WSSE header in HTTP request as following:

```
Host: api.vm16.dev.ut1.omniture.com
Accept: */*
Content-Type: application/json
Content-Length: 0
X-WSSE: UsernameToken Username="adobe_xinw", PasswordDigest="Or/zpqhCFTZZEAE+mBUL/o623jE=", Nonce="+UOpU1tx3oN3ED05TVeVrg==", Created="2014-03-24GMT03:00:100"
```

The following PHP sample demonstrates how to generate X-WSSE

```
$username = 'username';
$password = 'password';
$created = gmdate('Y-m-dTH:i:sZ');
$nonce = md5(rand(), true);
$base64_nonce = base64_encode($nonce);
$password_digest = base64_encode(sha1($nonce.$created.$password, true));
$data = '{
    'data': 'JSON Object to post'
}';
$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, 'https://api.omniture.com/genesis/rest/index.html');
curl_setopt($curl, CURLOPT_POSTFIELDS, $data);
curl_setopt($curl, CURLOPT_HEADER, 0);
curl_setopt($curl, CURLOPT_POST, 1);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_HTTPHEADER, array(
    'Content-Type: application/json',
    'Content-Length: ' . strlen($data),
    sprintf('X-WSSE: UsernameToken Username="%s", PasswordDigest="%s", Nonce="%s", Created="%s"', $username, $password_digest, $base64_nonce, $created),
));
```

**Parent topic:** [Data Connectors Partner API](../Overview/c_genapi_overview.md)

