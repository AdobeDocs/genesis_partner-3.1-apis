# Product.ModifyFaq

Modify a FAQ for a product.

Added in Data Connectors 3.0.

## Product.ModifyFaq Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
| **answer** | `xsd:string` | Yes| Answer to the provided question.|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
| **question** | `xsd:string` | Yes| Question to add to the frequently asked questions list.|

## Product.ModifyFaq Response

|Parameter|Type|Description|
|---------|----|-----------|
|** **status** ** | [status](../../data_types/r_datatype_status.md#) | A status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

