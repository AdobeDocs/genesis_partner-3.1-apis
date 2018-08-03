# Product.AddResource

Adds a resource to the specified product.

## Product.AddResource Parameters

A resource is additional information or code that a client needs when activating an integration. Data Connectors provides clients access to integration resources in multiple ways, including:

-   On the Summary page of the Data Connectors Integration Wizard
-   In an Email sent upon activating an integration
-   In the Data Connectors UI by clicking the Resources link

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**type** |[productResourceType](../../data_types/r_datatype_productResourceType_enum.md#) | Yes| The type of resource to add.|
|**title** |`xsd:string` | Yes| The resource name.|
|**description** |`xsd:string` | Yes| The resource URL.

 If the `type = static` or `type = dynamic`, then the URL must be the publicly accessible location of a resource document. Data Connectors downloads the document and stores it on its servers. The `url` parameter truncates the value to the name of the file instead of the full URL.

 Nothing is done if type is set to `link`.|
|**url** |`xsd:string` | No| Contains the name and base64-encoded bytes of a file that is uploaded to our servers directly.|
|**resourceFile** |[resourceEncoded](../../data_types/r_datatype_resourceEncoded.md#) | No| Contains the name and base64-encoded bytes of a file that is uploaded to Data Connectors servers directly.|
|**variablePrefix** |`xsd:string` | No| Used only when `type = dynamic`.

 A unique string value used to identify the start of a variable in the dynamic file.|
|**variableSuffix** |`xsd:string` | No| Used only when `type = dynamic`.

 A unique string value, which can be the same as `variablePrefix`, used to identify the end of a variable in the dynamic file.|
|**locale** |`xsd:string` | No| The language locale used for this resource.

 Defaults to en\_US.|

## Product.AddResource Response

|Parameter|Type|Description|
|---------|----|-----------|
|**resourceCode** |`xsd:string` | A unique code assigned to the new resource.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

