# data\_warehouse\_request

|Element|Type|Description|
|-------|----|-----------|
|**status** |`xsd:int` | A code representing the status of the data segment. Supported status values include:<br/> `status == 0: Waiting to Start` <br/> `status == 1: In Progress` <br/> `status == 2: Completed` <br/> `status == 3: On Hold` <br/> `status == 4: Cancelled` <br/> `status == 5: Has Error` <br/> `status == 6: Waiting to Start` <br/> `status == 7: Too Big` <br/> `status == 8: Waiting to Start` <br/> `status == 9: Waiting for Data` <br/> `status == 10: Waiting to Send` <br/> `status == 11: Waiting for Verification` <br/> `status == 12: Waiting to Send` <br/> `status == 13: Sent to Product` <br/> `status == 14: Sending` <br/> `status == 15: Waiting to Continue` <br/> `status == 16: Waiting to Continue` <br/> `status == 17: Continuing` <br/> `status == 18: Not Delivered` |
|**message** |`xsd:string` | A brief description of the status code. The message string for each status code is listed in the description of the `status` parameter.|
|**filesize** |`xsd:string` | Populated only when `status == 2`. The size of the requested data segment, in MB.|
|**data\_url** |`xsd:string` | Populated only when `status == 2`. Contains the REST URL where you can download the completed data segment.<br/> Use the REST URL to download all data segments larger than 10MB. For more information, see [Data Connectors REST Service](../Overview/c_overview_rest.md#).|<br/>

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)
