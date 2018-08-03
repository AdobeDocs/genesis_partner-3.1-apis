# Data Connectors Integration API

The Integration API enables the day-to-day data transfer between the partner environment and Adobe data collection servers.

The Integration API includes the following methods:

-   **[Partner.GetProduct](../../Genesis_API/integration_api/r_getProduct.md)**  
Get the product for the given partner.
-   **[Partner.GetProducts](../../Genesis_API/integration_api/r_getProducts.md)**  
Returns information about each product associated with the current Data Connectors partner.
-   **[Partner.GetIntegrationAccess](../../Genesis_API/integration_api/r_getIntegrationAccess.md)**  
Lets a partner see what data a customer has granted access to in the integration.
-   **[Partner.GetIntegrationMappings](../../Genesis_API/integration_api/r_GetIntegrationMappings.md)**  
Retrieves the mappings and access chosen by the user for an Integration.
-   **[Partner.GetIntegrations](../../Genesis_API/integration_api/r_getIntegrations.md)**  
Returns details about active Data Connectors integrations.
-   **[Partner.GetIntegrationsBrief](../../Genesis_API/integration_api/r_getIntegrationsBrief.md)**  
Returns brief information about a partner's active Data Connectors integrations.
-   **[Partner.GetIntegrationsDetail](../../Genesis_API/integration_api/r_getIntegrationsDetail.md)**  
Returns information about a partner's active Data Connectors integrations.
-   **[Partner.GetSandboxCredentials](../../Genesis_API/integration_api/r_getSandboxCredentials.md)**  
Returns the login information a partner needs to access their Data Connectors sandbox environment.
-   **[Partner.GetTokenUsage](../../Genesis_API/integration_api/r_getTokenUsage.md)**  
Returns the sandbox token usage details for the authenticated partner.
-   **[Partner.RunScript](../../Genesis_API/integration_api/r_runScript.md)**  
Runs an on-demand script against a client’s account during an integration.
-   **[Import.UploadMetrics](../../Genesis_API/integration_api/r_uploadMetrics.md)**  
Submits the first data block in the Data Connectors data submission.
-   **[Import.CheckMetricsUpload](../../Genesis_API/integration_api/r_CheckMetricsUpload.md)**  
Checks a Data Connectors data submission.
-   **[Import.ContinueMetricsUpload](../../Genesis_API/integration_api/r_ContinueMetricsUpload.md)**  
Appends an additional data block to an existing Data Connectors data submission.
-   **[Import.UploadClassifications](../../Genesis_API/integration_api/r_uploadClassifications.md)**  
Submits SAINT classification data for a Data Connectors integration on behalf of a client.
-   **[Import.CheckClassificationsUpload](../../Genesis_API/integration_api/r_CheckClassificationsUpload.md)**  
Checks submitted SAINT classification data for a Data Connectors integration.
-   **[Import.ContinueClassificationsUpload](../../Genesis_API/integration_api/r_continueClassificationsUpload.md)**  
Appends an additional data block to an existing Data Connectors classifications submission.
-   **[Export.RequestClassificationData](../../Genesis_API/integration_api/r_RequestClassificationData.md)**  
 Retrieves classification data from SAINT.
-   **[Export.CheckClassificationRequest](../../Genesis_API/integration_api/r_CheckClassificationRequest.md)**  
Determines if a requested classification from Export.RequestClassificationData is ready to be acquired by Export.GetClassificationData or downloaded by REST URL.
-   **[Export.GetClassificationData](../../Genesis_API/integration_api/r_GetClassificationData.md)**  
 Retrieves classification data for a Data Connectors partner which was requested previously from Export.RequestClassificationData.
-   **[Export.RequestSegmentedData](../../Genesis_API/integration_api/r_requestSegmentedData.md)**  
Submits a Data Warehouse request to return data to the Data Connectors partner.
-   **[Export.CheckDataRequest](../../Genesis_API/integration_api/r_checkDataRequest.md)**  
Returns the status of a previously requested data segment.
-   **[Export.GetSegmentedData](../../Genesis_API/integration_api/r_getSegmentedData.md)**  
Downloads previously requested segment data.
-   **[Export.ProduceResource](../../Genesis_API/integration_api/r_produceResource.md)**  
Produces a dynamic resource for the specified integration.

**Parent topic:** [Methods](../../Genesis_API/c_genesis_api.md)

