# Product.ModifyAccessRequest

Modifies an existing access request for the specified product.

## Product.ModifyAccessRequest Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**access** |`xsd:string` | Yes| The type of access that is being requested: `import`, `export`, or `import/export`.|
|**element** |`xsd:string` | Yes| The name of the metric or dimension that access is being requested for. See [Data Connectors Standard Elements](../../standard_elements/r_standard_elements.md#) for a list of valid values for this parameter.|
|**required** |`xsd:string` | Yes| Specifies if the request must be granted to complete the integration. Either `yes` or `no`.|

## Product.ModifyAccessRequest Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[status](../../data_types/r_datatype_status.md#) | A status code and associated message related to the operation.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

