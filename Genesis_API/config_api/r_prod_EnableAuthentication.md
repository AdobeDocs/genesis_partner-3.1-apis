# Product.EnableAuthentication

Enables authentication to partner APIs.

Added in Data Connectors 3.0.

To authenticate to a partner API, you need the following:

-   Authentication methods supported by the partner API
-   Name of the partner API that performs the authentication \(for example, `authenticate`\)
-   Location of the partner WSDL

## Product.EnableAuthentication Request

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**endpoint** |`xsd:string` | No| Optional only if the endpoint can be determined using the WSDL. Full URL to the endpoint where authentication occurs. For example, `http://myhost/Authenticationservice.asmx?` |
|**functionName** |`xsd:string` | Yes| Name of the function that performs authentication in the partner API. For example, `authenticate`.|
|**parameterList** |Array of `authenticationParameter` | Yes|  [Product.authenticationParameter](../../data_types/r_datatype_authenticationParameter.md#).|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [``](../integration_api/r_getProducts.md#).|
|**response** |`xsd:string` | Yes| String to parse out of the response message from the partner authentication API that indicates success. If this string is not located in the response the authentication attempt is considered unsuccessful. For example, "request OK".|
|**type** |`xsd:string` | Yes| Authentication type to use. One of the following values:

 -   plain
-   soap
-   wsse
-   curl|
|**url** |`xsd:string` | Yes| Typically the URL of the WSDL, or an asmx file for CURL.|

## Product.EnableAuthentication Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[status](../../data_types/r_datatype_status.md#) | A status code and associated message related to the operation.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

