<!-- loio72d9d22ae143415381cc717f6b406dab -->

# XML to JSON

API Management provides policies to convert messages from the extensible markup language \(XML\) format to JavaScript object notation \(JSON\) format. This policy is called the XML to JSON.

In an ideal scenario, you often pair a JSON to XML policy on the inbound request flow with an XML to JSON policy on the outbound response flow. By combining policies this way, a JSON API can be exposed for back end services that natively support only XML.

In cases where the APIs are consumed by diverse client apps that may require either JSON or XML, you can set the response format dynamically by configuring JSON to XML and XML to JSON policies to execute with conditions.

The policy can be attached in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!-- The policy will convert xml response to json response and store in variable named jsonresponse
> , Attributes of a xml tag will be mapped with root "root_tag" and the attributes inside root will have names with prefix as "attributes"-->
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <XMLToJSON async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>                    <Options>
>                               <OutputSuffix>_SUFFIX</OutputSuffix> <OutputPrefix>PREFIX_</OutputPrefix>
>                               <AttributePrefix>BAR_</AttributePrefix>
>                               <AttributeBlockName>FOO_BLOCK</AttributeBlockName>
>                               <TextNodeName>TEXT</TextNodeName>
>                               <TextAlwaysAsProperty>true</TextAlwaysAsProperty>
>                               <!-- The below three elements have to be used in conjunction if there is a namespace in the xml that is to undergo conversion -->
>                               <NamespaceSeparator/>
>                               <DefaultNamespaceNodeName/>
>                               <NamespaceBlockName/>
>                               <NullValue>NULL</NullValue>
>                               <RecognizeNull>true</RecognizeNull>
>                               <RecognizeNumber>true</RecognizeNumber>
>                               <RecognizeBoolean>true</RecognizeBoolean>
>                               <TreatAsArray>
>                                              <Path unwrap="false">custom/xpath</Path>
>                               </TreatAsArray>
>                </Options>
>                <!-- The variable to which the converted JSON should be assigned to -->
>                <OutputVariable>response</OutputVariable>
>                <!-- The variable that we want to convert to JSON -->
>                <Source>response</Source>
> 
> </XMLToJSON>
> 
> ```


<table>
<tr>
<th valign="top">

**Attribute Name**

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

The request or response variable that contains the XML message that you want to convert to JSON.

Usually, you set this to request or response, depending on whether you need to convert an inbound XML request, or an outbound XML response, into JSON.

If you don’t define the Source, it is treated as message. If the source variable is unresolved, or resolves to a non-message type, the policy throws an error.

Syntax: `<Source>request</Source>`

</td>
</tr>
<tr>
<td valign="top">

OutputVariable \(mandatory when the variable defined in the Source is a string\)

</td>
<td valign="top">

Stores the output of the XML to JSON format conversion. This is usually the same value as the source, that is, usually inbound XML request in converted to an inbound JSON request.

If you do not specify an OutputVariable, the source is treated as OutputVariable. For example, if the source is response, then OutputVariable defaults to response.

Syntax: `<OutputVariable>response</OutputVariable>`

</td>
</tr>
<tr>
<td valign="top">

Options

</td>
<td valign="top">

Use Options to have control over the conversion from XML to JSON.

The following configuration elements can be added as children of the Options element. All options are optional, however, at a minimum, an empty Options element must be present for a policy to be valid.

</td>
</tr>
<tr>
<td valign="top">

<Options\>/<RecognizeBoolean\>

</td>
<td valign="top">

Allows the conversion to maintain boolean values instead of turning them into strings.

Valid values: true and false

The default value is true

If the policy configuration looks like:

```
<RecognizeBoolean>true</RecognizeBoolean>
```

Consider an XML example:

```
<x>
  <y>false</y>
  <z>value</z>
