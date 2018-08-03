# Export.ProduceResource

Produces a dynamic resource for the specified integration.

## Export.ProduceResource Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | Yes| The integration identifier. Call [Partner.GetIntegrationAccess](r_getIntegrationAccess.md#) to get this value.|
|**resourceCode** |`xsd:string` | Yes| The resource identifier.|

## Export.ProduceResource Response

|Response|Type|Description|
|--------|----|-----------|
|**return** |[productResourceContent](../../data_types/r_datatype_productResourceContent.md#) | A structure containing the resource content.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

