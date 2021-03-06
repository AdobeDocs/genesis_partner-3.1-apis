# Import.CheckMetricsUpload

Checks a Data Connectors data submission.

## Import.CheckMetricsUpload Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**fileId** |`xsd:int` | Yes| The unique ID generated by the Processing Queue to identify a particular Data Connectors classifications submission.

 Returned by [Import.UploadMetrics](r_uploadMetrics.md#) or [Import.ContinueMetricsUpload](r_ContinueMetricsUpload.md#) |
|**integrationCode** |`xsd:string` | Yes| The integration identifier. Call [Partner.GetIntegrationAccess](r_getIntegrationAccess.md#) to get this value.|

## Import.CheckMetricsUpload Response

|Response|Type|Description|
|--------|----|-----------|
|**fileInfoResult** |Array of `DataSource.[dsFileStruct](../../../data_sources_api/data_types/r_ds_file_struct.md#) | Contains information about the submitted files associated with a data source.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

