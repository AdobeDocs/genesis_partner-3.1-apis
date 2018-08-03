# productClassification

|Element|Type|Description|
|-------|----|-----------|
|**metricName** |`xsd:string` | The partner’s metric name.|
|**classificationName** |`xsd:string` | Name of the classification.|
|**classificationNum** |`xsd:integer` | Numeric identifier of this classification for this metric.|
|**parentClassificationNum** |`xsd:integer` | Item that this classification is classifying. Assign a value of 0 if it is simple classifying the metric directly.|
|**campaignViewFlag** |`xsd:integer` | Whether or not to treat this classification like a campaign.|
|**type** |`tns:productClassificationType` | The classification type: Numeric or Text.|
|**childNodes** |[productClassificationList](r_datatype_productClassificationList.md#) | A list of child `productClassification` objects.|

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)

