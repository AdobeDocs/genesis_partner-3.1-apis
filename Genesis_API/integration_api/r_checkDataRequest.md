# Export.CheckDataRequest

Returns the status of a previously requested data segment.

## Export.CheckDataRequest Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | Yes| The integration where you want to submit the metric data. Call [Partner.GetIntegrationAccess](r_getIntegrationAccess.md#) to get this value.|
|**requestId** |`xsd:int` | Yes| The data segment identifier that you want to get. The [Export.RequestSegmentedData](r_requestSegmentedData.md#) method returns this identifier when it creates a new data segment.|

## Export.CheckDataRequest Response

|Response|Type|Description|
|--------|----|-----------|
|**return** |[data\_warehouse\_request](../../data_types/r_datatype_data_warehouse_request.md#) | A structure that includes information about the specified data request.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

