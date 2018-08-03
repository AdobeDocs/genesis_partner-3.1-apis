# Export.GetClassificationData

Retrieves classification data for a Data Connectors partner which was requested previously from Export.RequestClassificationData.

## Export.GetClassificationData Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | Yes| The partner product for which you want to retrieve classification data.|
|**file\_id** |`xsd:int` | Yes| The ID of the export file you want to view.

 You can get this value from `classifications.CheckJobStatus`.|
|**segment\_id** |`xsd:int` | Yes| The number of the data page you want to view from the SAINT export job.

 The `viewable_pages` value in `classifications.CheckJobStatus` indicates the number of data pages in the job. Valid values for `segment_id` are between 1 and the value of `viewable_pages`.|

## Export.GetClassificationData Response

|Name|Type|Description|
|----|----|-----------|
|**rows** |[tns:pagedetails](../../../saint_api/data_types/r_pagedetails.md#) | Information and data for the specified SAINT data segment.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

