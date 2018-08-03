# Product.Delete

Deletes an existing Data Connectors product.

## Product.Delete Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [``](../integration_api/r_getProducts.md#).|

## Product.Delete Response

|Response|Type|Description|
|--------|----|-----------|
|**success** |`xsd:boolean` | Indicates if the operation succeeded \(`True`\) or failed \(`False`\).|
|**status** |`xsd:string` | Status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

