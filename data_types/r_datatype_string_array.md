# string\_array

An array of `xsd:string`. The `string_array` XML has a consistent structure:

```
<parameterType>
   <item> </item>
   <item> </item>
   ...
</parameterType>
```

|Element|Type|Description|
|-------|----|-----------|
|**parameterType** |`N/A` | The root tag that identifies the type of parameter for which the `string_array` contains values. Possible values for `parameterType` include: `variableMappings`, `metricNames`, and `breakdownNames`.<br/> Each `variableMappings` tag can contain multiple `<item>` tags.|
|**item** |`xsd:string` | An individual item in the string array.|<br/>

**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)