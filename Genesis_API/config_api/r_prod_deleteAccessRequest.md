# Product.DeleteAccessRequest

Deletes an access request from the specified product.

## Product.DeleteAccessRequest Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**element** |`xsd:string` | Yes| The name of the metric or dimension where you want to delete the access request. See [Data Connectors Standard Elements](../../standard_elements/r_standard_elements.md#) for a list of valid values for this parameter.|

## Product.DeleteAccessRequest Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[status](../../data_types/r_datatype_status.md#) | A status code and associated message related to the operation.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

