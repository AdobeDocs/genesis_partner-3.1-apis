# productResource

|Element|Type|Description|
|-------|----|-----------|
|**resourceCode** |`xsd:string` | A partner-specific value used to identify the click and view data in the request.|
|**type** |`productResourceType` | The type of resource you want to add. Supported values include `link`, `static`, and `dynamic`.|
|**title** |`xsd:string` | A title for the resource.|
|**description** |`xsd:string` | A description of the resource.|
|**url** |`xsd:string` | The resource URL.<br/> If the type field is set to `static` or `dynamic` then the URL must be the publically accessible location of a resource document. Data Connectors downloads the document and stores it on its servers. The `url` parameter is truncated to file name instead of the full URL.<br/> Nothing is done if type is set to `link`.|
|**resourceFile** |`resourceEncoded` | Contains the name and base64-encoded bytes of a file that is uploaded to our servers directly.|
|**variablePrefix** |`xsd:string` | Used only with dynamic resources.<br/> The prefix used to delimit variables in the dynamic resource file that will be replaced on the fly with information specific to any particular integration.|
|**variableSuffix** |`xsd:string` | Used only with dynamic resources.<br/> The suffix used to delimit variables in the dynamic resource file that will be replaced on the fly with information specific to any particular integration.|
|**locale** |`xsd:string` |The locale used for this resource.|<br/>

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)