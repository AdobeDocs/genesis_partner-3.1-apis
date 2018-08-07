# Product.Add

**NOTE - This API has been sunset as of August, 2018.**

Creates a new Data Connectors product.

A Data Connectors Product does the following:

-   Defines the integration characteristics between the partner's product or service and our Suite client collection servers.
-   Facilitates the day-to-day transfer of data between the partner's environment and our Suite collection servers.

## Product.Add Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**contactName** |`xsd:string` | Yes| The name of the principal technical contact.|
|**contactEmail** |`xsd:string` | Yes| The email of the principal technical contact.|
|**version** |`xsd:string` | Yes| The version to assign to the product.|
|**industry** |`xsd:string` | Yes| The industry which best applies to this product.|
|**details** |[tns:productDetailsList](../../data_types/r_datatype_productDetailsList.md#) | Yes| The information about this product.|
|**supportPhone** |`xsd:string` | Yes| Phone contact for support.|
|**supportEmail** |`xsd:string` | Yes| Email contact for support.|

## Product.Add Response

|Response|Type|Description|
|--------|----|-----------|
|**productCode** |`xsd:string` | A unique code assigned to the new product.|
|**status** |`xsd:string` | Status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

