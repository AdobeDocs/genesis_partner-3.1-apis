# Export.CheckClassificationRequest

Determines if a requested classification from Export.RequestClassificationData is ready to be acquired by Export.GetClassificationData or downloaded by REST URL.

## Export.CheckClassificationRequest Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | Yes| The partner product for which you want to retrieve classification data.|
|**requestId** |`xsd:int` | Yes| The request ID returned by [Export.RequestClassificationData](r_RequestClassificationData.md#).|

## Export.CheckClassificationRequest Response

|Name|Type|Description|
|----|----|-----------|
|**data\_url** |`xsd:string` | The REST URL where the data can be downloaded.|
|**return** |[tns:saintresults](../../../saint_api/data_types/r_saintresults.md#) | The status of the classification request. Possible values are as follows:

 -   Waiting for user data
-   In Progress
-   In Progress - <number\>% Complete
-   Completed
-   Completed - With Errors : <message\>|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

