<!-- loio908598da29524e2aa1afd4aabf5eb51e -->

# JSON to XML

API Management enables developers to convert messages from the JavaScript object notation \(JSON\) format to the extensible markup language \(XML\) format by using the JSON to XML policy type.

This policy is useful for enabling backend XML services to support RESTful apps that require JSON \(for example, due to a lack of an XML parsing capabilities on the client\).

In a typical mediation scenario, a JSON to XML policy on the inbound request flow is often paired with an XML to JSON policy on the outbound response flow. By combining policies this way, a JSON API can be exposed for services that natively support only XML.

For scenarios where APIs are consumed by diverse consumer applications which may require either JSON or XML, the format of the response can be dynamically set by configuring JSON to XML and XML to JSON policies to execute conditionally.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!-- The policy will convert the json response to corresponding xml response for all elements where 
> the parent is rootElement and child is item inside it, if the root element of json doent have name, the objectRootElementName
>  property defines the name in xml -->  
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <JSONToXML async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <Options>
>         <ArrayItemElementName>item</ArrayItemElementName>
>         <ArrayRootElementName>rootelement</ArrayRootElementName>
>         <ObjectRootElementName>objectroot</ObjectRootElementName>
>         <InvalidCharsReplacement></InvalidCharsReplacement>
>         <AttributePrefix></AttributePrefix>
>         <AttributeBlockName></AttributeBlockName>
>         <TextNodeName></TextNodeName>
>         <NamespaceSeparator></NamespaceSeparator>
>         <DefaultNamespaceNodeName></DefaultNamespaceNodeName>
>         <NamespaceBlockName></NamespaceBlockName>
>         <NullValue>I_AM_NULL</NullValue>
>     </Options>
>     <OutputVariable>response</OutputVariable>
>     <Source>response</Source>
> </JSONToXML>
> ```

Following table lists the elements and attributes that you can configure on this policy


<table>
<tr>
<th valign="top">

**Elements and Attributes**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

Source \(optional\)

</td>
<td valign="top">

The variable containing the JSON-formatted message to be converted to XML. Usually, you set this to request or response, depending on whether the message to be transformed is inbound or outbound.

If you have not defined the source, then it is treated as message, resolving to a request when the policy is attached to a request flow, or a response when the policy is attached to a response flow.

If the source variable cannot be resolved, or resolves to a non-message type, the policy throws an error.

</td>
</tr>
<tr>
<td valign="top">

OutputVariable

</td>
<td valign="top">

The variable name of the resultant XML-formatted message. Usually, you set this to request or response, depending on whether the message to be transformed is inbound or outbound. In most cases, a JSON request is transformed into an XML request. Similarly, a JSON response is usually transformed into an XML response.

If OutputVariable is not specified, then the source variable is treated as OutputVariable. That is, the policy assumes that a JSON request, for example, is being converted into an XML request.

> ### Note:  
> This element is required when the variable defined in the Source element is a string.



</td>
</tr>
<tr>
<td valign="top">

InvalidCharsReplacement

</td>
<td valign="top">

To assist with handling invalid XML that may cause issues with a parser, this setting replaces any JSON elements that produce invalid XML with the string.

For example, the following setting: `<InvalidCharsReplacement>_</InvalidCharsReplacement>`

Converts this JSON object:

```
{
    "First%%%Name": "Adam"
}
```

to this XML structure: `<First_Name>Adam<First_Name>`

</td>
</tr>
<tr>
<td valign="top">

TextNodeName

</td>
<td valign="top">

Converts a JSON property into an XML text node with the specified name. For example, the following setting: `<TextNodeName>age</TextNodeName>`

converts this JSON:

```
{
    "person": {
        "firstName": "Adam",
        "lastName": "Philip",
        "age": 30
    }
}
```

to this XML structure:`<person><firstName>Adam</firstName>30<lastName>Philip</lastName></person>`

If TextNodeName is not specified, the XML is generated, using the default setting for a text node:

```
<person>
  <firstName>Adam</firstName>
  <age>30</age>
  <lastName>Philip</lastName>
</person>
```



</td>
</tr>
<tr>
<td valign="top">

NullValue

</td>
<td valign="top">

Indicates a null value. By default the value is NULL.

For example the following setting: `<NullValue>NULL_VALUE</NullValue>`

Converts the following JSON object: `{"person" : "NULL_VALUE"}`

to the following XML element: `<person></person>`

Where no value \(or a value other than NULL\_VALUE\) is specified for the Null value, then the same payload converts to: `<person>NULL_VALUE</person>`

</td>
</tr>
<tr>
<td valign="top">

AttributeBlockName

</td>
<td valign="top">

Enables you to specify when JSON elements are converted into XML attributes \(rather than XML elements\).

For example, the following setting converts properties inside an object named \#attrs into XML attributes: `<AttributeBlockName>#attrs</AttributeBlockName>`

The following JSON object:

```
{
    "person" : {
        "#attrs" : {
            "firstName" : "Adam",
            "lastName" : "Philip"
        },        
        "location" : "California"
    }
}
```

is converted to the following XML structure:

`<person firstName="Adam" lastName="Philip"><location>California</location></person>`

</td>
</tr>
<tr>
<td valign="top">

AttributePrefix

</td>
<td valign="top">

