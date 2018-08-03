# Product.GetProcessingRule

Get the processing rule template for this product.

Added in Data Connectors 3.1.

## Product.GetProcessingRule Parameters

|Element|Type|Required|Description|
|-------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

 

## Product.GetProcessingRule Response

|Parameter|Type|Description|
|---------|----|-----------|
|** **rule** ** | [productProcessingRule](../../data_types/r_datatype_productProcessingRule.md#) | Processing rule template.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

