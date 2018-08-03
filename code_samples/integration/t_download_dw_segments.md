# To Download Segmented Data

1.   If necessary, enable Data Warehouse before attempting to download data segments.. 

    Contact your Account Manager or ClientCare to help you with this.

2.   Run `GetDWSegment.php`. 

    This calls the `RequestSegmentedData` and `GetSegmentedData` methods from the Data Warehouse API. [GetGenesisIntegrations.php](r_getGenesisIntegrations.md#) returns the Data Warehouse segment names for each integration. If you stored the integration information in the `config` file, [GetDWSegment.php](r_getDWSegment.md#) retrieves this information automatically. For more information about Data Warehouse API methods, see the Data Warehouse API.


**Parent topic:** [Implementation](../../code_samples/integration/c_sample_integration_implement.md)

