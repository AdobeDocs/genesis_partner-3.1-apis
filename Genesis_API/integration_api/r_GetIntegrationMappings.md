# Partner.GetIntegrationMappings

Retrieves the mappings and access chosen by the user for an Integration.

## Partner.GetIntegrationMappings Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | No| An array of information about one partner product. `Partner.GetProducts` returns a separate array of product information for each product associated with the current partner.|

## Partner.GetIntegrationMappings Response

|Response|Type|Description|
|--------|----|-----------|
|**chosenMappings** |`string_array` |The chosen data mappings which were selected by the user.|
|**chosenAccessRequests** |[chosenAccessRequests](../../data_types/r_chosenAccessRequests.md#) |The chosen access requests selected by the user. These contain the exportable access requests \(can be requested via Data Warehouse\) and importable access requests \(can be imported with Data Sources and SAINT\).|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

