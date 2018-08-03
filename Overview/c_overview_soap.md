# SOAP Service

Simple Object Access Protocol \(SOAP\) is an XML-based protocol for the exchange of information between applications over HTTP. See [http://www.w3.org/TR/soap12-part1/](http://www.w3.org/TR/soap12-part1/) for a more complete review of SOAP-based implementations.

The Suite Web Services, including the Data Connectors Partner API, use a document/literal style version of SOAP \(not rpc/encoded\). Your program sends a SOAP request; Adobe's Web service processes the request and returns a response. Both the request and the response use standard XML messages with a header and a body.

Send SOAP requests \(in XML format\) as an HTTP POST request. It must include a special `SOAPAction` header. Adobe returns the response as a response to your POST. All of these communications are encrypted with SSL \(HTTPS\), thereby helping to protect data privacy.

Important details must be sent in the Header as metadata about your message, including your login email, password and a user agent header identifying the client company. The requested operation \(such as `addAdGroup`\) is included in the message body. The message body also includes all pertinent parameters such as the data objects.

Remember that requests for our Web service to process are defined in a Web services definition language \(WSDL\) file in XML. This WSDL file describes the operations that our Web service can perform, required parameters for each operation, and the expected response for each operation.

-   **[SOAP Development Toolkits](../Overview/c_overview_soap_toolkits.md)**  

-   **[Security](../Overview/c_overview_soap_security.md)**  


**Parent topic:** [Data Connectors Partner API](../Overview/c_genapi_overview.md)

