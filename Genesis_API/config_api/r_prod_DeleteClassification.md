# Product.DeleteClassification

Deletes a classification for a metric.

Added in Data Connectors 3.1.

## Product.DeleteClassification Parameters

|Element|Type|Required|Description|
|-------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**metricName** |`xsd:string` | Yes| Name of the metric where the classification is created.|
|**parentClassificationNum** |`xsd:integer` | False| The parent classification's classificationNum. Assign a value of 0 or leave empty if it is simple classifying the metric directly.|

## Product.DeleteClassification Response

|Parameter|Type|Description|
|---------|----|-----------|
|** **status** ** | [status](../../data_types/r_datatype_status.md#) | A status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

