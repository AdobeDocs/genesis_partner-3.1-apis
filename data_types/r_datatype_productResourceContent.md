# productResourceContent

|Element|Type|Description|
|-------|----|-----------|
|**status** |`xsd:int` | The status of the resource upload. Supported values include:<br/>  **`0`:** Success.<br/> **`1`:** Failure.|
|**error** |`xsd:string` | If `status = 1`, contains a message describing the cause of the failure.|
|**content** |`xsd:string` | The resource content. You must base64-encode a resource to upload it to Data Connectors. Data Connectors subsequently decodes the resource and stores it in this element.|<br/>

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)