# Partner.GetProduct

Get the product for the given partner.

Added in Data Connectors 3.1.

While this method is part of the Integration API, you might find it useful in both the Configuration and Integration phases of the integration development process.

## Partner.GetProduct Parameters

|Response|Type|Description|
|--------|----|-----------|
|**productCode** |`xsd:string` | An array of information about one partner product. `Partner.GetProduct` returns an array of product information for the product identified by the specified productCode.|

## Partner.GetProduct Response

|Response|Type|Description|
|--------|----|-----------|
|**productInfo** |[tns:product](../../data_types/r_datatype_product.md#) | An array of information about one partner product. `Partner.GetProducts` returns a separate array of product information for each product associated with the current partner.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

