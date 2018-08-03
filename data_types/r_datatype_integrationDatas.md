# integrationData

|Element|Type|Description|
|-------|----|-----------|
|**integrationCode** |`xsd:string` | The integration's unique identifier.|
|**integrationName** |`xsd:string` | The integration name.|
|**integrationEmail** |`xsd:string` | The email address that receives notifications and messages for this integration.|
|**integrationTimeZone** |`xsd:string` | The time zone of the report suite that contains this integration.|
|**integrationCurrency** |`xsd:string` | The currency of the report suite that contains this integration.|
|**productCode** |`xsd:string` | The version of the product that this integration represents.|
|**productVersion** |`xsd:string` | The version of the product that this integration represents.|
|**productName** |`xsd:string` | The product name related to this integration.|
|**reportSuiteId** |`xsd:string` | The report suite that uses this integration.|
|**company** |`xsd:string` | The company that created this integration.|
|**creationDate** |`xsd:string` | The date and time this integration was created.|
|**lastModifiedDate** |`xsd:string` | The date and time this integration was last modified.|
|**status** |`xsd:string` | One of the following:<br/>-   In Progress <br/>-   Active <br/>-   Deleted <br/>-   Paused|
|**selectedSegments** |`string_array` | If applicable, a list of the data segments chosen during the creation of the integration \(in the Data Connectors Wizard\).|
|**integrationValues** |`integrationValues` | An array of [integrationValue](r_datatype_integrationValue.md#) that contains the variable mappings and the value that was entered for this integration.|
|**dataSourceIds** |[int\_array](r_datatype_int_array.md#) | The list of Data Source IDs created for this integration. Use the Data Source IDs with `Import.UploadMetrics`.|
|**soapEndpoint** |`xsd:string` | The SOAP endpoint used to perform the integration’s data exchange.|
|**integrationAccesses** |Array of `ntegrationAccess` | [integrationAccess](r_datatype_integrationAccess.md#) |
|**integrationMappings** |Array of `integrationMapping` | [integrationMapping](r_datatype_integrationMapping.md#) |<br/>

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)