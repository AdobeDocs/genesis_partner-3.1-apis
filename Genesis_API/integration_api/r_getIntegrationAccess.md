# Partner.GetIntegrationAccess

Lets a partner see what data a customer has granted access to in the integration.

Also identifies if the client has granted export access, import access, or both.

## Partner.GetIntegrationAccess Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | No| An array of information about one partner product. `Partner.GetProducts` returns a separate array of product information for each product associated with the current partner.|

## Partner.GetIntegrationAccess Response

|Response|Type|Description|
|--------|----|-----------|
|**element** |`xsd:string` | Displays the name of the element for which access was requested.|
|**requested** |`xsd:string` | Displays the level of access that was requested: import, export, or import/export.|
|**granted** |`xsd:string` | Displays the level of access that was granted by the customer: `import`, `export`, or `import/export`.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

