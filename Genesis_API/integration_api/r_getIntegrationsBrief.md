# Partner.GetIntegrationsBrief

Returns brief information about a partner's active Data Connectors integrations.

Added in Data Connectors 3.1.

## Partner.GetIntegrationsBrief Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**filter** |`xsd:string` | No| An expression-like string that limits the returned results. The format for filter string is as follows:

 `<Variable1> <Operator1> <Constant1>[, <Variable2> <Operator2> <Constant2>[, ...]]` 

 CustomVals are searched with a customValue filter similar to the following:

 `<filter xsi:type="xsd:string">customValue='key=value'</filter>` 

 **Variable:** One of the keys returned in the Partner.GetIntegrationAccess response.

 **Operator:** A boolean operator \(<, <=, =, \>, \>=, or !=\).

 **Constant:** The filter value. Constant is either a string expression \(enclosed in single or double quotes\), or a numeric value.

 For example, the following filter returns all integrations between d1.100 and d2.200:

 `integrationCode >= "d1.100", integrationCode <= "d1.200"` |

## Partner.GetIntegrationsBrief Response

|Response|Type|Description|
|--------|----|-----------|
|**integrationBriefs** |Array of [integrationBrief](../../data_types/r_datatype_integrationBriefs.md#) | Displays details about the active integrations that pass the specified filter definition.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

