# Data Types

The Data Connectors Partner API uses these custom data types.

A custom data type defines a structure for organizing and containing a specific set of data. Additionally, XML defines certain primitive \(common\) data types such as int, string or date. The [XML Schema Definition](http://www.w3.org/TR/xmlschema11-2/) describes these primitive data types.

Adobe uses the following convention to identify a data type related to Experience Cloud web services:

`<namespace>:<type>` 

For example:

-   `xsd:int` identifies a primitive data type that is part of the `xsd` namespace \(XML Schema Definition\), and that the type is `int` \(Integer\).
-   `tns:code_items` identifies a custom data type that is part of the `tns` namespace \(an Adobe private namespace\), and that the type is `code_items`. The `tns` namespace prefixes all custom data types related to the Adobe Experience Cloud.

**REST APIs** 

The existing data type documentation was written for SOAP API, so it has parameter types defined. When using the REST API, there is no need to specify parameter types. Method name should be added to request URL, as described in [REST Service](../Overview/c_overview_rest.md#) section.

-   **[accessRequest](../data_types/r_accessRequest.md)**  
Information about a single access request.
-   **[accessRequests](../data_types/r_accessRequests.md)**  

-   **[adProcessingSettings](../data_types/r_datatype_adProcessingSettings.md)**  

-   **[adProcessingStatus](../data_types/r_datatype_adProcessingStatus.md)**  

-   **[adProcessingVariables](../data_types/r_datatype_adProcessingVariables.md)**  

-   **[Product.authenticationParameter](../data_types/r_datatype_authenticationParameter.md)**  
Contains details on an authentication parameter that is used for partner API authentication.
-   **[chosenAccessRequests](../data_types/r_chosenAccessRequests.md)**  
Chosen access requests selected by the user.
-   **[colArray](../data_types/r_datatype_colArray.md)**  

-   **[data\_warehouse\_report](../data_types/r_datatype_data_warehouse_report.md)**  
Contains a segmented Data Warehouse report.
-   **[data\_warehouse\_request](../data_types/r_datatype_data_warehouse_request.md)**  

-   **[display](../data_types/r_datatype_display.md)**  
Display information for a custom value.
-   **[int\_array](../data_types/r_datatype_int_array.md)**  

-   **[integrationAccess](../data_types/r_datatype_integrationAccess.md)**  

-   **[integrationBrief](../data_types/r_datatype_integrationBriefs.md)**  

-   **[integrationData](../data_types/r_datatype_integrationDatas.md)**  

-   **[integrationDetail](../data_types/r_datatype_integrationDetail.md)**  

-   **[integrationDetails](../data_types/r_datatype_integrationDetails.md)**  

-   **[integrationMapping](../data_types/r_datatype_integrationMapping.md)**  

-   **[integrationValue](../data_types/r_datatype_integrationValue.md)**  

-   **[integrationValues](../data_types/r_datatype_integrationValues.md)**  

-   **[metricClassificationList](../data_types/r_datatype_metricClassificationList.md)**  

-   **[metricClassifications](../data_types/r_datatype_metricClassifications.md)**  

-   **[partner\_sandbox\_credentials](../data_types/r_datatype_partner_sandbox_credentials.md)**  

-   **[product](../data_types/r_datatype_product.md)**  

-   **[productArray](../data_types/r_datatype_productArray.md)**  

-   **[productCalculatedMetric](../data_types/r_datatype_productCalculatedMetric.md)**  

-   **[productCalculatedMetrics](../data_types/r_datatype_productCalculatedMetrics.md)**  

-   **[productClassification](../data_types/r_datatype_productClassification.md)**  

-   **[productClassificationList](../data_types/r_datatype_productClassificationList.md)**  

-   **[productDetails](../data_types/r_datatype_productDetails.md)**  

-   **[productDetailsList](../data_types/r_datatype_productDetailsList.md)**  

-   **[Product.productFaq](../data_types/r_datatype_productFaq.md)**  
Contains a frequently asked question.
-   **[productProcessingRule](../data_types/r_datatype_productProcessingRule.md)**  

-   **[productResource](../data_types/r_datatype_productResource.md)**  

-   **[productResourceContent](../data_types/r_datatype_productResourceContent.md)**  

-   **[productResourceList](../data_types/r_datatype_productResourceList.md)**  

-   **[productResourceType](../data_types/r_datatype_productResourceType_enum.md)**  

-   **[product\_approval\_status\_container](../data_types/r_datatype_product_approval_status_container.md)**  

-   **[product\_info\_container](../data_types/r_datatype_product_info_container.md)**  

-   **[resourceEncoded](../data_types/r_datatype_resourceEncoded.md)**  

-   **[responseArray](../data_types/r_datatype_responseArray.md)**  

-   **[rowArray](../data_types/r_datatype_rowArray.md)**  

-   **[scriptParameter](../data_types/r_datatype_scriptParameter.md)**  

-   **[scriptParameters](../data_types/r_datatype_scriptParameters.md)**  

-   **[status](../data_types/r_datatype_status.md)**  

-   **[string\_array](../data_types/r_datatype_string_array.md)**  

-   **[timeBucket](../data_types/r_datatype_timeBucket.md)**  

-   **[timeBucketList](../data_types/r_datatype_timeBucketList.md)**  

-   **[token\_usage\_container](../data_types/r_datatype_token_usage_container.md)**  

-   **[token\_usage\_array](../data_types/r_datatype_token_usage_array.md)**  

-   **[varMapAll](../data_types/r_datatype_varMapAll.md)**  


**Parent topic:** [Data Connectors Partner API](../Overview/c_genapi_overview.md)

