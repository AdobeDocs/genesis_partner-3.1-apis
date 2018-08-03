# Product.GetProductScript

Returns the product script from the specified Data Connectors product.

## Product.GetProductScript Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**Name** |`xsd:string` | Yes| Name of the script.|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [Partner.GetProducts](../integration_api/r_getProducts.md#).|

## Product.GetProductScript Response

|Type|Description|
|----|-----------|
| ```
<genesis>
<ReportSuite.SaveClassifications> <!-- **\#1** -->
   <c_options/>
   <c_view replaceWith="mapping">Ad Campaign</c_view> <!-- **\#2** -->
   <camp_view>0</camp_view>
   <name>My Site Name</name>
   <rsid_list>
      <item replaceWith="client">RSID</item> <!-- **\#3** -->
   </rsid_list>
</ReportSuite.SaveClassifications>
<Report.QueueRanked>
...
</Report.QueueRanked>
</genesis>
```

 \* You should be able to call any Web Services API method through the Product Script. However, if you run into difficulties using a particular API method in the Product Script, contact your Adobe Account Manager. For detailed information about Web Services APIs, visit the [Developer Connection](https://marketing.adobe.com/developer/).| The encapsulated product script.\*

 \(See \#1\) A Web Services API method. This example calls a method from the Administration API.

 \(See \#2\) The `replaceWith` attribute instructs Data Connectors to replace the attribute contents with a setting or property from the client’s account. Data Connectors supports the following `replaceWith` values:

 **mapping:** \(See \#2\) Replaces the attribute with the specified attribute mapping. For more information about variable mapping, see [Product.AddVariableMappings](r_prod_addvarmapping.md#).

 **client:** \(See \#3\) Substitutes a client account property when making the call. Supported values include: `RSID` \(insert the Report Suite ID\), `INT_NAME` \(insert the Integration name\), `INT_EMAIL` \(insert the Integration Email\).

 **param:** \(Used only with On Demand scripts\) Inserts a partner-specified parameter when calling [Partner.RunScript](../integration_api/r_runScript.md#).

 For a more detailed product script example, see [Sample Data Connectors Integration](../../code_samples/integration/c_sample_genesis_integration.md#).|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

