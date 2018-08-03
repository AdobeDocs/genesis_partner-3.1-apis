# Partner.RunScript

Runs an on-demand script against a client’s account during an integration.

For sample code related to using `Partner.RunScript` with on-demand product scripts, see [Sample On-Demand Script Usage](../../code_samples/on-demand_script/c_sample_ondemand_scripts.md#).

## Partner.RunScript Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | Yes| The integration identifier. Call [Partner.GetIntegrationAccess](r_getIntegrationAccess.md#) to get this value.|
|**name** |`xsd:string` | Yes| The name of the on-demand script to execute. You can select only scripts that were submitted with the `runOn = demand` parameter \(see [Product.SubmitProductScript](../config_api/r_prod_submitProductScript.md#)\).|
|**parameters** |[scriptParameters](../../data_types/r_datatype_scriptParameters.md#) | Yes| The parameters inserted into the script’s `replaceWith` attributes. The list must include values for ALL `replaceWith` parameters.|

## Partner.RunScript Response

|Response|Type|Description|
|--------|----|-----------|
|**functionName** |`xsd:string` | Name of the on-demand script executed.|
|**hadSOAPFault** |`xsd:boolean` | Indicates if a SOAP error was encountered.

  |
|**result** |any| An array that contains the script results.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

