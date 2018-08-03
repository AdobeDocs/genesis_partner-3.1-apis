# Product.AddCalculatedMetric

Add a calculated metric for a product.

Added in Data Connectors 3.1.

## Product.AddCalculatedMetric Parameters

|Element|Type|Required|Description|
|-------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**name** |`xsd:string` | Yes| Name of the calculated metric to be created.|
|**formula** |`xsd:string` | Yes| The formula for the new calculated metric.|
|**replace\_with\_mapping** |`xsd:boolean` | Yes| Set to 1 to automatically replace formula metrics with variable-mapped metrics when an integration is saved.|
|**friendly\_formula** |`xsd:string` | Yes| Human-readable calculated metric formula.|
|**metric\_type** |`xsd:integer` | Yes| The type of metric to be created. 1:numeric, 2:percent, 3:currency|
|**decimal\_places** |`xsd:integer` | Yes| The number of decimal places to be displayed for this formula result.|

 

## Product.AddCalculatedMetric Response

|Parameter|Type|Description|
|---------|----|-----------|
|** **status** ** | [status](../../data_types/r_datatype_status.md#) | A status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

