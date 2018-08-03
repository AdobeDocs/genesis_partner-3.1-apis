# Partner.GetIntegrations

Returns details about active Data Connectors integrations.

## Partner.GetIntegrations Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**filter** |`xsd:string` | No| An expression-like string that limits the returned results. The format for filter string is as follows:

 `<Variable1> <Operator1> <Constant1>[, <Variable2> <Operator2> <Constant2>[, ...]]` 

 The list below this table contains the available filter items.

 CustomVals are searched with a customValue filter similar to the following:

 `<filter xsi:type="xsd:string">customValue='key=value'</filter>` 

 **Variable:** One of the keys returned in the Partner.GetIntegrationAccess response.

 **Operator:** A boolean operator \(<, <=, =, \>, \>=, or !=\).

 **Constant:** The filter value. Constant is either a string expression \(enclosed in single or double quotes\), or a numeric value.

 For example, the following filter returns all integrations between d1.100 and d2.200:

 `integrationCode >= "d1.100", integrationCode <= "d1.200"` |

The following filter items are available:

integrationCode

integrationName

integrationEmail

integrationTimeZone

integrationCurrency

productCode

productVersion

productName

reportSuiteId

company

creationDate

lastModifiedDate

status

selectedSegment

soapEndpoint

customValue

## Partner.GetIntegrations Response

|Response|Type|Description|
|--------|----|-----------|
|**integrationInfo** |[integrationDetails](../../data_types/r_datatype_integrationDetails.md#) | Displays details about the active integrations that pass the specified filter definition.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

