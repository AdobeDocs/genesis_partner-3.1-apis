# Run the GetStatus Script

Sample code that uses `Partner.RunScript` to call the `GetStatus` product script.

This script returns the current status of the report request. For more information, see [Report.GetStatus Script](r_getStatus_script.md#).

```
<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:omn="http://www.omniture.com/" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/">
   <soapenv:Header/>
   <soapenv:Body>
      <omn:Partner.RunScript soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
         <integrationCode xsi:type="xsd:string">**CLIENT_INTEGRATION_CODE**</integrationCode>
         <scriptName xsi:type="xsd:string">Report Status</scriptName>
         <scriptParameters>
            <scriptParameter>
               <name>REPORT_ID</name>
               <value>**REPORT_ID**</value>
            </scriptParameter>
         </scriptParameters>
      </omn:Partner.RunScript>
   </soapenv:Body>
</soapenv:Envelope>
```

**Parent topic:** [Sample RunScript Code](../../code_samples/on-demand_script/c_runscript_sample.md)

