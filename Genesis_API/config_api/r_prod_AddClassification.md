# Product.AddClassification

Add a classification for a metric.

Added in Data Connectors 3.1.

## Product.AddClassification Parameters

|Element|Type|Required|Description|
|-------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**classificationName** |`xsd:string` | Yes| Name of the classification to be created.|
|**metricName** |`xsd:string` | Yes| The partner’s metric name.|
|**parentClassificationNum** |`xsd:integer` | False| The parent classification's classificationNum. Assign a value of 0 or leave empty if it is simple classifying the metric directly.|
|**type** |`xsd:string` | Yes| One of the following values indicating the classification type:

 -   text
-   numeric
-   percent
-   currency|
|**version** |`xsd:integer` | False| Product version.|
|**campaignViewFlag** |`xsd:integer` | False| Whether or not to treat this classification like a campaign.|

## Product.AddClassification Response

|Parameter|Type|Description|
|---------|----|-----------|
| **classificationNum** |`xsd:integer` | ID for the new classification.|
| **metricName** |`xsd:string` | The partner’s metric name.|
|** **status** ** | [status](../../data_types/r_datatype_status.md#) | A status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

