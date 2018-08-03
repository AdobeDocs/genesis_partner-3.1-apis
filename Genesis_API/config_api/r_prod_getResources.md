# Product.GetResources

Returns all of the resources associated with the specified product.

Data Connectors 3.0: Added `includeResourceFile`.

## Product.GetResources Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**includeResourceFile** |`xsd:boolean` | Yes| Controls whether or not the actual file data associated with each resource is returned with the response.  If “false”, the call will return a list of resources without returning the actual file data.  If “true”, data for each file-based resource will be returned.

 Added in Data Connectors 3.0|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

## Product.GetResources Response

|Parameter|Type|Description|
|---------|----|-----------|
|**resource** |[productDetailsList](../../data_types/r_datatype_productDetailsList.md#) | A list of all resources associated with the specified product.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

