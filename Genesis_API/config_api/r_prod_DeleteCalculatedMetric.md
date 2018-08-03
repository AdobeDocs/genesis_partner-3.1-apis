# Product.DeleteCalculatedMetric

Deletes a calculated metric for a product.

Added in Data Connectors 3.1.

## Product.DeleteCalculatedMetric Parameters

|Element|Type|Required|Description|
|-------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**name** |`xsd:string` | Yes| Name of the calculated metric to be deleted.|

 

## Product.DeleteCalculatedMetric Response

|Parameter|Type|Description|
|---------|----|-----------|
|** **status** ** | [status](../../data_types/r_datatype_status.md#) | A status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

