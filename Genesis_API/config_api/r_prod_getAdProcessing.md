# Product.GetAdProcessing

Returns the current add processing settings for the specified product.

## Product.GetAdProcessing Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

## Product.GetAdProcessing Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[adProcessingStatus](../../data_types/r_datatype_adProcessingStatus.md#) | The current ad processing status for the specified Data Connectors product.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

