# Partner.GetProducts

Returns information about each product associated with the current Data Connectors partner.

While this method is part of the Integration API, you might find it useful in both the Configuration and Integration phases of the integration development process.

**Note:** Several Data Connectors API methods rely on the `productCode` returned by `Partner.GetProducts`.

## Partner.GetProducts Parameters

None. Data Connectors determines the product list based on the authentication credentials used to log in to the Data Connectors Partner Portal.

## Partner.GetProducts Response

|Response|Type|Description|
|--------|----|-----------|
|**productInfo** |[tns:product](../../data_types/r_datatype_product.md#) | An array of information about one partner product. `Partner.GetProducts` returns a separate array of product information for each product associated with the current partner.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

