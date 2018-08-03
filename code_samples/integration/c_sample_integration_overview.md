# Integration Overview

This sample integration gathers data from Twitter\* so you can see it in Analytics® reports. The Twitter report contains information about tweets that contain a particular keyword. Once installed, you can access the Twitter integration reports in Analytics by selecting **Campaigns** \> **Twitter Search Term** \> **Twitter Search Term**.

The sample Twitter integration includes the following files:

**`config`:** Stores integration information, including Data Connectors Sandbox login credentials and the integration’s working folder. The `config` file eliminates the need to manually provide login information manually when running the integration.

**`GenesisConfiguration-2.7.wsdl`:** The WSDL for the Data Connectors Configuration API.

**`GenesisIntegration-2.7.wsdl`:** The WSDL for the Data Connectors Integration API.

**`GenesisSoapApp.class.php`:** The SOAP class for the Twitter sample integration \(See [GenesisSoapApp.class.php](r_genesisSoapApp_class.md#)\).

**`GetGenesisProducts.php`:** Returns information about all your currently defined products and lets you save the information to the `config` file, as described in Step 1 \(See [GetGenesisIntegrations.php](r_getGenesisIntegrations.md#)\). Once saved to the `config` file, you can use the product information in product-specific calls, such as `AddVariableMappings`.

**`ConfigureTwitterApp.php`:** The Twitter sample integration configuration and Product Script \(See [ConfigureTwitterApp.php](r_configureTwitterApp.md#)\). This code leverages the methods and data types in the Data Connectors Configuration API.

**`GetGenesisIntegrations.php`:** Returns information about all your currently defined integrations and lets you save the information to the `config` file, as described in Step 1 \(See [GetGenesisIntegrations.php](r_getGenesisIntegrations.md#)\). Once saved to the `config` file, you can use the integration information in integration-specific calls, such as `GetDWSegment`.

**`UploadTwitterData.php`:** The Twitter sample integration data exchange with Adobe collection servers. This code leverages the methods and data types in the Data Connectors Integration API.

**`GetDWSegment.php`:** Returns a Data Warehouse segment for the integration specified in the config file \(See [GetDWSegment.php](r_getDWSegment.md#)\).

**Parent topic:** [Sample Data Connectors Integration](../../code_samples/integration/c_sample_genesis_integration.md)

