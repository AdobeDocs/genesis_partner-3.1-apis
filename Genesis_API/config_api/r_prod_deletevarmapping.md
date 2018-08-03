# Product.DeleteVariableMappings

Configures mappings between partner product metrics and Analytics eVars, events, and properties.

## Product.DeleteVariableMappings Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [``](../integration_api/r_getProducts.md#).|
|**variableMappings** |array\(`xsd:string`\)| Yes| A list of variable mappings to delete.|

## Product.DeleteVariableMappings Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[status](../../data_types/r_datatype_status.md#) | A status code and associated message related to the operation.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

