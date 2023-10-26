<!-- loio9331745d24ae4aa3b3a2bf137f7815b3 -->

# Dynamically Reading XSD Files from the Partner Directory

You can configure the XML Validator step in an integration flow to dynamically read XML schema \(XSD\) files from the Partner Directory. The XML Validator step will then point to an XSD file in the Partner Directory.

To do this, in the XML Validator step, specify the name of a header that points to the XSD file in the Partner Directory.

In the *XML Schema* field, enter the Camel simple expression for the header that should point to the corresponding Partner Directory entity.

In order for the scenario to work, there must be an additional integration flow step \(either a Script step or a Content Modifier step\) that sets the header so that the XML Validator step can refer to it.

In the additional step, the header must be specified as a URI in the following format:

`pd:<Partner ID>:<Parameter ID>:Binary`

This URI specifies a `Binary Parameter` from the Partner Directory. At runtime, the XSLT Engine resolves this URI.

> ### Note:  
> XSL documents that are stored in the Partner Directory can be referenced in other XSL and XML mappings by specifying it in the Partner Directory URI \(using the xsl:import or "document" feature\).
> 
> For detailed information, check out the [blog post](https://blogs.sap.com/2017/08/22/cloud-integration-partner-directory-partner-dependent-xml-structures-and-ids/) about partner dependent XML structures and IDs.



<a name="loio9331745d24ae4aa3b3a2bf137f7815b3__section_gy3_ddb_r1b"/>

## Example

The integration flow contains a Content Modifier step followed by an XML Validator step. You can configure both steps so that an XSD file is dynamically read from the Partner Directory.

In the *XML Validator* step, enter the following simple expression as the *XML Schema*: `${header.XSD_FROM_PD}`.

`XSD_FROM_PD` is the name of the header, which must be filled in a previous step \(in our example, a Content Modifier\).

In the *Content Modifier* step, specify the following settings \(under *Message Header*\):

****


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Specify With the Following Entry ...

</th>
</tr>
<tr>
<td valign="top">

*Name* 

</td>
<td valign="top">

Enter `XSD_FROM_PD`.

</td>
</tr>
<tr>
<td valign="top">

*Type* 

</td>
<td valign="top">

Select *Expression*.

</td>
</tr>
<tr>
<td valign="top">

*Data Type* 

</td>
<td valign="top">

Enter `java.lang.string`.

</td>
</tr>
<tr>
<td valign="top">

*Value* 

</td>
<td valign="top">

Enter `pd:${property.SENDER}:xsd:Binary`.

The expression `${property.SENDER}` makes sure that the Partner ID is dynamically read from the Partner Directory, the entry `xsd` is the name of the parameter for the XSD file in the Partner Directory, and the expression `Binary` classifies it as a binary parameter.

</td>
</tr>
</table>

