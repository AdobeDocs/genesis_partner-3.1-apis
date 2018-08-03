# Product.authenticationParameter

Contains details on an authentication parameter that is used for partner API authentication.

|Element|Type|Description|
|-------|----|-----------|
| **type** | `xsd:string` | Can be `input`, `static`, `array_key` 

 Input indicates a value that the user needs to provide at authentication time. Static is a persistent value that is used every time for authentication. Array key|
| **location** | `xsd:string` | Location of the authentication parameter. Values can be header, argument, both. Consult the partner API to determine where authentication information should be located.|
| **name** | `xsd:string` | Name that the partner is expecting for the authentication parameter.

 If the type is `array_key`, this value is an array that contains the name:value pairs.

 Some WSDLs require multi-dimensional arrays, similar to the following:

 ```
Array('username' => xxxx,
	'password' => xxx)
	
Array(parameters => Array('username' => xxxx,
	'password' => xxx)

```|
| **value** | `xsd:string` | Contains the authentication password if type is static, otherwise value is not used.|
| **label** | `xsd:string` | Friendly name of the parameter and a brief description of the information expected from the user. This string is displayed in the configuration Wizard.|
| **p\_order** | `xsd:int` | Order in which you want the parameters sent. If 1 is specified, the parameters are sent in the order provided. If 0 is specified, it indicates that parameter order doesn't matter to the partner API.|

The following contains an example of an authentication parameter:

```
<parameterList xsi:type="SOAP-ENC:Array">
            <prodAuthParam>
               <type>input</type>
               <location>both</location>
               <name>UserName</name>
               <value/>
               <label>Username</label>
               <p_order>0</p_order>
            </prodAuthParam>
            <prodAuthParam>
               <type>input</type>
               <location>both</location>
               <name>Password</name>
               <value/>
               <label>Password</label>
               <p_order>0</p_order>
            </prodAuthParam>
            <prodAuthParam>
               <type>input</type>
               <location>argument</location>
               <name>AdvertiserID</name>
               <value/>
               <label>Advertiser ID</label>
               <p_order>0</p_order>
            </prodAuthParam>
            <prodAuthParam>
               <type>input</type>
               <location>argument</location>
               <name>ConversionTagID</name>
               <value/>
               <label>Conversion Tag ID</label>
               <p_order>0</p_order>
            </prodAuthParam>
            <prodAuthParam>
               <type>array_key</type>
               <location>argument</location>
               <name>parameters</name>
               <value/>
               <label></label>
               <p_order>0</p_order>
            </prodAuthParam>
         </parameterList>

```

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)

