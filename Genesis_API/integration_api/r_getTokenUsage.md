# Partner.GetTokenUsage

Returns the sandbox token usage details for the authenticated partner.

## Partner.GetTokenUsage Parameters

None. Data Connectors determines the partner identity based on the authentication credentials used to log in to the Data Connectors Partner Portal.

## Partner.GetTokenUsage Response

|Response|Type|Description|
|--------|----|-----------|
|**allowedTokens** |`xsd:int` | The total number of tokens available for use during a usage period.|
|**consumedTokens** |`xsd:int` | The number of tokens consumed during the current usage period.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

