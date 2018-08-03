# Product.ModifyProcessingRule

Modifies the processing rule template for this product.

Added in Data Connectors 3.1.

## Product.ModifyProcessingRule Parameters

|Element|Type|Required|Description|
|-------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
| **xml** | `xsd:string` | Yes| The processing rule template XML string.|

 

## Product.ModifyProcessingRule Response

|Parameter|Type|Description|
|---------|----|-----------|
|** **status** ** | [status](../../data_types/r_datatype_status.md#) | A status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

