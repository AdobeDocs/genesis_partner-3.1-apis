# Product.ModifyClassification

Modifies a classification for a metric.

Added in Data Connectors 3.1.

## Product.ModifyClassification Parameters

|Element|Type|Required|Description|
|-------|----|--------|-----------|
| **productCode** | `xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**classificationName** |`xsd:string` | Yes| Name of the classification.|
|**metricName** |`xsd:string` | Yes| The partner’s metric name.|
| **classificationNum** |`xsd:integer` | Yes| ID of the classification you want to modify.|
|**type** |`xsd:string` | Yes| One of the following values indicating the classification type:

 -   text
-   numeric
-   percent
-   currency|
|**campaignViewFlag** |`xsd:integer` | False| Whether or not to treat this classification like a campaign.|

## Product.ModifyClassification Response

|Parameter|Type|Description|
|---------|----|-----------|
| **classificationNum** |`xsd:integer` | ID for the new classification.|
| **metricName** |`xsd:string` | The partner’s metric name.|
|** **status** ** | [status](../../data_types/r_datatype_status.md#) | A status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

