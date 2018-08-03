# Product.GetCalculatedMetrics

Gets all calculated metrics for a product.

Added in Data Connectors 3.1.

## Product.GetCalculatedMetrics Parameters

|Element|Type|Required|Description|
|-------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

 

## Product.GetCalculatedMetrics Response

|Parameter|Type|Description|
|---------|----|-----------|
|** **metrics** ** | [productCalculatedMetrics](../../data_types/r_datatype_productCalculatedMetrics.md#) | Details about calculated metrics.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

