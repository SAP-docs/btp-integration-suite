<!-- loio66a551a6368a4ecab65902e75643152e -->

# Dynamically Reading XSLT Mappings from the Partner Directory

You can configure the XSLT Mapping step in an integration flow to dynamically read XSLT mappings from the Partner Directory. The Mapping step will then point to an XSLT mapping defined in the Partner Directory.

To do this, in the XSLT Mapping step, specify the name of a header that points to the XSLT mapping in the Partner Directory.

Select *Header* as the *Source* in the XSLT Mapping step.

In order for the scenario to work, there must be an additional integration flow step \(either a Script step or a Content Modifier step\) that sets the header so that the XSLT Mapping step can refer to it.

In this additional step, the header must be specified as a URI in the following format:

`pd:<Partner ID>:<Parameter ID>:Binary`

This URI specifies a `Binary Parameter` from the Partner Directory. At runtime, the XSLT Engine resolves this URI.

> ### Note:  
> XSL documents that are stored in the Partner Directory can be referenced in other XSL and XML mappings by specifying it in the Partner Directory URI \(using the xsl:import or "document" feature\).
> 
> For detailed information, check out the [blog post](https://blogs.sap.com/2017/08/22/cloud-integration-partner-directory-partner-dependent-xml-structures-and-ids/) about partner dependent XML structures and IDs.



<a name="loio66a551a6368a4ecab65902e75643152e__section_gy3_ddb_r1b"/>

## Example

The integration flow contains a Content Modifier step followed by an XSLT Mapping step. You can configure both steps so that an XSLT mapping is dynamically read from the Partner Directory.

In the *XSLT Mapping* step, specify the following settings:

In the *Source* field, select *Header*, and in the *Header Name* field, specify `XSLT_FROM_PD`. This is the name of the header, which must be filled in a previous step \(in our example, a Content Modifier\).

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

Enter `XSLT_FROM_PD`.

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

Enter `pd:${property.SENDER}:xslt:Binary`.

The expression `${property.SENDER}` makes sure that the Partner ID is dynamically read from the Partner Directory, the entry `xslt` is the name of the parameter for the XSLT mapping in the Partner Directory, and the expression `Binary` classifies it as a binary parameter.

</td>
</tr>
</table>

