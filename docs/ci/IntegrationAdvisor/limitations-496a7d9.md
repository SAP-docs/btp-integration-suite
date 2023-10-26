<!-- loio496a7d9dcdf347398697317704569c52 -->

# Limitations

Consider the following limitations before you upload a custom message:


<table>
<tr>
<th valign="top">

DescriptionLimitation

</th>
<th valign="top">

 

</th>
</tr>
<tr>
<td valign="top">

Only native-XML messages supported

</td>
<td valign="top">

Full support is only given to messages that are natively XML \(All messages are imported with SyntaxType = XML.\) You can also import XSDs representing non-XML messages and SAP Integration Advisor will support standard XML-handling. But extended special features like XSD creation for EDI Flow Steps are not supported.

</td>
</tr>
<tr>
<td valign="top">

Qualification of elements and attributes of the message is not supported

</td>
<td valign="top">

*elementFormDefault* or *form* attribute must be set to *unqualified*.

</td>
</tr>
<tr>
<td valign="top">

*xsd:include* and *xsd:import* are not supported

</td>
<td valign="top">

Import \(or reference\) of another XSD is not supported. This also implies that only one namespace is allowed across the message.

</td>
</tr>
<tr>
<td valign="top">

*@ref* is not supported

</td>
<td valign="top">

Referencing another element/attribute/group/attributeGroup is not possible. The SAP Integration Advisor will throw a validation exception.

</td>
</tr>
<tr>
<td valign="top">

No support for :

-   xsd:any

-   xsd:anyType
-   xsd:group
-   xsd:attributeGroup
-   Global xsd:attribute
-   xsd:complexContent



</td>
<td valign="top">

The SAP Integration Advisor will throw a validation exception.

</td>
</tr>
<tr>
<td valign="top">

Recursion \(limited support\)

</td>
<td valign="top">

**Self-recursion** occurs when a child node refers to its parent *complexType*. In such cases, the message will be imported as Custom Message. But this recursive node can not be used and will be disabled for selection in the MIG.

**Chain recursion** occurs when a child node refers to an ancestor *complexType*. This scenario is not supported and such elements will be removed automatically when imported into the SAP Integration Advisor .

</td>
</tr>
</table>

