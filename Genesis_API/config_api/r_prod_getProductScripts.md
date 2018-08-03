# Product.GetProductScripts

Returns a list of all product scripts submitted for the specified product.

## Product.GetProductScripts Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

## Product.GetProductScripts Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[string\_array](../../data_types/r_datatype_string_array.md#) | A list of product scripts submitted for the specified product code.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

