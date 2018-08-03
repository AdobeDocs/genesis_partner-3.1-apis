# Product.GetLogo

Gets the logo of a product for a given locale.

Added in Data Connectors 3.0.

## Product.GetLogo Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**locale** |`xsd:string` | No| The locale to be used for the image uploaded. If no locale is used, Data Connectors defaults to `en_US`.|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

## Product.GetLogo Response

|Parameter|Type|Description|
|---------|----|-----------|
| **encodedData** | `xsd:string` | The base64-encoded string of the Data Connectors logo to be updated. The image must be transparent, 88x28 pixels, in either GIF or PNG format.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

