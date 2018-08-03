# To Upload Data to Analytics

1.   Run `GetGenesisIntegrations.php` to call [partner.GetIntegrations](../../Genesis_API/integration_api/r_getIntegrations.md#). 

    This call returns information about your active integrations. When `GetGenesisIntegrations` runs, it prompts you to save integration information to the `config` file:

    **`y`:** Select the appropriate integration from a list of active integrations. `GetGenesisIntegrations` copies the integration information for the selected integration into the `integrationCode` parameter of the `config` file. The Data Connectors integration uses this information when uploading data to Analytics.

    **`n`:** `GetGenesisIntegrations` displays integration information for all active integrations, but does not copy any information to the `config` file.

    **Note:** Exclude the `integrationCode` parameter from the `config` file to upload data for ALL configured integrations.

2.   Run `UploadTwitterData.php`. 

    `UploadTwitterData` does the following:

    -   Calls the Twitter Search API using the Saved Search Term value to gather information about Tweets that contain the search term. To keep the data in Analytics current, call the Twitter Search API regularly. For example, every 60 minutes. For information about the Twitter Search API, visit the Twitter API Documentation Web site. The code for the Twitter search call for the Twitter integration is available at [UploadTwitterData.php](r_uploadTwitterData.md#).
    -   Stores the tweet id in a file for use in the next Twitter call. This prevents downloading data from the same tweets multiple times. The tweet id contains the ID of the last tweet included in the current Twitter search, so you can use it as a starting point for the next search. The code for storing and retrieving the tweet id in the Twitter integration is available at [UploadTwitterData.php](r_uploadTwitterData.md#).
    -   Calls [Import.UploadMetrics](../../Genesis_API/integration_api/r_uploadMetrics.md#). This call uploads the Twitter search data to Analytics. The code for the data transfer in the Twitter integration is available at [UploadTwitterData.php](r_uploadTwitterData.md#).
    -   Calls [Import.UploadClassifications](../../Genesis_API/integration_api/r_uploadClassifications.md#). This call submits SAINT classification data for the integration.

**Parent topic:** [Implementation](../../code_samples/integration/c_sample_integration_implement.md)

