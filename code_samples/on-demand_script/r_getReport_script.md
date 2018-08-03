# Report.GetReport Script

Script that downloads report data from a completed report, using the report ID received from the `Report.QueueOvertime` call.

```
<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:omn="http://www.omniture.com/">
   <soapenv:Header/>
   <soapenv:Body>
      <omn:Product.SubmitProductScript soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
         <productCode xsi:type="xsd:string">**PRODUCT_CODE**</productCode>
         <runOn xsi:type="xsd:string">demand</runOn>
         <script xsi:type="xsd:string"><![CDATA[<genesis version="3">
            <Report.GetReport>
               <reportID>{{REPORT_ID}}</reportID>
            </Report.GetReport>
         </genesis>]]></script>
         <scriptDesc xsi:type="xsd:string">First try at Reporting API</scriptDesc>
         <scriptName xsi:type="xsd:string">Get Report</scriptName>
      </omn:Product.SubmitProductScript>
   </soapenv:Body>
</soapenv:Envelope>
```

**Parent topic:** [On-Demand Product Script](../../code_samples/on-demand_script/c_ondemand_product_script.md)