</x>
```

If true, then:

```
{
    "x": {
        "y": false,
        "z": "value"
    }
}
```

If false, then:

```
{
    "x": {
        "y": "false",
        "z": "value"
    }
}
```



</td>
</tr>
<tr>
<td valign="top">

<Options\>/<RecognizeNumber\>

</td>
<td valign="top">

Allows the number fields in the XML payload to retain their original format if the value is true.

Valid values: true or false

Default value: true

If the policy configuration looks like:

```
<RecognizeNumber>true</RecognizeNumber>
```

Consider an XML example:

```
<x>
  <y>999</y>
  <z>value</z>
</x>
```

If true, then:

```
{
    "x": {
        "y": 999
        "z": "value"
    }
}
```

If false, then:

```
{
    "x": {
        "y": "999"
        "z": "value"
    }
}
```



</td>
</tr>
<tr>
<td valign="top">

<Options\>/<RecognizeNull\>

</td>
<td valign="top">

Allows you to convert empty values to null values.

Valid values: true and false

The default value is false

If the policy configuration looks like:

```
<RecognizeNull>true</RecognizeNull>
```

Consider an XML example:

```
<x>
  <y></y>
  <z>value</z>
</x>
```

If true, then:

```
{
    "x": {
        "y": null
        "z": "value"
    }
}
```

If false, then:

```
{
    "x": {
        "y": {},
        "z": "value"
    }
}
```



</td>
</tr>
<tr>
<td valign="top">

<Options\>/<NullValue\>

</td>
<td valign="top">

Indicates a null value. By default the value is NULL.

Syntax: `<NullValue>NULL</NullValue>`

</td>
</tr>
<tr>
<td valign="top">

<Options\>/<NamespaceSeparator\>

</td>
<td valign="top" rowspan="3">

Use the three elements NamespaceSeparator, NamespaceBlockName, and DefaultNamespaceNodeName together.

If the policy configuration looks like:

```
<NamespaceBlockName>#namespaceblock</NamespaceBlockName>
		<DefaultNamespaceNodeName>$defaultname</DefaultNamespaceNodeName>
		<NamespaceSeparator>:</NamespaceSeparator>
```

Consider the following XML example:

```
<x xmlns="http://abc.com" xmlabc:ns1="http://abc1.com">
  <abc1:y>value</abc1:y>
</x>
```

If NamespaceSeparator isn’t specified, the following JSON structure is generated:

```
{
    "x": {
        "y": "value"
    }
}
```

If the elements NamespaceSeparator, NamespaceBlockName, and DefaultNamespaceNodeName are specified as `:` , `#namespaceblock`, and `$defaultname` respectively, then the following JSON structure is generated:

```
{
    "x": {
        "&namespaces": {
            "%": "http://abc.com",
            "abc1": http://abc1.com
        },
        "abc1:y": "value"
    }
}
```



</td>
</tr>
<tr>
<td valign="top">

<Options\>/<NamespaceBlockName\>

</td>
</tr>
<tr>
<td valign="top">

<Options\>/<DefaultNamespaceNodeName\>

</td>
</tr>
<tr>
<td valign="top">

<Options\>/<OutputPrefix\>

</td>
<td valign="top" rowspan="2">

Use the two elements OutputPrefix and OutputSuffix together.

Syntax:

```
<OutputSuffix>_SUFFIX</OutputSuffix> 
		<OutputPrefix>PREFIX_</OutputPrefix>
```

Consider the following XML example: `<x>value</x>`

If both the attributes are specified as defined in the XML to JSON example, the following JSON structure is generated:

```
PREFIX_{
    "x": "value"
}_SUFFIX
```

If only OutputPrefix is specified, the following JSON structure is generated:

```
PREFIX_{
  "x" : "value"
}
```

If only OutputSuffix is specified, the following JSON structure is generated:

```
{
  "x" : "value"
}_SUFFIX
```

If neither OutputPrefix nor OutputSuffix is specified, the following JSON structure is generated:

```
{
    "x": "value"
}
```



</td>
</tr>
<tr>
<td valign="top">

<Options\>/<OutputSuffix\>

</td>
</tr>
<tr>
<td valign="top">

<Options\>/<AttributeBlockName\>

</td>
<td valign="top" rowspan="2">

