<!-- loioab38cc8da12446c190f7384480b6a1c1 -->

# Blueprint Metadata

Blueprint metadata defines the attributes of the sender and receiver adapters that contain multiple tags.This document mainly describes all the tags and attributes apart from CMD and camel blueprint tags for providing additional generation injection for ADK development.



<a name="loioab38cc8da12446c190f7384480b6a1c1__section_m3q_ds2_h1b"/>

## Blueprint Metadata

This set of tags and attributes allows you to define the metadata.


<table>
<tr>
<th valign="top">

Attributes

</th>
<th valign="top">

Datatype

</th>
<th valign="top">

Cardinality

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

createOnce

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">



</td>
<td valign="top">

If you set the string value as “true”, then the bean instantiation in the blueprint generation is done only once. By default the value is 'false'.

</td>
</tr>
<tr>
<td valign="top">

createCondition

</td>
<td valign="top">

xsd:string

</td>
<td valign="top">



</td>
<td valign="top">

This attribute can be used to conditionally instantiate the bean. The syntax followed is similar to XSLT test attribute.

For example:

> ### Sample Code:  
> ```
> <bean id=”123” class=”com.example.Someclass.java” createCondition="$.cmd.attribute(proxyType)='onPremise'"/>
> ```

Here `Someclass.java` is generated in the blueprint only if the UI variable `proxyType` contains the value `onPremise`.

</td>
</tr>
</table>


<table>
<tr>
<th valign="top">

Tag

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`<TransformationTags xmlns:bp=”http://www.adk.gen/xmlns/blueprint/”>` 

</td>
<td valign="top">

This is the parent tag for the `<blueprint>` tag. This tag does not contain any generation specific information as part of attribute. The `<blueprint>` tag must be included within this tag.

</td>
</tr>
<tr>
<td valign="top">

`<bp:blueprint>` 

</td>
<td valign="top">

This tag can be used to specify additional namespaces if needed.

</td>
</tr>
<tr>
<td valign="top">

`<bp:bean>` 

</td>
<td valign="top">

Beans are declared using <bean\> element.

</td>
</tr>
<tr>
<td valign="top">

`<bp:reference>` 

</td>
<td valign="top">

To generate References this tag can be used. This tag does not contain any new attributes. It is similar to the camel blueprint's reference tag. Refer the XSD above for all supported attributes.

</td>
</tr>
<tr>
<td valign="top">

`<cxfcore:bus xmlns:cxfcore=”http://cxf.apache.org/blueprint/core”>` 

</td>
<td valign="top">

Refer `http://cxf.apache.org/schemas/blueprint/core.xsd` for all attributes supported.

</td>
</tr>
<tr>
<td valign="top">

`<cxf:cxfEndpoint xmlns:cxf=”http://camel.apache.org/schema/blueprint/cxf”>` 

</td>
<td valign="top">

Refer `https://camel.apache.org/schema/cxf/camel-cxf.xsd` for all the attributes supported.

</td>
</tr>
<tr>
<td valign="top">

`<camel:camelContext xmlns:camel=”http://camel.apache.org/schema/blueprint”>` 

</td>
<td valign="top">

This is the root camel context tag just for the reference. This contains all the properties a final blueprint’s camelContext contains as part of g&b generation. The user is not allowed to make any change to this tag. Any changes/additions will simply be ignored.

</td>
</tr>
<tr>
<td valign="top">

`<http-conf:conduit xmlns:http-conf="http://cxf.apache.org/transports/http/configuration" >` 

</td>
<td valign="top">

This is same as that of Camel Blueprint specification for conduit tag. Refer `http://cxf.apache.org/schemas/configuration/http-conf.xsd`.

</td>
</tr>
<tr>
<td valign="top">

`<camel:route xmlns:camel="http://camel.apache.org/schema/blueprint">` 

</td>
<td valign="top">

This is same as that of Camel blueprint specification <route\>. Must apear within <camelContext\>.. Refer the XSD for the attributes. Multiple routes are supported.

</td>
</tr>
<tr>
<td valign="top">

`<properties>` 

</td>
<td valign="top">

Can be contained in the DSL just for reference. This tag must be same as g&b's generated tag. It has no significance. i.e. any modification to this tag can simply be ignored by the DSL processor.

</td>
</tr>
<tr>
<td valign="top">

`<streamCaching>` 

</td>
<td valign="top">

Provided just for the reference.

</td>
</tr>
</table>

