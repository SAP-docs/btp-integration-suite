<!-- loio65c70da30831464a9e7c72a050681d1f -->

# Setting and Getting SOAP Headers

Understand how SOAP headers can be accessed, set, and read through an API.

A SOAP message consists of SOAP headers and a SOAP body. SOAP Headers need to be accessed by an API for further processing.

**SOAP Header Attributes**

The attributes that can be used in the SOAP header are conform to the SOAP specifications. You can set two attributes for the SOAP header:

-   **MustUnderstand** defines whether the header needs to be processed by the recipient or not. If the value is set to |true|, the processing of the header becomes mandatory and you need to specify the header in the WSDL file. Otherwise, the header will be rejected. If the value is set to |false|, the header does not have to be processed.

-   **Actor** defines who of the processors has to react to the message. It can be used for your own purposes as it is not used at runtime. If you specify more than one actor, it is possible to route the message to multiple recipients with only the specific information that is relevant to each of the recipient.


**How to Set and Get SOAP Headers**

There are three methods which can be used to process SOAP headers:

-   **GetSoapHeaders**: returns a list \(ArrayList\) of SOAP headers represented by objects of type SOAPHeader.

-   **SetSoapHeaders**: sets SOAP headers in a request or response message before the message is sent out. This method can be used in an integration flow as often as reuqired.

-   **ClearSoapHeaders**: removes headers that were received, so that they won't be propagated.


You can create a SOAP header instance using a DOM tree element or a Java string class instance.

Check out the related blog if you want to know how to process SOAP headers in an integration flow. The blog describes a detailed integration flow example using a script step: [Cloud Integration - Accessing and Setting SOAP Headers in an Integration Flow](https://blogs.sap.com/2019/04/08/cloud-integration-accessing-and-setting-soap-headers-in-an-integration-flow/)

