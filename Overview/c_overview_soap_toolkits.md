# SOAP Development Toolkits

The easiest way to use the Data Connectors API is with a toolkit that interprets WSDL files and provide a framework for easier development. Development toolkits encode and decode XML request/response messages for you. More specifically, toolkits let you work in an object oriented environment, so you can both create and receive objects that are translated to and from XML by the toolkit.

**Note:** Make sure the SOAP toolkit you select supports, and is configured for, document/literal SOAP.

Choose a SOAP toolkit that matches the programming language you are using. Toolkits vary in performance, capability, and user-friendliness. The commonly used toolkits include:

**PHP:** NuSOAP \([http://sourceforge.net/projects/nusoap/](http://sourceforge.net/projects/nusoap/)\) and Pear \([http://pear.php.net/](http://pear.php.net/)\).

**Java:** Apache Axis \([http://ws.apache.org/axis/](http://ws.apache.org/axis/)\) and Apache WSS4J \([http://ws.apache.org/wss4j/](http://ws.apache.org/wss4j/)\).

**Windows:** .NET SOAP support, and .Net Microsoft Visual Studio .NET \([http://msdn.microsoft.com/en-us/vstudio/default.aspx](http://msdn.microsoft.com/en-us/vstudio/default.aspx)\)

 **Python:** SOAPPy \([http://pywebsvcs.sourceforge.net/](http://pywebsvcs.sourceforge.net/)\)

 **Perl:** SOAP::Lite \([http://www.soaplite.com/](http://www.soaplite.com/)\)

 **SOAPUI** \([www.soapui.org](http://www.soapui.org)\)

 **XMLSPY** \([http://www.altova.com/products/xmlspy/xml\_editor.html](http://www.altova.com/products/xmlspy/xml_editor.html)\)

Some SOAP toolkits take care of the XML coding for you. By using a SOAP toolkit that handles the XML generation, you should rarely have to write XML code to use the Data Connectors Web Service. However, some toolkits might require you to hand-code some of the XML. For example, nusoap.php requires you to write the XML namespace for input parameters.

**Note:** It can sometimes be helpful to capture the XML request and response messages for debugging purposes.

**Parent topic:** [SOAP Service](../Overview/c_overview_soap.md)

