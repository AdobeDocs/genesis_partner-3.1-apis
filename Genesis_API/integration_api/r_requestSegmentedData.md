# Export.RequestSegmentedData

Submits a Data Warehouse request to return data to the Data Connectors partner.

## Export.RequestSegmentedData Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | Yes| The identifier of the integration for which you want to request an export. Call [Partner.GetIntegrations](r_getIntegrations.md#) to get this value.|
|**breakdownNames** |[string\_array](../../data_types/r_datatype_string_array.md#) | Yes| The breakdowns to include in the Data Warehouse request. The breakdown must be the name of a variable mapping defined in the Data Connectors integration \(See [Product.GetVariableMappings](../config_api/r_prod_getVarMappings.md#)\).

 A valid request must contain at least one Metric or Breakdown.|
|**metricNames** |[string\_array](../../data_types/r_datatype_string_array.md#) | Yes| The metrics to include in the Data Warehouse request. The metric must be the name of a variable mapping defined in the Data Connectors integration \(See [Product.GetVariableMappings](../config_api/r_prod_getVarMappings.md#)\).

 A valid request must contain at least one Metric or Breakdown.|
|**segmentName** |`xsd:string` | Yes| The segment to use with this Data Warehouse request. Use [Partner.GetIntegrations](r_getIntegrations.md#) to get a list of valid segment names.|
|**dateGranularity** |`xsd:string` | Yes| The granularity of the Data Warehouse request. Supported values include the following: `none`, `hour`, `day`, `week`, `month`, `quarter`, `year`.|
|**dateType** |`xsd:string` | Yes| The type of date range used with the Data Warehouse request. Supported values include:

 **range:** Specifies that you want to use a custom date range. To do this, specify the report's start date using the `dateFrom` parameter, and the end using the `dateTo` parameter.

 **preset:** Specifies that you want to use a predefined date range. To do this, specify the report's preset date using the `datePreset` parameter.|
|**datePreset** |`xsd:string` | No| The predefined date range to use with the Data Warehouse request. Specify this parameter when `dateType = preset`.

 Supported values include the following \(values are case-sensitive\): `Last month`, `Last week`, `Last 2 weeks`, `Last 4 weeks`, `Last 7 days`, `Last 30 days`, `This month`, `This week`, `Today`, `Yesterday`.|
|**dateFrom** |`xsd:string` | No| The start date of the custom date range for the Data Warehouse request. Specify this parameter when `dateType = range`.

 Date values must use the format `MM/DD/YY`.|
|**dateTo** |`xsd:string` | No| The end date of the custom date range for the Data Warehouse request. Specify this parameter when `dateType = range`.

 Date values must use the format `MM/DD/YY`.|

## Export.RequestSegmentedData Response

|Response|Type|Description|
|--------|----|-----------|
|**requestId** |`xsd:int` | A unique identifier for the requested data segment.|
|**status** |`xsd:string` | Indicates if the call was successful. Valid return values include `Failed` or `Success`.

 If the call fails, Data Connectors returns an error message to help you understand why the call failed.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

