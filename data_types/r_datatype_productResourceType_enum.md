# productResourceType

Data Connectors 3.0: Added `feed` resource type.

An enumerated list of supported resource types:

|Element|Description|
|-------|-----------|
|**link** | A simple URL that redirects the integration client to an external Web page.|
|**static** | A static file, such as a PDF. Data Connectors downloads and includes static resources as Email attachments to an integration’s Welcome Email.<br/> A static resource is identical for all integrations.|
|**dynamic** | Data Connectors includes dynamic resources as Email attachments to an integration’s Welcome Email. A dynamically generated file, typically code such as a JavaScript file. Data Connectors processes dynamic resources, replacing variables in the dynamic template file with values the client specified when activating the integration. This lets you create a single file that Data Connectors dynamically modifies for each client that activates your integration.|
|**feed** | A URL to an RSS or Atom feed. The content of this feed is displayed on the **Tips & Tricks** tab in Data Connectors.<br/> Added in Data Connectors 3.0.|<br/>

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)