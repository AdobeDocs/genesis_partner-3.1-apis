# How Data Connectors Works

Data Connectors provides a complete development ecosystem to help Data Connectors partners integrate their products and services into the Adobe Experience Cloud.

Adobe provides a well-defined process for creating a Data Connectors integration.

![](overview.png)

1.  Partner defines the integration using the Configuration API.

    1.  Partner defines variable mappings between their metrics and Analytics variables \(eVars, events, props\).
    2.  Partner defines any internal variables, known as `customvals`, necessary for the integration to work. For example, a username/password, a search term, or an account ID.
    3.  Partner creates the Product Script, which lets the Integration Wizard call use other Web Services API methods that might be helpful to the integration. For example, if the partner wants to create some calculated metrics when the integration completes, they can use the Product Script to call `ReportSuite.SaveCalculatedMetrics`.
    4.  Partner uploads the Partner Product Script.
    **Note:** All Web Services APIs should be accessible through the Product Script. However, if you run into difficulties using a particular API in the Product Script, contact your Account Manager. Information about all the Web Services APIs is available on the [Developer Connection](https://marketing.adobe.com/developer).

2.  Partner finalizes and tests the integration in the Data Connectors Sandbox.
3.  Partner notifies Adobe that the Integration is ready to verify.
4.  Adobe verifies and approves the Integration.
5.  Adobe sends Partner an updated WSDL with an correct endpoint for the production environment.
6.  Adobe enables the Integration in Data Connectors.
7.  Using the Data Connectors Integration API, partner checks on a regular basis for clients that have activated the integration in their Analytics report suite.
8.  After a client activates the partner’s Data Connectors integration, partner uses the Integration API to enable the flow of data between the partner’s product or service and Analytics.

**Parent topic:** [Data Connectors Partner API](../Overview/c_genapi_overview.md)

