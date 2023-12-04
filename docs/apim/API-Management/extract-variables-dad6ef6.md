<!-- loiodad6ef6e8bf444819cd5e26b649bbdd2 -->

# Extract Variables

The Extract variables policy can be used to extract content from the HTTP request or response messages of the API Proxy and assign that content to specific variables that can be accessed during the execution of the API Proxy.

For more information on how to extract different variables, see [Examples](examples-6f56308.md).

This policy can be applied on the request or response stream of the proxy endpoint or target endpoint.

You can attach the policy in one of the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!-- The policy will extract data at xpath /Developer/Email and store in varaible "email" for xml payload -->
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <ExtractVariables async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <Source>AccessEntity.GetDeveloperProfile</Source>
>     <XMLPayload>
>         <Variable name="email" type="string">
>             <XPath>/Developer/Email</XPath>
>         </Variable>
>     </XMLPayload>
> </ExtractVariables>
> ```


<table>
<tr>
<th valign="top">

**Element**

</th>
<th valign="top">

**Attribute Name**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

Pattern

</td>
<td valign="top">

ignoreCase

</td>
<td valign="top">

Specifies the pattern to be applied to the parent element. The list of parent elements are:

-   URIPath
-   QueryParam
-   FormParam
-   Header
-   Variable



</td>
</tr>
<tr>
<td valign="top">

<URIPath\>

</td>
<td valign="top">



</td>
<td valign="top">

Extracts the value of a variable from the specified URI path of the specified message. This element is applicable only if source is request.

\* You must include at least one of the following:

`<URIPath>, <QueryParam>, <Header>, <FormParam>, <JSONPayload>, or <XMLPayload>`

</td>
</tr>
<tr>
<td valign="top">

<QueryParam\>

</td>
<td valign="top">

name\(Mandatory\)

</td>
<td valign="top">

Extracts the value of a variable from the specified query parameter of the specified message.

\* You must include at least one of the following:

`<URIPath>, <QueryParam>, <Header>, <FormParam>, <JSONPayload>, or <XMLPayload>`

</td>
</tr>
<tr>
<td valign="top">

<Header\>

</td>
<td valign="top">

name\(Mandatory\)

</td>
<td valign="top">

Extracts the value of a variable from the specified HTTP header of the specified message.

\* You must include at least one of the following:

`<URIPath>, <QueryParam>, <Header>, <FormParam>, <JSONPayload>, or <XMLPayload>`

</td>
</tr>
<tr>
<td valign="top">

<FormParam\>

</td>
<td valign="top">

name\(Mandatory\)

</td>
<td valign="top">

Extracts the value of a variable from the specified form parameter. Form parameters can be extracted only when the contentType of the specified message is application/x-wwwform- urlencoded.

\* You must include at least one of the following:

`<URIPath>, <QueryParam>, <Header>, <FormParam>, <JSONPayload>, or <XMLPayload>`

</td>
</tr>
<tr>
<td valign="top">

<Variable\>

</td>
<td valign="top">

name\(Mandatory\)

</td>
<td valign="top">

Specifies the name of the variable to which the extracted value will be assigned. If there is a VariablePrefix element, then this name will be appended, as variableprefix.name.

For example, suppose the name is specified as Developer:

If `<VariablePrefix>` is not specified, the extracted values are assigned to `Developer`.

If `<VariablePrefix>` is specified as `MyUser`, the extracted values are assigned to `MyUser.Developer`.

> ### Note:  
> When an XML variable is not resolved via an XPath expression, the ExtractVariables policy will result in an error. So, continueOnError or IgnoreUnresolvedVariables should be set to true to allow the execution of the policy.



</td>
</tr>
<tr>
<td valign="top">

<IgnoreUnresolvedVariables\>

</td>
<td valign="top">



</td>
<td valign="top">

Set to `true` to treat any unresolvable variable as an empty string \(null\). Set to `false` if you want the policy to throw an error when any referenced variable is unresolvable.

</td>
</tr>
<tr>
<td valign="top">

<JSONPayload\>

</td>
<td valign="top">



</td>
<td valign="top">

Specifies the JSON formatted message from which the value of the variable will be extracted.

\* You must include at least one of the following:

`<URIPath>, <QueryParam>, <Header>, <FormParam>, <JSONPayload>, or <XMLPayload>`

</td>
</tr>
<tr>
<td valign="top">

<JSONPayload\><Variable\>

</td>
<td valign="top">



</td>
<td valign="top">

Specific the variable where the extracted value will be assigned.

</td>
</tr>
<tr>
<td valign="top">

<JSONPayload\><Variable\><JSONPath\>

</td>
<td valign="top">



</td>
<td valign="top">

Specifies the JSON path used to extract the value of a variable from a JSON formatted message.

JSON payloads are extracted only when the contentType of the specified message is application/json.

</td>
</tr>
<tr>
<td valign="top">

<Source\>

</td>
<td valign="top">



</td>
<td valign="top">

Specifies the message to be parsed. The value of Source defaults to message. The message value is context-sensitive; In a request flow, message resolves to the request message.

In a response flow, message resolves to the response message.

If the source variable cannot be resolved, or resolves to a nonmessage type, the policy will fail to respond.

In advanced configurations, source can resolve to a variable containing a message generated by another policy, such as one generated from a ServiceCallout.

</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

clearPayload

</td>
<td valign="top">

Set to true is you want to clear the request payload after the request is sent to the HTTP target.

Use the clearPayload option only if the request message is not required after the ServiceCallout is executed because clearPayload allocates memory during message processing.

</td>
</tr>
<tr>
<td valign="top">

<VariablePrefix\>

</td>
<td valign="top">



</td>
<td valign="top">

The complete variable name is created by joining the <VariablePrefix\>,a dot, and the name you define in curly braces in the Pattern element.

</td>
</tr>
<tr>
<td valign="top">

<XMLPayload\>

</td>
<td valign="top">



</td>
<td valign="top">

Specifies the XML formatted message from which the value of the variable will be extracted.

\* You must include at least one of the following:

`<URIPath>, <QueryParam>, <Header>, <FormParam>, <JSONPayload>, or <XMLPayload>`

> ### Note:  
> When an XML variable is not resolved via an XPath expression, the ExtractVariables policy will result in an error. So, continueOnError or IgnoreUnresolvedVariables should be set to true to allow the execution of the policy.



</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

stopPayload

Processing

</td>
<td valign="top">

Set to true to stop XPath evaluation after one variable is populated.

</td>
</tr>
<tr>
<td valign="top">

<XMLPayload\>

<Namespaces\>

</td>
<td valign="top">



</td>
<td valign="top">

Specifies the namespace to be used in the XPath evaluation. XML payloads are extracted only when the contentType of the message is text/xml, application/xml, or application/\*+xml

</td>
</tr>
<tr>
<td valign="top">

<XMLPayload\><Variable\>

</td>
<td valign="top">



</td>
<td valign="top">

Specifies variable to which the extracted value will be assigned.

</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

type

</td>
<td valign="top">

Specifies the data type of the variable value. Supported data types are as follows:

-   string
-   boolean
-   integer
-   long
-   float
-   double
-   nodeset \(returns an XML fragment\)



</td>
</tr>
<tr>
<td valign="top">

XPath

</td>
<td valign="top">



</td>
<td valign="top">

Specifies the XPath defined for the variable. Only XPath 1.0 expressions are supported.

</td>
</tr>
<tr>
<td valign="top">

<XMLPayload\>

<Variable\>

<XPath\>

</td>
<td valign="top">



</td>
<td valign="top">

Specifies the XPath defined for the variable. Only XPath 1.0 expressions are supported.

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

ExecutionFailed

</td>
<td valign="top">

The policy tried to parse input that is malformed or otherwise invalid.

The policy tried to parse XML with a namespace that is not declared in the <Namespace\> element.

</td>
</tr>
<tr>
<td valign="top">

SourceMessageNotAvailable

</td>
<td valign="top">

A variable specified in <Source\> is out of scope or can't be resolved. For example, if the policy executes in the request flow, the <Source\> variable cannot be set to response or error.

</td>
</tr>
<tr>
<td valign="top">

SetVariableFailed

</td>
<td valign="top">

The policy was not able to set a variable value.

</td>
</tr>
<tr>
<td valign="top">

ImmutableVariable

</td>
<td valign="top">

A variable used in the policy is immutable. The policy was unable to set this variable.

</td>
</tr>
<tr>
<td valign="top">

VariableResolutionFailed

</td>
<td valign="top">

The policy could not resolve a variable. Be sure the variable you are trying to set exists in the runtime flow.

</td>
</tr>
<tr>
<td valign="top">

UnsupportedOperation

</td>
<td valign="top">

The policy tried to perform an unsupported operation on named flow variables.

</td>
</tr>
<tr>
<td valign="top">

UnableToCast

</td>
<td valign="top">

The policy was unable to cast a variable.

</td>
</tr>
<tr>
<td valign="top">

JSONPathCompilationFailed

</td>
<td valign="top">

The policy was unable to compile a JSON path expression.

</td>
</tr>
<tr>
<td valign="top">

JsonPathParsingFailure

</td>
<td valign="top">

The policy was unable to parse a JSON path to extract data into flow variables.

</td>
</tr>
<tr>
<td valign="top">

InvalidJSONPath

</td>
<td valign="top">

A JSON path used in the policy is invalid.

</td>
</tr>
<tr>
<td valign="top">

NothingToExtract

</td>
<td valign="top">

A required element is missing from the policy. At least one of these elements is required: `URIPath, QueryParam, Header, FormParam, XMLPayload, JSONPayload`.

</td>
</tr>
<tr>
<td valign="top">

NONEmptyPrefixMappedToEmptyURI

</td>
<td valign="top">

The <XMLPayload\> element is not configured properly. A non-empty prefix cannot be mapped to an empty URI.

</td>
</tr>
<tr>
<td valign="top">

DuplicatePrefix

</td>
<td valign="top">

The <XMLPayload\> element is not configured properly. There is a duplicate prefix.

</td>
</tr>
<tr>
<td valign="top">

NoXPathsToEvaluate

</td>
<td valign="top">

There are no XPaths to evaluate. An <XPath\> child element must be specified.

</td>
</tr>
<tr>
<td valign="top">

EmptyXPathExpression

</td>
<td valign="top">

The policy has invalid configuration of the <Variable\> child element of an <XMLPayload\> element.

</td>
</tr>
<tr>
<td valign="top">

NoJSONPathsToEvaluate

</td>
<td valign="top">

You do not specify a <JSONPath\> child element where it is required.

</td>
</tr>
<tr>
<td valign="top">

EmptyJSONPathExpression

</td>
<td valign="top">

The policy has an empty child element <JSONPath\> in a element <JSONPayload\>.

</td>
</tr>
<tr>
<td valign="top">

MissingName

</td>
<td valign="top">

The name attribute is missing from a policy element that requires it.

</td>
</tr>
<tr>
<td valign="top">

PatternWithoutVariable

</td>
<td valign="top">

A <Pattern\> element that does not have a variable specified. The element requires the name of the variable in which extracted data will be stored.

</td>
</tr>
<tr>
<td valign="top">

CannotBeConvertedToNodeset

</td>
<td valign="top">

The result of an XPath expression cannot be converted to type nodeset.

</td>
</tr>
<tr>
<td valign="top">

JSONPathCompilationFailed

</td>
<td valign="top">

The policy could not compile a specified JSON Path.

</td>
</tr>
<tr>
<td valign="top">

InstantiationFailed

</td>
<td valign="top">

The policy could not be instantiated.

</td>
</tr>
<tr>
<td valign="top">

XPathCompilationFailed

</td>
<td valign="top">

The policy could not compile a specified XPath. Be sure to declare any namespaces that are used in the XPath.

</td>
</tr>
<tr>
<td valign="top">

InvalidPattern

</td>
<td valign="top">

A <Pattern\> element is invalid in one of these elements: `URIPath, QueryParam, Header, FormParam, XMLPayload, JSONPayload`.

</td>
</tr>
</table>

Following fault variables are set when the policy triggers an error at runtime:

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

The \[prefix\] is extractvariables.

The \[policy\_name\] is the name of the policy to check.

</td>
<td valign="top">

extractvariables.EV-ParseJsonResponse.failed = true

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

fault.name = "SourceMessageNotAvailable"

</td>
</tr>
</table>

**Related Information**  


[Examples](examples-6f56308.md "You can use the Extract variables policy to choose the names of the variables to be set.")

