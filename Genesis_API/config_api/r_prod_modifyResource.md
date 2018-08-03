# Product.ModifyResource

Modifies an existing resource associated with the specified product.

## Product.ModifyResource Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**resourceCode** |`xsd:string` | Yes| A unique code assigned to the resource you want to modify.|
|**type** |[productResourceType](../../data_types/r_datatype_productResourceType_enum.md#) | No| The type of resource.|
|**title** |`xsd:string` | No| The resource name.|
|**description** |`xsd:string` | No| A description of the resource.|
|**url** |`xsd:string` | No| The resource URL.

 If the `type = static` or `type = dynamic`, then the URL must be the publicly accessible location of a resource document. Data Connectors downloads the document and stores it on its servers. The `url` parameter truncates the value to the name of the file instead of the full URL.

 Nothing is done if type is set to `link`.|
|**resourceFile** |[resourceEncoded](../../data_types/r_datatype_resourceEncoded.md#) | No| Contains the name and base64-encoded bytes of a resource file to upload directly to Data Connectors servers.|
|**variablePrefix** |`xsd:string` | No| Used only when `type = dynamic`.

 A unique string value used to identify the start of a variable in the dynamic file.|
|**variableSuffix** |`xsd:string` | No| Used only when `type = dynamic`.

 A unique string value, which can be the same as `variablePrefix`, used to identify the end of a variable in the dynamic file.|
|**locale** |`xsd:string` | No| The language locale used for this resource.

 Defaults to en\_US.|

## Product.ModifyResource Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[status](../../data_types/r_datatype_status.md#) | A status code and associated message related to the operation.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

