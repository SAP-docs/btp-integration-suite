<!-- loioa0615a5b8f7b4c81b5d72fe88b43d553 -->

# XSL Transform

Extensible stylesheet language transformations \(XSLT\) is a language that is used to convert documents from one XML format to another. This policy is used in applications that support XML but require a different XML-format for the same data.

The XSL Transformation policy is executed as a processing step in an API proxy flow. The XSLT is implemented via an xsl file that is stored in the API proxy bundle under `APIProxy/FileResources/<policyname>.xsl`. The XSL policy references this XSL file.

The XSL policy requires two inputs:

-   The name of an XSLT stylesheet \(which contains a set of transformation rules\) stored in the API proxy bundle under APIProxy/FileResources
-   The source of the XML to be transformed \(typically a request or response message\)

> ### Note:  
> `<xsl:include>` and `<xsl:import>` are not supported in the xslt code used in this policy.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> 
> <!-- The policy will take the read the xml response and transform the xsl and assign the transformed xml to the output variable outVar
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <XSL async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <OutputVariable>outVar</OutputVariable>
>     <ResourceURL>xsl://XSLTransform.xsl</ResourceURL>
>     <Source>response</Source>
> </XSL>
> 
> example :  XSLTransform.xsl
> 
> <?xml version="1.0" encoding="UTF-8"?><xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
>   <xsl:template match="/hello-world">
>     <HTML>
>       <HEAD>
>         <TITLE/>
>       </HEAD>
>       <BODY>
>         <H1>
>           <xsl:value-of select="greeting"/>
>         </H1>
>         <xsl:apply-templates select="greeter"/>
>       </BODY>
>     </HTML>
>   </xsl:template>
>   <xsl:template match="greeter">
>     <DIV>from <I>
> <xsl:value-of select="."/>
> </I>
> </DIV>
>   </xsl:template>
> </xsl:stylesheet>
> ```


<table>
<tr>
<th valign="top">

**Elements and Attributes**

</th>
<th valign="top">

 

</th>
<th valign="top">

 

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" colspan="3">

Source \(Optional\)

</td>
<td valign="top">

Contains the message from which information needs to be extracted. Usually this value is set to request or response, depending on whether the message to be transformed is inbound or outbound.

-   If source is missing, it is treated as a simple message. For example, <Source\>message</Source\>.
-   If the source variable cannot be resolved, or resolves to a non-message type, the transformation step fails.



</td>
</tr>
<tr>
<td valign="top" colspan="3">

OutputVariable \(Optional\)

</td>
<td valign="top">

A variable that stores the output of the transformation. The OutputVariable cannot be of Message type, that is, it cannot be 'message', 'request', or 'response'. You should set this element to be a custom variable, and then consume that variable.

To replace the message content with the output of the transformation, delete this element.

</td>
</tr>
<tr>
<td valign="top" colspan="3">

ResourceURL \(Mandatory\)

</td>
<td valign="top">

The XSLT file to be used for transforming the message

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Parameters\(Optional\)

</td>
<td valign="top" colspan="2">

ignoreUnresolvedVariables

\(Optional\)

</td>
<td valign="top">

Ignores any unresolved variable errors in the XSLT script instructions.

Valid values: true/false

Default value: false

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Parameter

\(Optional\)

</td>
<td valign="top">

name

\(Mandatory\)



</td>
<td valign="top">

Name of a custom parameter. Note that with name you can only use one of the optional parameters listed below.

</td>
</tr>
<tr>
<td valign="top">

ref\(Optional\)

</td>
<td valign="top">

Specifies the reference that sources the value from a variable.

</td>
</tr>
<tr>
<td valign="top">

value

\(Optional\)

</td>
<td valign="top">

Value of the parameter

</td>
</tr>
</table>

During the policy execution, the following errors can occur:

**Error Cause**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

XSLSourceMessageNotAvailable

</td>
<td valign="top">

\{0\} message is not available for XSL: \{1\}

</td>
</tr>
<tr>
<td valign="top">

XSLEvaluationFailed

</td>
<td valign="top">

Evaluation of XSL \{0\} failed with reason: "\{1\}"

</td>
</tr>
<tr>
<td valign="top">

XSLVariableResolutionFailed

</td>
<td valign="top">

Failed to resolve variable \{0\}

</td>
</tr>
<tr>
<td valign="top">

XSLInvalidResourceType

</td>
<td valign="top">

XSL \{0\}: Resource type must be xsl. Context \{1\}

</td>
</tr>
<tr>
<td valign="top">

XSLEmptyResourceUrl

</td>
<td valign="top">

Resource Url cannot be empty in XSL \{0\}

</td>
</tr>
</table>

