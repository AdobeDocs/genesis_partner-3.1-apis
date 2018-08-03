# Product.EnableAdProcessing

Enables ad processing during the product configuration in the Data Connectors environment.

## Product.EnableAdProcessing Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [``](../integration_api/r_getProducts.md#).|
|**prefix** |`xsd:string` | Yes| A partner-specific value used to identify the click and view data in the request.|
|**variables** |[adProcessingVariables](../../data_types/r_datatype_adProcessingVariables.md#) | Yes| Specifies the names of the variable mappings used to receive data from the ad processing system.|
|**settings** |[adProcessingSettings](../../data_types/r_datatype_adProcessingSettings.md#) | No| Specifies settings that change the behavior and setup of the ad processing system.|

## Product.EnableAdProcessing Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[status](../../data_types/r_datatype_status.md#) | A status code and associated message related to the operation.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

