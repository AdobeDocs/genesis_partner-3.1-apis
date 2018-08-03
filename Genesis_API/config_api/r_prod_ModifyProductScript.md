# Product.ModifyProductScript

Creates or modifies a product script.

Added in Data Connectors 3.0.

## Product.ModifyProductScript Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|
|**script** |`xsd:string` | Yes| The product script that you want to submit. For information about the script format and structure, see the [Product.GetProductScript](r_prod_getProductScript.md#)response.|
|**name** |`xsd:string` | Yes| A short name for this product script. The `scriptName` must be unique.|
|**description** |`xsd:string` | No| A detailed description of the product script.|
|**runOn** |`xsd:string` | Yes| When the script should execute. Supported values include:

 **demand:** Designates the script as an on-demand script that you can call at any time \(see [Partner.RunScript](../integration_api/r_runScript.md#)\).

 **integration\_create:** Runs the script after the Data Connectors Wizard completes for a new integration.

 **integration\_edit:** Runs the script after the Data Connectors Wizard completes for an existing integration.|

## Product.ModifyProductScript Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |[status](../../data_types/r_datatype_status.md#) | A status code and associated message related to the operation.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

