# Export.RequestClassificationData

Retrieves classification data from SAINT.

## Export.RequestClassificationData Parameters

After creating an export job, use [Export.CheckClassificationRequest](r_CheckClassificationRequest.md#) to determine when the export data is ready for download. Export data files can be very large. Use [Export.GetClassificationData](r_GetClassificationData.md#) to download the file in pieces \(segments\).

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**integrationCode** |`xsd:string` | Yes| The partner product for which you want to retrieve classification data.|
|**campaign\_filter\_begin\_range** |`xsd:string` | No| The campaign start date. Include this parameter when `campaign_filter_option = 2`.

 Specify the date range using the following format:`<start_date>-<end_date>`. Provide the date in the following format: `YYYMMDD`, where:

 `YYY + 1900` equals the year \(For example, 2008 is `108`\).

 `MM` equals the month number minus 1 \(January = 00, February = 01, and so on\).

 `DD` equals the 2 digit day.

 For example, May 22, 2008 is `1080422`.|
|**campaign\_filter\_end\_range** |`xsd:string` | No| The campaign end date. Include this parameter when `campaign_filter_option = 2`.

 Use the same date range format described for the `campaign_filter_begin_range` parameter.|
|**campaign\_filter\_option** |`xsd:int` | No| The filter option to use for the SAINT export. Supported values include:

 `0` : Return all Campaigns \(No filter\)

  `1` : \(Default\) Return active campaigns

 `2` : Return campaigns with the specified begin and end date.|
|**date\_filter\_row\_start\_date** |`xsd:string` | No| The start date for including rows in the export. Include this parameter when `campaign_filter_option = 1`.

 Specify the date using the following format: `Mmm YYYY`, where:

 `Mmm`: A three-character month code. For example, January=Jan, February=Feb, and so on.

 `YYYY`: The 4-digit year.

 For example, September, 2008 is `Sep 2008`.|
|**date\_filter\_row\_end\_date** |`xsd:string` | No| The end date for including rows in the export. Include this parameter when `campaign_filter_option = 1`.

 Use the same date range format described for the `date_filter_row_start_date` parameter.|
|**email\_address** |`xsd:string` | Yes| The email address to receive job notifications.|
|**relation\_id** |`xsd:int` | Yes| The relation ID.

 You get this ID as a return value from `Saint.GetCompatibilityMetrics```.

 For example, `53` is the ID for the "campaign" relation.|
|**row\_match\_filter\_empty\_column\_name** |`xsd:string` | No| \(Optional\) The column ID number of the column that SAINT checks for empty data cells.

 If this parameter is specified, the export contains only keys which have empty values for the provided column.

 You get the column ID by calling`Saint.GetFilters` for a specific relation id.|
|**row\_match\_filter\_match\_column\_name** |`xsd:string` | No| \(Optional\) The column name that SAINT checks for cell values that match the value specified in the `row_match_filter_match_column_value` parameter.

 If the cell value matches the value, SAINT excludes it from the export.|
|**row\_match\_filter\_match\_column\_value** |`xsd:string` | No| \(Optional\) The value that SAINT uses to exclude a data row from the export.

 Include this parameter when using `row_match_filter_match_column_name`.|
|**select\_all\_rows** |`xsd:int` | Yes| Specifies whether to include all data rows in the export \(up to the 50,000 row limit\). Supported values include:

 `0`: Do not include all rows in the export.

 `1`: \(Default\) Include all rows in the export.|
|**select\_number\_of\_rows** |`xsd:int` | No| \(Optional\) Limits the number of data rows in the export file to the specified value. The default limit is 50,000.

 Include this parameter when `select_all_rows = 0`.|

## Export.RequestClassificationData Response

|Name|Type|Description|
|----|----|-----------|
|**requestID** |`xsd:int` | The request ID associated with your export request.|

**Parent topic:** [Data Connectors Integration API](../../Genesis_API/integration_api/c_genesis_api_integrate.md)

