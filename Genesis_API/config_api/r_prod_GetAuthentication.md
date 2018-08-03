# Product.GetAuthentication

Returns authentication configuration information

Added in Data Connectors 3.0.

## Product.GetAuthentication Request

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [``](../integration_api/r_getProducts.md#).|

## Product.GetAuthentication Response

|Parameter|Type|Description|
|---------|----|-----------|
| **authenticationConfiguration** | `authResponse` | **AuthResponse**:

 •type type string

 •functionName type string

 •response type string

 •url type string

 •endpoint type string

 •parameterList type authenticationParameterArray - array of type authenticationParameter

 •type type string

 •location type string

 •name type string

 •value type string

 •label type string

 •p\_order type int|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

