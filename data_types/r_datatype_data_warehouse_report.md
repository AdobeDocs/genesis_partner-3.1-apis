# data\_warehouse\_report

Contains a segmented Data Warehouse report.

|Element|Type|Description|
|-------|----|-----------|
|**start\_row** |`xsd:int` | The first data row to include in the report. This value should always be `1`.|
|**end\_row** |`xsd:int` | The last data row to include in the report. This value should always equal the number of elements in `rows`.|
|**finished** |`xsd:boolean` | Indicates that additional data is available \(a paged report\). This value is not currently enabled. It always returns `True`.|
|**headings** |`string_array` | An array of column headings for this report.|
|**rows** |`string_array` | An array of data rows for this report.|

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)

