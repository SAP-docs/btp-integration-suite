<!-- loio45ed5c0321824f26863396174bd32deb -->

# Creating an Exception Response for SOAP-Based Adapters

Understand how to populate the fields in the exception response for SOAP-based adapters via API by populating/overwriting the generated exception.

> ### Note:  
> This topic is related to SOAP-based adapters. This includes the following adapter types:
> 
> -   SOAP SOAP 1.x
> 
> -   SOAP SAP RM
> 
> -   IDoc
> 
> -   XI

If an error is thrown during processing, the user receives a detailed fault description. Overwrite that generated exception with exception responses adapted to the workflow's needs.

The `com.sap.gateway.ip.core.customdev.processor.SoapFaultFactory` class provides the following methods:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

throwSoapFault\(SoapFaultParam param\)

</td>
<td valign="top">

Use this method for SOAP sender channels. It allows the setting of all attributes that the SOAP specification describes, especially the SOAP version. For details, see the SOAP specification. Be aware that there are some differences between SOAP 1.1 and SOAP 1.2. In particular, SOAP 1.2 only allows certain fault codes.

-   @param `param`: Object to set all parameters according to the SOAP specification. The parameter detail is expected to be an Element object of a DOM tree. The parameter namespaces can be used to add additional namespace declarations for parameter detail if required.

-   @throws: `UnknownSoapVersionException`

-   @throws `UnknownFaultCodeException`




</td>
</tr>
<tr>
<td valign="top">

throwSoapFault\(String faultstring, Element detail, Map<String, String\> namespaces\)

</td>
<td valign="top">

Use this method for SOAP sender channels. It provides a minimum set of parameters to only set text parameters. All other parameters are set to their defaults. The SOAP version is set to SOAP 1.1.

-   @param `faultstring`: See also the SOAP specification. This is a simple error text.
-   @param `detail`: See also the SOAP specification. Here you can set additional information. The SOAP fault exception object of the SOAP adapter required here is an Element object of a DOM tree.

-   @param `namespaces`:

    If the detail parameter requires additional namespace declarations, then they can be set here.




</td>
</tr>
<tr>
<td valign="top">

throwXiSoapFault\(XiSoapFaultParam param\)

</td>
<td valign="top">

Use this method for XI sender channels. It throws a SOAP fault exception that fulfills the XI protocol specification. This specification basically restricts the detail attribute of the SOAP fault to a certain format. For the SOAP adapter, this can be freely chosen. In the XI adapter, the detail has to follow the XI error header specification. In addition, the SAP category is always set to 'XIServer' and the SAP code is set to 'INTERNAL.MESSAGE'. All other codes and categories are reserved. P1 to P4, additional text, and stack can be freely chosen.

-   @param `param`: Object to set all possible attributes of an XI SOAP fault.

-   @throws `XMLStreamException`




</td>
</tr>
</table>

Check out the related blog if you want to know how to process SOAP headers in an integration flow. The blog describes a detailed integration flow example using a script step: [Cloud Integration - Accessing and Setting SOAP Headers in an Integration Flow](https://blogs.sap.com/2019/04/08/cloud-integration-accessing-and-setting-soap-headers-in-an-integration-flow/)

**Related Information**  


[Creating Scripts in a Script Collection](creating-scripts-in-a-script-collection-ed9b52c.md "")

[XI Adapter](xi-adapter-8fedc92.md "The XI adapter connects an SAP Cloud Integration tenant to a remote system that can process the XI message protocol.")

