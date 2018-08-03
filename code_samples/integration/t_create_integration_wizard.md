# To Create a Data Connectors Integration Wizard

1.   Create a working folder for the integration. 

    For the sample Twitter integration, the working folder stores the `config` file, the integration code files, the Data Connectors Partner API WSDL files \(from the Data Connectors Sandbox Welcome Email\).

    **Note:** The sample Twitter integration also creates a subfolder, called `TweetIds`, that contains information about the last `TweetId` used.

2.   Create a `config` file that contains information needed by the integration. 

    The `config` file eliminates the need to provide account credentials each time you run the integration. The file must be named `config`, and should contain the following entries:

    -    `username=YOUR_Data Connectors_API_USERNAME`: Your Data Connectors Partner API username, as provided in the Data Connectors Sandbox Welcome Email.
    -   `password=YOUR_Data Connectors_API_PASSWORD`: Your Data Connectors Partner API password, as provided in the Data Connectors Sandbox Welcome Email.
    -   `workingDir=/path/to/working/dir`: The full path to the integration’s working directory.
    -    `configWSDL=GenesisConfiguration-2.7.wsdl`: The name of the Data Connectors Partner Configuration Web Service file.
    -    `integrationWSDL=GenesisIntegration-2.7.wsdl`: The name of the Data Connectors Partner Integration Web Service.
3.   Run `GetGenesisProducts.php` to call [partner.GetProducts](../../Genesis_API/integration_api/r_getProducts.md#). 

    This call returns information about your existing products. When `GetGenesisProducts` runs, it prompts you to save integration information to the `config` file:

    **`y`:** Select the appropriate product from the product list, and `GetGenesisProducts` copies the product information for the selected product into the `config` file.

    **`n`:** `GetGenesisProducts` displays product information for existing products, but does not copy any information to the `config` file.

4.   Configure the `AddVariableMappings` section of `ConfigureTwitterApp.php` as needed for the integration. 

    To do this, you must identify the application metrics that you want to integrate into the Analytics report suite. For the sample Twitter integration, this includes the following:

    |Application Metric|Variable Type|Desciption|
    |------------------|-------------|----------|
    |`Twitter Search Term` |eVar| Collects data about the Twitter search term for which you want to generate a Analytics report.

 This mapping requires that the assigned eVar has full sub-relations enabled, so Adobe recommends using the Campaign Variable for this purpose.|
    |`Twitter` |eVar| Collects data about the Twitter ID that publishes tweets with the specified search term.

 This mapping requires that the assigned eVar has basic sub-relations enabled.|
    |`Tweets` |Event| A counter of the Tweets that include the specified search term.|
    |`Saved Search Term` |Customval| Stores the Twitter search term value.|

5.   Configure the Product Script section of `ConfigureTwitterApp.php` as needed for the integration. 

    To do this, you must identify the non-Data Connectors API calls that you want to call at the end of the Data Connectors Integration Wizard. The sample Twitter integration requires the following non-Data Connectors API calls:

    -   `ReportSuite.SaveCalculatedMetrics` 
    -   `ReportSuite.SaveClassifications` 
    -   `DataSource.SetupGeneric` 
6.   Configure the `SubmitProductScript` section of `ConfigureTwitterApp.php` as needed for the integration. 

    To do this, you must determine when you want the non-Data Connectors API calls to execute. For more information, see [Product.SubmitProductScript](../../Genesis_API/config_api/r_prod_submitProductScript.md#).

7.   Run `ConfigureTwitterApp.php`. 

    `ConfigureTwitterApp` does the following:

    -   Calls [Product.AddVariableMappings](../../Genesis_API/config_api/r_prod_addvarmapping.md#). The complete AddVariableMappings section of the sample Twitter integration is available at [ConfigureTwitterApp.php](r_configureTwitterApp.md#).
    -   Calls [Product.SubmitProductScript](../../Genesis_API/config_api/r_prod_submitProductScript.md#) to set up any post-installation API calls. The complete Product Script for the sample Twitter integration is available at [ConfigureTwitterApp.php](r_configureTwitterApp.md#).

**Parent topic:** [Implementation](../../code_samples/integration/c_sample_integration_implement.md)

