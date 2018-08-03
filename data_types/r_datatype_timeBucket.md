# timeBucket

|Element|Type|Description|
|-------|----|-----------|
|**seconds** |`xsd:int` | The number of seconds where this bucket starts \(the bucket ends at one second less than the start time of the next bucket\)|
|**name** |`xsd:string` | The name of the time bucket.<br/> The default time bucket names, and the number of seconds at which each time bucket starts, are:<br/> **0-5 minutes:** 0 seconds<br/> **5-30 minutes:** 300 seconds<br/> **30-60 minutes:** 1800 seconds<br/> **1-3 hours:** 3600 seconds<br/> **3-6 hours:** 10800 seconds<br/> **6-12 hours:** 21600 seconds<br/> **12-24 hours:** 43200 seconds<br/> **1-2 days:** 86400 seconds<br/> **2-5 days:** 172800 seconds<br/> **5-10 days:** 432000 seconds<br/> **10-20 days:** 864000 seconds<br/> **20+ days:** 1728000 seconds|<br/>

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)