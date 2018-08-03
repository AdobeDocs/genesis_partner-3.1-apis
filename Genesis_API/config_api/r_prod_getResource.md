# Product.GetResource

Returns the specified resource associated with the specified product.

## Product.GetResource Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**resourceCode** |`xsd:string` | Yes| The unique code assigned to the resource you want to get.|

## Product.GetResource Response

|Parameter|Type|Description|
|---------|----|-----------|
|**resource** |[productResource](../../data_types/r_datatype_productResource.md#) | A structure containing information about the specified resource.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

