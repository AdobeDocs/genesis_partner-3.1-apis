# adProcessingSettings

|Element|Type|Description|
|-------|----|-----------|
|**variable** |`xsd:string` | The name of the variable mapping that contains the incoming data string.<br/> If not specified, Data Connectors uses the value from the `variables.viewsVariable` parameter.|
|**delimiters** |`xsd:string` | The default value is `:=`.<br/> A list of the delimiters used to indicate new tokens in the incoming data string.|
|**tokenCount** |`xsd:int` | The default value is `9`.<br/> The total number of tokens in the incoming data string.|
|**format** |`xsd:string` | The default value is `:` \(colon\).<br/> The string indicating the delimiter used when building the outgoing strings.|
|**clickToken** |`xsd:int` | The default value is `6`.<br/> A number indicating the token that contains the click information.|
|**clickSeconds** |`xsd:int` | The default value is `300`.<br/> The number of seconds after which a click is no longer counted.|
|**clickFormat** |`xsd:string` | The default value is `:$7:$8:$9`.<br/> A string used to build the outgoing click data. It contains a template string that indicates the tokens used and the delimiters separating them. This data is appended to the prefix to create the full click string.|
|**viewToken** |`xsd:int` | The default value is `2`.<br/> A number indicating the token that contains the view information.|
|**viewSeconds** |`xsd:int` | The default value is `2592000` \(30 days\).<br/> The number of seconds after which a view is no longer counted.|
|**viewFormat** |`xsd:string` | The default value is `:$3:$4:$5`.<br/> A string used to build the outgoing view data. It contains a template string that indicates the tokens used and the delimiters separating them. This data is appended to the prefix to create the full view string.|
|**timeBucketFormat** |`timeBucketList` | A list that contains the timebucket intervals used for the time bucket metric.|

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)