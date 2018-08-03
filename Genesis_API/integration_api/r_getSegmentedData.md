# Export.GetSegmentedData

Downloads previously requested segment data.

You must first request the data segment using [Export.RequestSegmentedData](r_requestSegmentedData.md#). Use this method only when the data segment is less than 10MB. Use [Export.CheckDataRequest](r_checkDataRequest.md#) to determine the size of the data segment. For data segments larger than 10MB use the [Data Connectors REST Service](../../Overview/c_overview_rest.md#).

## Export.GetSegmentedData Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | Yes| The integration identifier. Call [Partner.GetIntegrationAccess](r_getIntegrationAccess.md#) to get this value.|
|**requestId** |`xsd:int` | Yes| The data segment identifier. The [Export.RequestSegmentedData](r_requestSegmentedData.md#) method returns this identifier when it creates a new data segment.|
|**startRow** |`xsd:int` | Yes| Start the retrieval at the specified row.|

## Export.GetSegmentedData Response

|Response|Type|Description|
|--------|----|-----------|
|**return** |[data\_warehouse\_report](../../data_types/r_datatype_data_warehouse_report.md#) | A table containing the requested segment data.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