Use the two attributes AttributeBlockName and AttributePrefix together, to group the values into a JSON block and append prefixes to the attribute names.

Consider the following XML example: `<a att1="value1" att2="value2"/>`

If the policy configuration looks like:

```
<AttributeBlockName>FOO_BLOCK</AttributeBlockName>
<AttributePrefix>BAR_</AttributePrefix>
```

Then, the following JSON structure is generated:

```
{
  "a": {
    "FOO_BLOCK": {
      "BAR_att1": "value1",
      "BAR_att2": "value2"
    }
  }
}
```

If only AttributeBlockName is specified, the following JSON structure is generated:

```
{
    "a": {
        "FOO_BLOCK": {
            "att1": "value1",
            "att2": "value2"
        }
    }
}
```

If only AttributePrefix is specified, the following JSON structure is generated:

```
{
    "a": {
            "BAR_att1": "value1",
            "BAR_att2": "value2"
        }
    }
}
```

If neither value is specified, the following JSON structure is generated:

```
   "a": {
        "att1": "value1",
        "att2": "value2"
    }
}
```



</td>
</tr>
<tr>
<td valign="top">

<Options\>/<AttributePrefix\>

</td>
</tr>
<tr>
<td valign="top">

<Options\>/<TextAlwaysAsProperty\>

</td>
<td valign="top" rowspan="2">

Use the two elements TextAlwaysAsProperty and TextNodeName together.

Valid values: true/false

Default is false.

If set to true, the content of the XML element is converted to a string property.

If the policy configuration looks like:

```
<TextNodeName>TEXT</TextNodeName>
		<TextAlwaysAsProperty>true</TextAlwaysAsProperty>
```

For the following XML:

```
<a>
  <b>value1</b>
  <c>value2<d>value3</d>value4</c>
</a>
```

If TextAlwaysAsProperty is set to true and TextNodeName specified as TEXT, the following JSON structure is generated:

```
{
  "a": {
    "b": {
      "TEXT": "value1"
    },
    "c": {
      "TEXT": [
        "value2",
        "value4"
        ],
        "d": {
          "TEXT": "value3"
        }
      }
    }
}
```

If TextAlwaysAsProperty is set to false and TextNodeName specified as TEXT, the following JSON structure is generated:

```
{
    "a": {
        "b": "value1",
        "c": {
            "TEXT": [
                "value2",
                "value4"
            ],
            "d": "value3"
        }
    }
}
```



</td>
</tr>
<tr>
<td valign="top">

<Options\>/<TextNodeName\>

</td>
</tr>
<tr>
<td valign="top">

<Options\>/<TreatAsArray\>

</td>
<td valign="top">

Enables you to streamline the values from an XML document into a JSON array. This attribute is useful when the number of child elements vary from one to many, and you want to ensure the values are always in an array.

Syntax:

```
<Options>
    <TreatAsArray>
        <Path unwrap="true">employers/employername/employees/name</Path>
    </TreatAsArray>
</Options>
```

Consider the following xml example:

> ### Sample Code:  
> ```
> 
> #Example 1
> 
> <employers>
>   <employername>
>     <name>employer1</name>
>     <employees>
>         <name>emp1</name>
>         <name>emp2</name>
>     </employees>
>   </employername>
> </employers>
> 
> # Output
> 
> {
>   "employers" : {
>       "employername" : {
>           "name" : "employer1",
>           "employees" : {
>               "name" : [
>                  "emp1",
>                  "emp2"
>               ]}...
> 
> 
> # Example 2
> 
> 
> <employers>
>   <employername>
>     <name>employer1</name>
>     <employees>
>         <name>emp1</name>
>     </employees>
>   </employername>
> </employers>
> 
> # Output
> 
> {
>   "employers" : {
>       "employername" : {
>           "name" : "employer1",
>           "employees" : {
>               "name" : "emp1"
>               }
> 			}
> 		}
> 	}
> ```

By default, XMl to JSON policy puts multiple child values into an array \(example 1\). However, when there is only one child, the policy places it in a string. In such cases <TreatAsArray\>/<Path\> element allows you to control the output.

