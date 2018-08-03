# Methods

The Data Connectors Partner API lets you import data from third-party applications and services into Analytics, where you can gather and analyze data in a central location.

When a Analytics client uses a Data Connectors-enabled product or service, they can configure an integration between Analytics and the product or service that imports data into Analytics. Once integrated, they can generate Analytics reports that include data from the Data Connectors application.

The Data Connectors API methods are organized into two separate Web Services that correspond to the phase of the integration process where those methods are used.

**REST APIs** 

The existing method documentation was written for SOAP API, so it has parameter types defined. When using the REST API, there is no need to specify parameter types. Method name should be added to request URL, as described in [REST Service](../Overview/c_overview_rest.md#) section.

**Note:** For a list of supported values for many of the parameters used in the Data Connectors API methods, see [Data Connectors Standard Elements](../standard_elements/r_standard_elements.md#).

-   **[Data Connectors Configuration API](../Genesis_API/config_api/c_genesis_api_config.md)**  
The Configuration API lets Data Connectors partners define an integration’s characteristics, including the data that the partner wants to share with Analytics.
-   **[Data Connectors Integration API](../Genesis_API/integration_api/c_genesis_api_integrate.md)**  
The Integration API enables the day-to-day data transfer between the partner environment and Adobe data collection servers.

**Parent topic:** [Data Connectors Partner API](../Overview/c_genapi_overview.md)

