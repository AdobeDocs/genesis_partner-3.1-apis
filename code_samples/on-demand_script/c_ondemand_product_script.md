# On-Demand Product Script

Generating the sample Analytics report involves the following Web Services API calls. Each of these calls should be uploaded \(using [Product.SubmitProductScript](../../Genesis_API/config_api/r_prod_submitProductScript.md#)\) as a separate on-demand product script. For detailed information about these Web Services API methods, see the Analytics Reporting API on the Developer Connection.

**Note:** The scripts include generic parameter values \(for example: `**PRODUCT_CODE**`\) that you would replace with values appropriate to your integration.

-   **[Report.QueueOvertime Script](../../code_samples/on-demand_script/r_queueOvertime_script.md)**  
Sample script to generate a Analytics Overtime report.
-   **[Report.GetStatus Script](../../code_samples/on-demand_script/r_getStatus_script.md)**  
Sample script to check the status of a previously submitted report request using the report ID received from the `Report.QueueOvertime` call.
-   **[Report.GetReport Script](../../code_samples/on-demand_script/r_getReport_script.md)**  
Script that downloads report data from a completed report, using the report ID received from the `Report.QueueOvertime` call.

**Parent topic:** [Sample On-Demand Script Usage](../../code_samples/on-demand_script/c_sample_ondemand_scripts.md)