Using the <TreatAsArray\>/<Path\> element you can ensure that values for <name\> is always put oin an array, even for a single value. You configure this by identifying the Path to the element whose values you want to put in an array. like: \(consider example 2\)

```

	 <TreatAsArray>
		<Path>employers/employername/employees/name</Path>
       
    </TreatAsArray>

```

> ### Sample Code:  
> ```
> 
> <employers>
>   <employername>
>     <name>employer1</name>
>     <employees>
>         <name>emp1</name>
>      </employees>
>   </employername>
> </employers>
> 
> # Output
> 
> {
>   "employers" : {
>       "employername" : {
>           "name" : "employer1",
>           "employees" : {
>               "name" : [
>                  "emp1",
>                 ]}...
> 
> 
> ```

Also, in the above output, <employername\> element and the <name\> element for employees are unnecessary. We can unwrap them using the following syntax:

> ### Code Syntax:  
> ```
> 
> 	 <TreatAsArray>
> 		<Path unwrap="true">employers/employername/employees/name</Path>
>         <Path unwrap="true">employers/employername/employees/name</Path>
>     </TreatAsArray>
> 
> ```

Output:

> ### Sample Code:  
> ```
> 
> 	{
>   "employers" : [{
>       "name" : "employer1",
>       "employees" : ["emp1","emp2"]
>       }]...
> ```



</td>
</tr>
</table>

During the policy execution, the following errors can occur:

**Error Code**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

HTTP Status

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

EitherOptionOrFormat

</td>
<td valign="top">

500

</td>
<td valign="top">

See the fault string.

</td>
</tr>
<tr>
<td valign="top">

UnknownFormat

</td>
<td valign="top">

500

</td>
<td valign="top">

See the fault string.

</td>
</tr>
<tr>
<td valign="top">

FormatUnavailable

</td>
<td valign="top">

500

</td>
<td valign="top">

See the fault string.

</td>
</tr>
<tr>
<td valign="top">

SourceUnavailable

</td>
<td valign="top">

500

</td>
<td valign="top">

The variable specified in the `<Source>` element has to exist.

</td>
</tr>
<tr>
<td valign="top">

ExecutionFailed

</td>
<td valign="top">

500

</td>
<td valign="top">

See the fault string. Be sure the incoming message contains valid XML.

</td>
</tr>
<tr>
<td valign="top">

InvalidSourceType

</td>
<td valign="top">

500

</td>
<td valign="top">

See the fault string.

</td>
</tr>
<tr>
<td valign="top">

InCompatibleTypes

</td>
<td valign="top">

500

</td>
<td valign="top">

See the fault string.

</td>
</tr>
<tr>
<td valign="top">

OutputVariableIsNotAvailable

</td>
<td valign="top">

500

</td>
<td valign="top">

See the fault string.

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

The \[prefix\] is xmltojson..

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

xmltojson.XMLtoJSON-1.failed = true

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
>     "faultstring": "XMLToJSON[XMLtoJSON_1]: Source xyz is not available",
>     "detail": {
>       "errorcode": "steps.xml2json.SourceUnavailable"
>     }
>   }
> 
> ```

Following is an example of a fault rule:

> ### Sample Code:  
> ```
> <faultrule name="VariableOfNonMsgType"></faultrule><FaultRule name="XML to JSON Faults">
>     <Step>
>         <Name>AM-SourceUnavailableMessage</Name>
>         <Condition>(fault.name Matches "SourceUnavailable") </Condition>
>     </Step>
>     <Step>
>         <Name>AM-BadXML</Name>
>         <Condition>(fault.name = "ExecutionFailed")</Condition>
>     </Step>
>     <Condition>(xmltojson.XMLtoJSON_1.failed = true) </Condition>
> </FaultRule>
> ```

**Related Information**  


[JSON to XML](json-to-xml-908598d.md "API Management enables developers to convert messages from the JavaScript object notation (JSON) format to the extensible markup language (XML) format by using the JSON to XML policy type.")

