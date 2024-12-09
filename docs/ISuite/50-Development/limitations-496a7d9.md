<!-- loio496a7d9dcdf347398697317704569c52 -->

# Limitations

Consider the following limitations before uploading a Custom Message/IDoc/SOA.

The following limitation applies to all custom messages:

-   The maximum file size of custom message that you can upload is 10MB, with a maximum limit of 20000 nodes.




<a name="loio496a7d9dcdf347398697317704569c52__section_bbd_rkc_lzb"/>

## Custom Type System - Custom Messages

**XSD Features with limited support**

The following XSD features are currently only supported in a limited way. You can upload your XSD as custom message, but you might not be able to use the full scope of the XSD feature in your MIGs.

**Custom Messages - Limitations**


<table>
<tr>
<th valign="top">

Limitation

</th>
<th valign="top">

Detail

</th>
</tr>
<tr>
<td valign="top">

Only native-XML messages supported

</td>
<td valign="top">

Full support is only given to messages that are natively XML \(all messages are imported with *SyntaxType = XML*.\) You can still import XSDs representing non-XML messages and SAP Integration Suite will support standard XML-handling. But extended special features such as XSD creation for EDI Flow Steps are not supported.

</td>
</tr>
<tr>
<td valign="top">

Recursion \(limited support\)

</td>
<td valign="top">

**Self-recursion** occurs when a child node refers to its parent *complexType*. In such cases, the message will be imported as Custom Message. But this recursive node cannot be used and will be disabled for selection in the MIG.

**Chain recursion** occurs when a child node refers to an ancestor *complexType*. This scenario is not supported and such elements will be removed automatically when imported into the tenant .

</td>
</tr>
</table>

**Unsupported XSD features**

The following XSD features are not supported. If they are present in your XSD, XSD validation will fail and the custom message will not be uploaded. In certain cases you can resolve the situation by manually modifying the XSD before upload.

**Custom Messages - Limitations**


<table>
<tr>
<th valign="top">

Limitation

</th>
<th valign="top">

Detail

</th>
<th valign="top">

Resolution / Workaround

</th>
</tr>
<tr>
<td valign="top">

*xsd:import* not supported

</td>
<td valign="top">

Import of another XSD \(different namespace\) is not supported. This also implies that only one namespace is allowed across the message.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*xsd:include* not supported

</td>
<td valign="top">

Include of another XSD \(same namespace\) is not supported.

</td>
<td valign="top">

Merge all XSD files of the same namespace into one XSD file. \(Basic XSD knowledge required.\)

</td>
</tr>
<tr>
<td valign="top">

No support for schema extension via:

-   xsd:any

-   xsd:anyType




</td>
<td valign="top">

SAP Integration Suite always works on specific message structures and not on generic undeclared nodes. Therefore any generic schema extensions must be replaced by the specifically required elements and attributes before the upload.

</td>
<td valign="top">

Firstly, ensure whether you need any extension of your custom message structure.

If yes, extend your XSD file before the upload: replace the **xsd:any** with element\(s\) you want to use and replace the **xsd:anyType** with the specific type you want to use.

If not, restrict your XSD file before the upload: simply remove the respective elements or attributes from the xsd file.

\(Intermediate XSD knowledge required.\)

</td>
</tr>
<tr>
<td valign="top">

No support for advanced XSD features like:

-   xsd:complexContent

-   mixed content
-   xsd:extension \(of Complex or Simple Types\)
-   xsd:substitutionGroup



</td>
<td valign="top">

 

</td>
<td valign="top">

Some of these missing advanced XSD features can be replaced by semantically equivalent standard XSD features which are supported. It depends a lot on the specific use case to decide if this is possible or not.

\(Advanced XSD knowledge required.\)

</td>
</tr>
</table>



<a name="loio496a7d9dcdf347398697317704569c52__section_dlw_c4c_lzb"/>

## Custom Type System - SOA Messages

**Unsupported WSDL features**

The following WSDL features are not supported. If they are present in your WSDL, it cannot be uploaded. In some cases you can resolve the situation by manually modifying the WSDL before upload.

**Custom SOA - Limitations**


<table>
<tr>
<th valign="top">

Limitation

</th>
<th valign="top">

Detail

</th>
</tr>
<tr>
<td valign="top">

WSDL version 2.0 not supported

</td>
<td valign="top">

SAP Integration Suite works on the predominantly used WSDL version 1.1 \(= WSDL file starting with tag <definitions\>\).

WSDL version 2.0 is not supported \(= WSDL file starting with tag <description\>\).

</td>
</tr>
<tr>
<td valign="top">

Only one *wsdl:part* allowed

</td>
<td valign="top">

A **wsdl:message** can only refer to one **wsdl:part** declaration. A declaration of multiple **wsdl:part** for one **wsdl:message** is not supported.

</td>
</tr>
<tr>
<td valign="top">

Same global element cannott be referenced by multiple messages

</td>
<td valign="top">

All messages within one WSDL file must refer to different global elements and it is not allowed to reuse a global element in multiple messages.

</td>
</tr>
</table>

**XSD features unsupported or with limited support**

For all the XSD Schemas declared within the *wsdl:types* section of your WSDL file, the same restrictions and limitations apply as described in section for *Custom Messages*. The only exception to this is, that multiple XSD Schemas are allowed within one WSDL file and that they are allowed to reference each other via *xsd:import*.



<a name="loio496a7d9dcdf347398697317704569c52__section_jxv_kwc_lzb"/>

## Custom Type System - Custom IDocs

For Custom IDocs, an IDoc-XSD file is expected as it can be downloaded from the SAP S/4HANA System \(transaction WE60\).

In principle the same restrictions and limitations apply as described in section for *Custom Messages*, however, none of the advanced XSD features are used in the IDoc-XSDs.

