<!-- loioe68da2ff0e1241978fae3964261a41c5 -->

# Message Validation Policy

Validates a message and rejects it if it does not conform to the specified requirements.

This policy is used to:

-   Validate any XML message against an XSD schema.

-   Validate SOAP messages against a WSDL definition.
-   Confirm JSON or XML is well-formed, based on content-type \(if <ResourceURL\> element is omitted\)

You can attach the policy in the following locations ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows

> ### Sample Code:  
> ```
> <!-- The policy will validate the response again the xsd, in the below policy the soap message is validated to 
> contain a element with name "msg" and type string -->
> 
> <MessageValidation async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <Element namespace="http://www.webserviceX.NET">string</Element>
>     <SOAPMessage version= "1.1/1.2" />
>     <Source>request</Source>
>     <ResourceURL>xsd://validation.xsd</ResourceURL>
> </MessageValidation>
> 
> Example validation.xsd
> <?xml version="1.0" encoding="UTF-8"?><xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://www.webserviceX.NET">
>   <xs:element name="msg" type="xs:string"/>
> </xs:schema>
> ```

**Attributes of the `<MessageValidation>` element**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`async`

</td>
<td valign="top">

false

</td>
<td valign="top">

String

</td>
<td valign="top">

This attribute is deprecated.

</td>
</tr>
<tr>
<td valign="top">

`continueOnError`

</td>
<td valign="top">

false

</td>
<td valign="top">

String

</td>
<td valign="top">

Set to false to return an error when a policy fails. This is expected behavior for most policies. Set to true to have flow execution continue even after a policy fails.

</td>
</tr>
<tr>
<td valign="top">

`enabled`

</td>
<td valign="top">

true

</td>
<td valign="top">

String

</td>
<td valign="top">

Set to true to enforce the policy. Set to false to "turn off" the policy. The policy will not be enforced even if it remains attached to a flow.

</td>
</tr>
</table>

**`<Element>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Element` \(Mandatory\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Specifies the root, or parent, element of the messages to be validated.

> ### Sample Code:  
> ```
> <Element namespace="http://finance.com/1999">PurchaseOrder</Element> 
> ```



</td>
</tr>
</table>

**`namespace` attribute of the `<Element>` element**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`namespace`

</td>
<td valign="top">

http://sample.com

</td>
<td valign="top">

String

</td>
<td valign="top">

Provides the namespace of the root, or parent, element of the messages to be validated.

</td>
</tr>
</table>

**`<SOAPMessage>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`SOAPMessage` \(Mandatory\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Provides the SOAP version against which to validate SOAP messages.

> ### Sample Code:  
> ```
> <SOAPMessage version= "1.1/1.2" />
> ```



</td>
</tr>
</table>

**`version` attribute of the `<SOAPMessage>` element**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`version`

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Identifies the SOAP version against which to validate SOAP messages. Valid values: 1.1, 1.2, 1.1/1.2

</td>
</tr>
</table>

**`<Source>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Source` 

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Identifies the source message to be validated.

If you do not provide a `<Source>` value, a value of message is used.

If the `<Source>` variable cannot be resolved, or resolves to a non-message type, then one of the following occurs:

If the `<Source>` variable resolves to a null value in the message flow, a steps.messagevalidation.SourceMessageNotAvailable error code is thrown.

If the `<Source>` variable resolves to a non-message value, a steps.messagevalidation.NonMessageVariable error code is thrown.

> ### Sample Code:  
> ```
> <Source>request</Source>
> ```



</td>
</tr>
</table>

**`<ResourceURL>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`ResourceURL` \(Optional\)

</td>
<td valign="top">

wsdl://<name\>

</td>
<td valign="top">

String

</td>
<td valign="top">

Identifies the XSD schema or WSDL definition to be used to validate the source message.

If the WSDL does not have schemas or if the maximum import depth exceeds 10, message validation will fail.

If a `<ResourceURL>` value is not specified, the message is checked for well-formed JSON or XML if the content-type is application/json or application/xml, respectively.

> ### Sample Code:  
> ```
> <ResourceURL>xsd://validation.xsd</ResourceURL>
> ```



</td>
</tr>
</table>

Message Validation policy type defines the following error codes:


<table>
<tr>
<th valign="top">

Error code

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

InvalidResourceType

</td>
<td valign="top">

InvalidResourceType MessageValidation \{0\}: Invalid Resource Type \{1\}. It should be xsd or wsdl. Context \{2\}

</td>
</tr>
<tr>
<td valign="top">

ResourceCompileFailed

</td>
<td valign="top">

ResourceCompileFailed MessageValidation \{0\}: Failed to compile resource \{1\}. Context \{2\}

</td>
</tr>
<tr>
<td valign="top">

RootElementNameUnspecified

</td>
<td valign="top">

RootElementNameUnspecified MessageValidation \{0\}: RootElement name is not specified

</td>
</tr>
<tr>
<td valign="top">

InvalidRootElementName

</td>
<td valign="top">

InvalidRootElementName MessageValidation \{0\}: RootElement name \{1\} is invalid

</td>
</tr>
<tr>
<td valign="top">

NonMessageVariable

</td>
<td valign="top">

NonMessageVariable Variable \{0\} does not resolve to a Message

</td>
</tr>
<tr>
<td valign="top">

SourceMessageNotAvailable

</td>
<td valign="top">

SourceMessageNotAvailable \{0\} message is not available for MessageValidation: \{1\}

</td>
</tr>
<tr>
<td valign="top">

NoElements

</td>
<td valign="top">

Resource "\{0\}" has no element definitions

</td>
</tr>
<tr>
<td valign="top">

Failed

</td>
<td valign="top">

MessageValidation \{0\} failed with reason: "\{1\}"

</td>
</tr>
</table>

