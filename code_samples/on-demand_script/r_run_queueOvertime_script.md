# Run the QueueOvertime Script

Sample code that uses `Partner.RunScript` to call the `QueueOvertime` product script.

For more information, see [Report.QueueOvertime Script](r_queueOvertime_script.md#).

```
<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:omn="http://www.omniture.com/" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/">
   <soapenv:Header/>
   <soapenv:Body>
      <omn:Partner.RunScript soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
         <integrationCode xsi:type="xsd:string">**CLIENT_INTEGRATION_CODE**</integrationCode>
         <scriptName xsi:type="xsd:string">Queue Report</scriptName>
         <scriptParameters>
            <scriptParameter>
               <name>myDateTo</name>
               <value>2010-01-31</value>
            </scriptParameter>
         </scriptParameters>
      </omn:Partner.RunScript>
   </soapenv:Body>
</soapenv:Envelope>
```

**Parent topic:** [Sample RunScript Code](../../code_samples/on-demand_script/c_runscript_sample.md)

