# Product.Clone

**NOTE - This API has been sunset as of August, 2018.**

Creates a new Data Connectors product based on an existing product.

This is useful when you need to update a product integration due to a new release.

## Product.Clone Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [``](../integration_api/r_getProducts.md#).|
|**newProductVersion** |`xsd:string` | Yes| The product version of the new product.|

## Product.Clone Response

|Response|Type|Description|
|--------|----|-----------|
|**productCode** |`xsd:string` | A unique code assigned to the new product.|
|**status** |`xsd:string` | Status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

