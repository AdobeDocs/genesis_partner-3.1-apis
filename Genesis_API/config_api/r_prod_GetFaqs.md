# Product.GetFaqs

Returns the FAQs for a product.

Added in Data Connectors 3.0.

## Product.GetFaqs Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

## Product.GetFaqs Response

|Parameter|Type|Description|
|---------|----|-----------|
|** **faqs** ** | An array of [Product.productFaq](../../data_types/r_datatype_productFaq.md#) | |

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