Converts the property starting with the specified prefix into XML attributes.

Where the attribute prefix is set to \#, for example: `<AttributePrefix>#</AttributePrefix>`

Converts the following JSON object:

```
{
"person" : {
   "#firstName" : "Adam",
   "#lastName" : "Philip",
   "location" : "California"

 }
}
```

to the following XML structure:

`<person firstName="Adam" lastName="Philip"><location>California</location></person>`

</td>
</tr>
<tr>
<td valign="top">

NamespaceBlockName

DefaultNamespaceNodeName

NameSpaceSeparator

</td>
<td valign="top">

JSON has no support for namespaces, while XML documents often require them. The NamespaceBlockName enables you to define a JSON property that serves as the source of a namespace definition in the XML that is produced by the policy. \(This means that the source JSON must provide a property that can be mapped into a namespace that is expected by application that consumes the resulting XML.\)

For example, the following settings:

```
<NamespaceBlockName>#namespaceblock</NamespaceBlockName>
<DefaultNamespaceNodeName>$defaultname</DefaultNamespaceNodeName>
<NamespaceSeparator>:</NamespaceSeparator>
```

indicates that a property called \#namespaceblock exists in the source JSON that contains at least one namespace designated as the default. For example:

```
{
   "vehicle": {
       "#namespaceblock": {
           "$default": "http://www.w3.org/1999/name",
           "xmlns:model": "http://www.w3.org/1999/models"
       },
       "name": "Car",
       "models:name": "Alto"
   }
}
```

converts to:

```
<name xmlns="http://www.w3.org/1999/name" xmlns:exp="http://www.w3.org/1999/models">
  <name>Car</name>
  <models:name>Alto</models:name>
</name>
```



</td>
</tr>
<tr>
<td valign="top">

ArrayRootElementName

ArrayItemElementName

</td>
<td valign="top">

Converts a JSON array into a list of XML elements with specified parent and child element names.

For example, the following settings:

```
<ArrayRootElementName>Array</ArrayRootElementName>
<ArrayItemElementName>Item</ArrayItemElementName>
```

Converts the following JSON array:

```
[
"Doctor",
{
 "occupation": "Engineer"
},
"Scientist"
]
```

into the following XML structure:

```
<Array>
  <Item>Dcotor</Item>
  <Item>
    <occupation>Engineer</occupation>
  </Item>
  <Item>Scientist</Item>
</Array>
```



</td>
</tr>
<tr>
<td valign="top">

ObjectRootElementName

</td>
<td valign="top">

Specifies the root element name when you convert from JSON, which does not have a named root element, to XML.

For example, if the JSON appears as:

```
{
  "xyz": "123",
  "abc": "234"
}
```

And you set the ObjectRootElementName as:`<ObjectRootElementName>Root</ObjectRootElementName>`

The resulting XML appears as:

```
<Root>
   <xyz>123</xyz>>
   <abc>234</abc>
</Root>
```



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

SourceUnavailable

</td>
<td valign="top">

The variable specified in the Source element is not available or cannot be resolved.

</td>
</tr>
<tr>
<td valign="top">

ExecutionFailed

</td>
<td valign="top">

The input payload \(JSON\) is empty or the input \(JSON\) passed to XML policy is invalid or malformed.

</td>
</tr>
<tr>
<td valign="top">

OutputVariableIsNotAvailable

</td>
<td valign="top">

The variable specified in the Source element of the JSON to XML Policy is of type string and the OutputVariable is not defined.

</td>
</tr>
<tr>
<td valign="top">

InCompatibleTypes

</td>
<td valign="top">

The type of the variable defined in the Source and OutputVariable element does not match. The valid types are message and string.

</td>
</tr>
<tr>
<td valign="top">

InvalidSourceType

</td>
<td valign="top">

The type of the variable used to define the Source element is invalid. The valid types are message and string.

</td>
</tr>
</table>

The following fault variables are set when the policy triggers an error at runtime:

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

The variable \[prefix\] is jsontoxml.

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

jsontoxml.JSON-to-XML-1.failed = true

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
>     "faultstring": "JSONToXML[JSON-to-XML-1]: Source abc is not available",
>     "detail": {
>       "errorcode": "steps.json2xml.SourceUnavailable"
>     }
>   }
> }
> ```

Following is an example of a fault rule:

> ### Sample Code:  
> ```
> <FaultRule name="JSON To XML Faults">
>     <Step>
>         <Name>AM-SourceUnavailableMessage</Name>
>         <Condition>(fault.name Matches "SourceUnavailable") </Condition>
>     </Step>
>     <Step>
>         <Name>AM-BadJSON</Name>
>         <Condition>(fault.name = "ExecutionFailed")</Condition>
>     </Step>
>     <Condition>(jsontoxml.JSON-to-XML-1.failed = true) </Condition>
> </FaultRule>
> ```

**Related Information**  


[XML to JSON](xml-to-json-72d9d22.md "API Management provides policies to convert messages from the extensible markup language (XML) format to JavaScript object notation (JSON) format. This policy is called the XML to JSON.")

[XSL Transform](xsl-transform-a0615a5.md "Extensible stylesheet language transformations (XSLT) is a language that is used to convert documents from one XML format to another. This policy is used in applications that support XML but require a different XML-format for the same data.")

