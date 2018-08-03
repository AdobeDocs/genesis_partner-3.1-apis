# varMapAll

Includes the variable mapping XML that defines the mappings between partner metrics and Analytics variables \(eVars, events, and props\). The XML for this purpose uses the following structure and tags:

```
<variableMappings>
   <item>
      <metric></metric>
      <friendly_name></friendly_name>
      <om_variable></om_variable>
      <type_flag>
         <item></item>
            ...
         <item></item>
      </type_flag>
      <description></description>
      <required>yes</required>
      <access></access>
   </item>
   <item>
      ...
   </item>
</variableMappings>
```

|Element|Type|Required|Description|
|-------|----|--------|-----------|
|**variableMappings** |`N/A` | Yes| The root tag for all variable mappings.|
|**item** |`N/A` | Yes| Contains a single variable mapping. You can map multiple partner metrics by using multiple `<item>` tags.|
|**metric** |`xsd:string` | Yes| The partner’s metric name.|
|**friendly\_name** |`xsd:string` | No| A more easily understood name for the mapped variable.|
|**om\_variable** |`xsd:string` | Conditional| The type of Analytics variable used in the mapping \(supported values include evar, event, or prop\).<br/> **Note:** The `om_variable` tag is required for adding and modifying variable mappings, but is not required for deleting variable mappings.|
|**description** |`xsd:string` | No| A description of the variable mapping \(255 character max.\)|
|**required** |`xsd:string` | No| Indicates if this mapping is required \(supported values include yes and no\).|
|**access** |`xsd:string` | Conditional| Indicates whether you can import data to, or export data from, the variable. Supported values include `import`, `export`, and `import/export`.<br/> **Note:** The `access` tag is required for adding and modifying variable mappings, but is not required for deleting variable mappings.|
|**display** |[display](r_datatype_display.md#) | Conditional| Specifies the display type and values of the custom value. Added in Data Connectors 3.1.|
|**type\_flag** |`xsd:string` | No| The variable subcategory for this partner metric. Enclose each variable subcategory in an `<item>` tag.<br/> Use `type_flag` to restrict the list of variables \(evars or events\) that users can select from when configuring the product integration through the Data Connectors Integration Wizard. If you do not specify `type_flag`, the Integration Wizard lets users select from the full list of currently defined variables of that type \(evar, event, or prop\).<br/> Each `<om_variable>` value \(evar, event, prop\) has a specific set of `type_flag` options:<br/> **evar:** `campaign`, `merchandising`, or `custom`.<br/> **event:** `custom`, `standard`, `counter`, `counter_nosub`, `currency`, `currency_nosub`, `numeric`, or `numeric_nosub`.<br/> **Note:** To import the metric using [Import.UploadMetrics](../Genesis_API/integration_api/r_uploadMetrics.md#), an event must be of type `Currency` or `Numeric`.<br/> **prop:** Not Applicable. No `type_flag` needed.<br/> **customval:** Not Applicable. No `type_flag` needed.<br/> **Note:** Customval is used only to store internal integration variables. These values are not available to, or used in, Analytics.<br/> You can specify multiple options in a single `type_flag`. For example, the following `type_flag` definition restricts the variable list to events of type `Custom` and `Numeric`:<br/> ```
<type_flag>
   <item>custom</item>
   <item>numeric</item>
<type_flag>
```|

Added in Data Connectors 3.0.
**Parent topic:** [Data Types](../data_types/c_genesis_api_datatypes.md)