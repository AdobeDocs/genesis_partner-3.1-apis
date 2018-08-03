# Product.GetVariableMappings

Gets the variable mappings for the specified product.

## Product.GetVariableMappings Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|**productCode** |`xsd:string` | Yes| A valid Data Connectors product code. You can get a list of your company's product codes by calling [``](../integration_api/r_getProducts.md#).|
|**filter** |`xsd:string`\)| No| An expression-like string that limits the variable mapping info returned. The format for the filter string is as follows:

 ```
<Variable1> <Operator1> <Constant1>[,
<Variable2> <Operator2> <Constant2>[,
...]]
```

 **Variable:** One of the tags supported by the [tns:varMapAll](../../data_types/r_datatype_varMapAll.md#) data type.

 **Operator:** A boolean operator \(<, <=, =, \>, \>=, or !=\).

 **Constant:** The filter value. Constant is either a string expression or a numeric value. For example, the following filter returns all variable mappings of type `evar`.

 `om_variable == evar` 

 The following filter returns variable mappings where metric is “Clicks”:

 `metric == Clicks` |

## Product.GetVariableMappings Response

|Parameter|Type|Description|
|---------|----|-----------|
|**variableMappings** |array\([varMapAll](../../data_types/r_datatype_varMapAll.md#)\)| XML that defines the variable mappings.|

**Parent topic:** [Data Connectors Configuration API](../../Genesis_API/config_api/c_genesis_api_config.md)

