# Product.AddVariableMappings

Configures mappings between partner product metrics and Analytics eVars, events, and properties.

## Product.AddVariableMappings Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [``](../integration_api/r_getProducts.md#).|
|**variableMappings** |array\([tns:varMapAll](../../data_types/r_datatype_varMapAll.md#)\)| Yes| XML that defines the variable mappings.|

## Product.AddVariableMappings Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[status](../../data_types/r_datatype_status.md#) | A status code and associated message related to the operation.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

