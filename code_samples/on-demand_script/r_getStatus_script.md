# Report.GetStatus Script

Sample script to check the status of a previously submitted report request using the report ID received from the `Report.QueueOvertime` call.

Once the report status is done, you can download the report data.

```
<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/
soap/envelope/" xmlns:omn="http://www.omniture.com/">
   <soapenv:Header/>
   <soapenv:Body>
      <omn:Product.SubmitProductScript soapenv:encodingStyle="http://
schemas.xmlsoap.org/soap/encoding/">
         <productCode xsi:type="xsd:string">**PRODUCT_CODE**</productCode>
         <runOn xsi:type="xsd:string">demand</runOn>
         <script xsi:type="xsd:string"><![CDATA[<genesis version="3">
            <Report.GetStatus>
               <reportID>{{REPORT_ID}}</reportID>
            </Report.GetStatus>
         </genesis>]]></script>
         <scriptDesc xsi:type="xsd:string">First try at Reporting API</scriptDesc>
         <scriptName xsi:type="xsd:string">Get Status</scriptName>
      </omn:Product.SubmitProductScript>
   </soapenv:Body>
</soapenv:Envelope>
```

**Parent topic:** [On-Demand Product Script](../../code_samples/on-demand_script/c_ondemand_product_script.md)

