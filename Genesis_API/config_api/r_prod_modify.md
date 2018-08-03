# Product.Modify

Modifies the Data Connectors product as specified.

## Product.Modify Parameters

|Parameter|Type|Description|
|---------|----|-----------|
|**productCode** |`xsd:string` | A valid Data Connectors product code. You can get a list of your company's product codes by calling [``](../integration_api/r_getProducts.md#).|
|**contactName** |`xsd:string` | The name of the principal technical contact.|
|**contactEmail** |`xsd:string` | The email of the principal technical contact.|
|**version** |`xsd:string` | The product version.|
|**industry** |`xsd:string` | The industry which best applies to this product.|
|**details** |[tns:productDetailsList](../../data_types/r_datatype_productDetailsList.md#) | Detailed information about the product configuration.|
|**supportPhone** |`xsd:string` | Phone contact for support.|
|**supportEmail** |`xsd:string` | Email contact for support.|

## Product.Modify Response

|Parameter|Type|Description|
|---------|----|-----------|
|**productCode** |`xsd:string` | A unique product code associated with this Data Connectors product.|
|**status** |`xsd:string` | A status message pertaining to the success of the action.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

