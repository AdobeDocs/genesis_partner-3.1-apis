# Product.UpdateLogo

Modifies the logo graphic that Data Connectors displays in the Partner List.

In Data Connectors 3.0, `Product.UpdateLogo` was renamed to [Product.ModifyLogo](r_prod_ModifyLogo.md#). The parameters have not changed so you can safely rename the method with no additional changes.

## Product.UpdateLogo Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**encodedData** |`xsd:string` | Yes| The base64-encoded string of the Data Connectors logo to be updated. The image must be transparent, 88x28 pixels, in either GIF or PNG format.|
|**locale** |`xsd:string` | No| The locale to be used for the image uploaded. If no locale is used, Data Connectors defaults to `en_US`.|

## Product.UpdateLogo Response

|Parameter|Type|Description|
|---------|----|-----------|
|**result** |`xsd:string` | Indicates if the logo was successfully updated. The response returns `Logo updated` if successful, or an error message if unsuccessful.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

