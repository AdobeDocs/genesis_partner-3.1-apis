# integrationDetail

|Element|Type|Description|
|-------|----|-----------|
|**integrationCode** |`xsd:string` | The integration's unique identifier.|
|**integrationName** |`xsd:string` | The integration name.|
|**integrationEmail** |`xsd:string` | The email address that receives notifications and messages for this integration. See [Time Zones](../Overview/c_Time_Zones.md#).|
|**integrationTimeZone** |`xsd:string` | The time zone of the report suite that contains this integration.|
|**integrationCurrency** |`xsd:string` | The currency of the report suite that contains this integration. See [Currency Codes](http://microsite.omniture.com/t2/help/en_US/reference/index.html?f=currency).|
|**productCode** |`xsd:string` | The version of the product that this integration represents.|
|**productVersion** |`xsd:string` | The version of the product that this integration represents.|
|**productName** |`xsd:string` | The product name related to this integration.|
|**reportSuiteId** |`xsd:string` | The report suite that uses this integration.|
|**company** |`xsd:string` | The company that created this integration.|
|**creationDate** |`xsd:string` | The date and time this integration was created.|
|**selectedSegments** |`string_array` | If applicable, a list of the data segments chosen during the creation of the integration \(in the Data Connectors Wizard\).|
|**integrationValues** |`integrationValues` | A list of `customval` variable mappings and the value that was entered for this integration.|
|**dataSourceIds** |[int\_array](r_datatype_int_array.md#) | The list of Data Source IDs created for this integration. Use the Data Source IDs with `Import.UploadMetrics`.|
|**soapEndpoint** |`xsd:string` | The SOAP endpoint used to perform the integration’s data exchange.|

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)

