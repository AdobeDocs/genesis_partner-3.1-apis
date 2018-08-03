# Product.GetProductApprovalStatus

Returns a current status of the approval process.

## Product.GetProductApprovalStatus Parameters

Call this method after [Product.SubmitProductForApproval](r_prod_submitProductForApproval.md#) to check the approval status.

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

## Product.GetProductApprovalStatus Response

|Parameter|Type|Description|
|---------|----|-----------|
|**status** |`xsd:string` | Indicates the current status of the approval process for the submitted product integration. Suppported response values include `unsubmitted`, `pending`, `approved`, or `rejected`.|
|**comments** |`xsd:string` | If `status == rejected`, the comment contains a reason why the product integration was rejected.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

