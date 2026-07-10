<!-- loio3de6615cc00843499d6a427e93e2c582 -->

# XML Threat Protection

API Management enables developers to address XML vulnerabilities and minimize attacks on API. Further, it allows you to detect XML payload attacks based on configured limits and screen against XML threats by using the following approaches:

-   Validating messages against the XML schema \(.xsd\)
-   Evaluating message content for specific blocklisted keywords or patterns
-   Detecting corrupt or malformed messages before such messages are parsed

You can attach this policy in the following locations:

![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> 
> <XMLThreatProtection async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>    <NameLimits>
>             <Element>20</Element>
>             <Attribute>20</Attribute>
>             <NamespacePrefix>20</NamespacePrefix>
>             <ProcessingInstructionTarget>20</ProcessingInstructionTarget>
>     </NameLimits>
>     <Source>request</Source>
>     <StructureLimits>
>             <NodeDepth>6</NodeDepth>
>             <AttributeCountPerElement>3</AttributeCountPerElement>
>        	  <NamespaceCountPerElement>5</NamespaceCountPerElement>
>             <ChildCount  includeComment="true" includeElement="true" includeProcessingInstruction="true" includeText="true">5</ChildCount>
>      </StructureLimits>
>      <ValueLimits>
>              <Text>10</Text>
>              <Attribute>12</Attribute>
>              <NamespaceURI>12</NamespaceURI>
>              <Comment>12</Comment>
>              <ProcessingInstructionData>12</ProcessingInstructionData>
>  	 </ValueLimits>
> </XMLThreatProtection>
> 
> ```


<table>
<tr>
<th valign="top">

**Attribute Name**

</th>
<th valign="top">

 

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top" colspan="2">

Source

</td>
<td valign="top">

Indicates the message that needs to be screened for XML payload attacks. If it is set to request, you must validate the inbound requests from client apps. If it is set to message, the element automatically evaluates the request or response message when the message is attached to a request flow or a response flow respectively.

`<Source>request</Source>`

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Name Limits \(Optional\)

</td>
<td valign="top">

Element

</td>
<td valign="top">

NameLimits indicates the character limits that need to be checked and enforced by the policy.

The NameLimits <Element\> element indicates the limit on the maximum number of characters allowed in an element name.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML:
> 
> ```
> 
> <book category="WEB">
>    <title>XML for Beginners</title>
>    <author>Adam J. Smith</author>
>    <year>2010</year>
> </book>
> ```
> 
> The policy snippet below validates that the element names do not exceed the specified character limit.
> 
> ```
> 
> <NameLimits>
>    <Element>15</Element>
>    <Attribute>15</Attribute>
>    <NamespacePrefix>15</NamespacePrefix>
>    <ProcessingInstructionTarget>15</ProcessingInstructionTarget>     
> </NameLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

Attribute

</td>
<td valign="top">

Indicates a limit on the maximum number of characters allowed in an attribute name within the XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML:
> 
> ```
> 
> <book category="WEB">
>    <title>XML for Beginners</title>
>    <author>Adam J. Smith</author>
>    <year>2010</year>
> </book>
> ```
> 
> The policy snippet below validates that the attribute name does not exceed the specified character limit.
> 
> ```
> 
> <NameLimits>
>    <Element>15</Element>
>    <Attribute>15</Attribute>
>    <NamespacePrefix>15</NamespacePrefix>
>    <ProcessingInstructionTarget>15</ProcessingInstructionTarget>     
> </NameLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

NamespacePrefix

</td>
<td valign="top">

Indicates a limit on the maximum number of characters allowed in the namespace prefix within the XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML: `<ns1:myelem xmlns:ns1="http://abc.com"/>`
> 
> The policy snippet below validates that the namespace prefix `ns1` does not exceed the specified character limit.
> 
> ```
> 
> <NameLimits>
>    <Element>15</Element>
>    <Attribute>15</Attribute>
>    <NamespacePrefix>15</NamespacePrefix>
>    <ProcessingInstructionTarget>15</ProcessingInstructionTarget>     
> </NameLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

ProcessingInstructionTarget

</td>
<td valign="top">

Indicates a limit on the maximum number of characters allowed in the target of any processing instructions within the XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML: `<?xml-doc type="text/xsl" href="doc.xsl"?>`
> 
> The policy snippet below validates that the processing instruction target `xml-doc` does not exceed the specified character limit.
> 
> ```
> 
> <NameLimits>
>    <Element>15</Element>
>    <Attribute>15</Attribute>
>    <NamespacePrefix>15</NamespacePrefix>
>    <ProcessingInstructionTarget>15</ProcessingInstructionTarget>     
> </NameLimits>
> ```



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

StructuralLimits \(Optional\)

</td>
<td valign="top">

NodeDepth

</td>
<td valign="top">

StructuralLimits indicates the structural limits that need to be checked and enforced by the policy.

The StructuralLimits <NodeDepth\> element indicates the maximum node depth that is allowed within an XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> ```
> <StructureLimits>
>    <NodeDepth>6</NodeDepth>
>    <AttributeCountPerElement>3</AttributeCountPerElement>
>    <NamespaceCountPerElement>5</NamespaceCountPerElement>
>    <ChildCount includeComment="true" includeElement="true" includeProcessingInstruction="true" includeText="true">5</ChildCount>
> </StructureLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

AttributeCountPerElement

</td>
<td valign="top">

Indicates the maximum number of attributes allowed for any element within an XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML:
> 
> ```
> 
> <book category="WEB">
>    <title>XML for Beginners</title>
>    <author>Adam J. Smith</author>
>    <year>2010</year>
> </book>
> ```
> 
> The policy snippet below validates that the elements book, title, author, and year do not have more than `3` attributes each. The attributes used for defining namespaces are not counted.
> 
> ```
> <StructureLimits>
>    <NodeDepth>6</NodeDepth>
>    <AttributeCountPerElement>3</AttributeCountPerElement>
>    <NamespaceCountPerElement>5</NamespaceCountPerElement>
>    <ChildCount includeComment="true" includeElement="true" includeProcessingInstruction="true" includeText="true">5</ChildCount>
> </StructureLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

NamespaceCountPerElement

</td>
<td valign="top">

Indicates the maximum number of namespace definitions allowed for any element within an XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML:
> 
> ```
> 
> <a1 attr1="value1" attr2="value2">
>     <a2 xmlns="http://sap.com" xmlns:abc="http://abc.com" one="1" abc:two="2"/>
> </a1>
> ```
> 
> The policy snippet below validates that for the elements `a1` and `a2`, the number of namespace definitions are limited to `5` each. In the above example, the `a1` element has `0` namespace definitions and the `a2` element has `2` namespace definitions: `xmlns="http://sap.com"` and`xmlns:abc="http://abc.com"`.
> 
> ```
> <StructureLimits>
>    <NodeDepth>6</NodeDepth>
>    <AttributeCountPerElement>3</AttributeCountPerElement>
>    <NamespaceCountPerElement>5</NamespaceCountPerElement>
>    <ChildCount includeComment="true" includeElement="true" includeProcessingInstruction="true" includeText="true">5</ChildCount>
> </StructureLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

ChildCount

</td>
<td valign="top">

Specifies the maximum number of child elements allowed for any element within an XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

The ChildCount element contains the following attributes:

-   includeComment \(Default: true\)
-   includeElement \(Default: true\)
-   includeProcessingInstructions \(Default: true\)
-   includeText \(Default: true\)

> ### Sample Code:  
> Example
> 
> ```
> <StructureLimits>
>    <NodeDepth>6</NodeDepth>
>    <AttributeCountPerElement>3</AttributeCountPerElement>
>    <NamespaceCountPerElement>5</NamespaceCountPerElement>
>    <ChildCount includeComment="true" includeElement="true" includeProcessingInstruction="true" includeText="true">5</ChildCount>
> </StructureLimits>
> ```



</td>
</tr>
<tr>
<td valign="top" rowspan="5">

ValueLimits \(Optional\)

</td>
<td valign="top">

Text

</td>
<td valign="top">

ValueLimits indicates the character limits for values to be checked and enforced by the policy.

The ValueLimits <Text\> element indicates the character limit for any text nodes within an XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML:
> 
> ```
> 
> <book category="WEB">
>    <title>XML for Beginners</title>
>    <author>Adam J. Smith</author>
>    <year>2010</year>
> </book>
> ```
> 
> The policy snippet below validates that the element text values `XML for Beginners`, `Adam J. Smith`, and `2010` do not exceed `20` characters each.
> 
> ```
> <ValueLimits>
>    <Text>20</Text>
>    <Attribute>10</Attribute>
>    <NamespaceURI>15</NamespaceURI>
>    <Comment>10</Comment>
>    <ProcessingInstructionData>10</ProcessingInstructionData>
> </ValueLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

Attribute

</td>
<td valign="top">

Indicates the character limit for any attribute values within an XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML:
> 
> ```
> 
> <book category="WEB">
>    <title>XML for Beginners</title>
>    <author>Adam J. Smith</author>
>    <year>2010</year>
> </book>
> ```
> 
> The policy snippet below validates that the attribute value `WEB` does not exceed `10` characters.
> 
> ```
> <ValueLimits>
>    <Text>20</Text>
>    <Attribute>10</Attribute>
>    <NamespaceURI>15</NamespaceURI>
>    <Comment>10</Comment>
>    <ProcessingInstructionData>10</ProcessingInstructionData>
> </ValueLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

NamespaceURI

</td>
<td valign="top">

Indicates the character limit for any namespace URIs within an XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML: `<ns:my_element xmlns:ns="http://ns.com"/>`
> 
> The policy snippet below validates that the namespace URI value `http://ns.com` does not exceed `15` characters.
> 
> ```
> <ValueLimits>
>    <Text>20</Text>
>    <Attribute>10</Attribute>
>    <NamespaceURI>15</NamespaceURI>
>    <Comment>10</Comment>
>    <ProcessingInstructionData>10</ProcessingInstructionData>
> </ValueLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

Comment

</td>
<td valign="top">

Indicates the character limit for any comment within an XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML:
> 
> ```
> 
> <book category="WEB">
> <!-- This is a comment -->
>    <title>XML for Beginners</title>
>    <author>Adam J. Smith</author>
>    <year>2010</year>
> </book>
> ```
> 
> The value of the <comment\> element in the policy snippet below validates that the comment text `This is a comment` does not exceed `10` characters.
> 
> ```
> <ValueLimits>
>    <Text>20</Text>
>    <Attribute>10</Attribute>
>    <NamespaceURI>15</NamespaceURI>
>    <Comment>10</Comment>
>    <ProcessingInstructionData>10</ProcessingInstructionData>
> </ValueLimits>
> ```



</td>
</tr>
<tr>
<td valign="top">

ProcessingInstructionData

</td>
<td valign="top">

Indicates the character limit for any processing instruction text within an XML document.

If you do not specify a limit, the policy applies a default value of -1, which denotes no limit.

> ### Sample Code:  
> Example
> 
> For the following example XML: `<?xml-doc type="text/xsl" href="doc.xsl"?>`
> 
> The policy snippet below validates that the processing instruction text `type="text/xsl" href="doc.xsl"` does not exceed `10` characters.
> 
> ```
> <ValueLimits>
>    <Text>20</Text>
>    <Attribute>10</Attribute>
>    <NamespaceURI>15</NamespaceURI>
>    <Comment>10</Comment>
>    <ProcessingInstructionData>10</ProcessingInstructionData>
> </ValueLimits>
> ```



</td>
</tr>
</table>

XML Threat Protection policy type defines the following error codes:


<table>
<tr>
<th valign="top">

Error Code

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

ExecutionFailed

</td>
<td valign="top">

Errors that occur when specific thresholds set in the policies are exceeded.

These errors include `node depth`, `attribute count`, `child count`, `namespace count`, `element name length`,`attribute name and value length`, `namespace prefix and URL length`, `processing instruction name and data length`, `comment length`, and `text length`.

</td>
</tr>
<tr>
<td valign="top">

NodeDepthExceeded

</td>
<td valign="top">

This error occurs when the maximum depth of XML elements allowed in an XML payload is exceeded.

</td>
</tr>
<tr>
<td valign="top">

AttrCountExceeded

</td>
<td valign="top">

This error occurs when the maximum number of attributes allowed in a single element is exceeded.

</td>
</tr>
<tr>
<td valign="top">

ChildCountExceeded

</td>
<td valign="top">

This error occurs when the maximum number of child elements allowed in an XML payload is exceeded.

</td>
</tr>
<tr>
<td valign="top">

NSCountExceeded

</td>
<td valign="top">

This error occurs when the number of name spaces allowed in a single element is exceeded.

</td>
</tr>
<tr>
<td valign="top">

ElemNameExceeded

</td>
<td valign="top">

This error occurs when the maximum string length allowed in an XML tag is exceeded.

</td>
</tr>
<tr>
<td valign="top">

AttrNameExceeded

</td>
<td valign="top">

This error occurs when the maximum length allowed for an attribute name is exceeded.

</td>
</tr>
<tr>
<td valign="top">

AttrValueExceeded

</td>
<td valign="top">

This error occurs when the maximum length allowed for an attribute value is exceeded.

</td>
</tr>
<tr>
<td valign="top">

NSPrefixExceeded

</td>
<td valign="top">

This error occurs when the namespace prefix length is exceeded.

</td>
</tr>
<tr>
<td valign="top">

NSURIExceeded

</td>
<td valign="top">

This error occurs when the namespace URL length is exceeded.

</td>
</tr>
<tr>
<td valign="top">

PITargetExceeded

</td>
<td valign="top">

This error occurs when the process instruction name length is exceeded.

</td>
</tr>
<tr>
<td valign="top">

PIDataExceeded

</td>
<td valign="top">

The allowed processing instruction data length is exceeded.

</td>
</tr>
<tr>
<td valign="top">

CommentExceeded

</td>
<td valign="top">

This error occurs when the maximum length allowed for a comment is exceeded.

</td>
</tr>
<tr>
<td valign="top">

TextExceeded

</td>
<td valign="top">

This error occurs when the maximum length allowed for text is exceeded.

</td>
</tr>
<tr>
<td valign="top">

SourceUnavailable

</td>
<td valign="top">

This error occurs when the message variable mentioned in the source element is either unavailable in the specific flow where the policy is being executed or it does not have a valid value \(request, response, or message\).

</td>
</tr>
<tr>
<td valign="top">

NonMessageVariable

</td>
<td valign="top">

This error occurs when the source element is set to a variable type which is not a message.

</td>
</tr>
<tr>
<td valign="top">

InvalidXMLPayload

</td>
<td valign="top">

This error occurs when the input XML Payload is invalid.

</td>
</tr>
</table>

Following fault variables is set when the policy triggers an error at runtime:

**Fault Variables**


<table>
<tr>
<th valign="top">

Variable Set

</th>
<th valign="top">

Where

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

\[prefix\].\[policy\_name\].failed

</td>
<td valign="top">

The \[prefix\] is xmlattack.

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

xmlattack.XPT-SecureRequest.failed = true

</td>
</tr>
<tr>
<td valign="top">

fault.\[error\_name\]

</td>
<td valign="top">

\[error\_name\] = The specific error name to check for as listed in the table above.

</td>
<td valign="top">

fault.name Matches "SourceUnavailable"

</td>
</tr>
</table>

Following is an example of an error response:

> ### Sample Code:  
> ```
> {
>   "fault": {
>     "faultstring": "XMLThreatProtection[XPT-SecureRequest]: Execution failed. reason: XMLThreatProtection[XTP-SecureRequest]: Exceeded object entry name length at line 2",
>     "detail": {
>       "errorcode": "steps.xmlthreatprotection.ExecutionFailed"
>     }
>   }
> }
> ```

Following is an example of a fault rule:

> ### Sample Code:  
> ```
> <FaultRule name="XML Threat Protection Policy Faults">
>     <Step>
>         <Name>AM-CustomErrorResponse</Name>
>         <Condition>(fault.name Matches "ExecutionFailed") </Condition>
>     </Step>
>     <Condition>(xmlattack.XPT-SecureRequest.failed = true) </Condition>
> </FaultRule>
> ```

**Related Information**  


[JSON Threat Protection](json-threat-protection-952cbd7.md "Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings.")

[Regular Expression Protection](regular-expression-protection-0118f91.md "API Management helps to identify common content level threats that follow certain patterns, by enabling developers configure regular expressions that can be evaluated against API traffic at runtime.")

