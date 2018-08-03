# Product.GetClassifications

Get classifications for a product.

Added in Data Connectors 3.1.

## Product.GetClassifications Parameters

|Element|Type|Required|Description|
|-------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

 

## Product.GetClassifications Response

|Parameter|Type|Description|
|---------|----|-----------|
|** **classificationList** ** | [productClassificationList](../../data_types/r_datatype_productClassificationList.md#) | Classifications defined for the specified product.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

