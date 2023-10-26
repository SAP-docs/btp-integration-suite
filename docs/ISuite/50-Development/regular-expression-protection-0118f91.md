<!-- loio0118f91793b54ad78de0e831c10bd69f -->

# Regular Expression Protection

API Management helps to identify common content level threats that follow certain patterns, by enabling developers configure regular expressions that can be evaluated against API traffic at runtime.

This policy extracts information from a message \(for example, URI Path, Query Param, Header, Form Param, Variable, XML Payload, or JSON Payload\) and evaluates that content against predefined regular expressions. If any specified regular expressions evaluates to true, the message is considered a threat and is rejected. The most common usage of RegularExpressionProtection policy is the evaluation of payloads of JSON and XML for malicious content.

This policy supports regular expression rules as the classes in the java.util.regex package in java language.

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> 
> <RegularExpressionProtection async="false" continueOnError="true" enabled="true" xmlns="http://www.sap.com/apimgmt">
>                <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>                
> 				 <!--Validates if the Uri path has “internal” keyworkd -->
> 			     <URIPath>
>                    <Pattern>(.*)(internal)(.*)</Pattern>
>                </URIPath> 
>  									
> 				<!--Validates if  the “action” query param has any sql injection code to do any invasive operation -->
>                <QueryParam name="action">
>                    <Pattern>[\s]*((delete)|(exec)|(drop\s*table)|(insert)|(shutdown)|(update)|(\bor\b))</Pattern>
>                </QueryParam>
> 
> 				<!--Validates if the “action” header has any content with “threat” string -->
>                <Header name="action">
>                    <Pattern>(.*)(threat)(.*)</Pattern>
>                </Header>
> 
> 				<!--Validates if the “action” form param has any content with “threat” string -->
>                <FormParam name="action">
>                    <Pattern>(.*)(threat)(.*)</Pattern>
>                </FormParam>
> 
> 				<!--Validates if “flow.actionvar” variable has any content with “threat” string -->
>                <Variable name="flow.actionvar">
>                    <Pattern>(.*)(threat)(.*)</Pattern>
>                </Variable>
> 
>                <Source>request</Source>
> 
> 				<!--Validates if “command.action” node has any content with “threat” string -->
>                <JSONPayload>
>                    <JSONPath>
>                         <Expression>$.command.action</Expression>
>                         <Pattern>(.*)(threat)(.*)</Pattern>
>                    </JSONPath>
>                </JSONPayload>
> 
> 				<!--Validates if “/sap:Command/sap:Action” node has any content with “threat” string -->
>                <XMLPayload>
>                    <Namespaces>
>                          <Namespace prefix="sap">http://www.sap.com</Namespace>
>                    </Namespaces>
>                    <XPath>
>                         <Expression>/sap:Command/sap:Action</Expression>
>                         <Type>string</Type>
>                         <Pattern>(.*)(threat)(.*)</Pattern>
>                    </XPath>
>                </XMLPayload>
> </RegularExpressionProtection>
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
<th valign="top">

Presence

</th>
</tr>
<tr>
<td valign="top">

Source

</td>
<td valign="top">

Indicates the message from which information needs to be extracted.

If the <Source\> element is omitted, the value defaults to message. For example, <Source\>message</Source\>. When set to message, the policy uses the request message as source when attached to a request flow. Likewise, the policy uses the response message when attached to a response flow.

If the source message cannot be resolved or if it resolves to a non-message type, the policy returns an error.

`<Source>response</Source>`

</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

IgnoreUnresolvedVariables

</td>
<td valign="top">

If set to true and any variable is unresolvable, the policy returns an error and the unresolved variable is treated as empty string \(Null\).

`<IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>`

</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

URIPath

</td>
<td valign="top">

Specifies the request URI path from where the information needs to be extracted and evaluated against the provided regular expression. Provide at least one <Pattern\> element specifying a regular expression pattern to match.

```
<URIPath>
			<Pattern>REGEX PATTERN</Pattern>
			<Pattern>REGEX PATTERN</Pattern>
		 </URIPath>
```



</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

QueryParam

</td>
<td valign="top">

Specifies the request query parameter from where the information needs to be extracted and evaluated against the provided regular expression. Provide at least one <Pattern\> element specifying a regular expression pattern to match.

```
<QueryParam name="s-query-param">
			<Pattern>REGEX PATTERN</Pattern>
			<Pattern>REGEX PATTERN</Pattern>
		 </QueryParam>
```



</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

Specifies the request and response header from where the information needs to be extracted and evaluated against the provided regular expression. Provide at least one <Pattern\> element specifying a regular expression pattern to match.

```
<Header name="s-header">
			<Pattern>REGEX PATTERN</Pattern>
			<Pattern>REGEX PATTERN</Pattern>
		 </Header>
```



</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

FormParam

</td>
<td valign="top">

Specifies the request form parameter from where the information needs to be extracted and evaluated against the provided regular expression. Provide at least one <Pattern\> element specifying a regular expression pattern to match.

```
<FormParam name="s-form-param">
			<Pattern>REGEX PATTERN</Pattern>
			<Pattern>REGEX PATTERN</Pattern>
		 </FormParam>
```



</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

Variable

</td>
<td valign="top">

Specifies the variable from where the information needs to be extracted and evaluated against the provided regular expression.

```
<Variable name="request.content">
			<Pattern>REGEX PATTERN</Pattern>
			<Pattern>REGEX PATTERN</Pattern>
		 </Variable>
```



</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

XMLPayload

</td>
<td valign="top">

Specifies theXML payload from where the information needs to be extracted and evaluated against the provided regular expression.

```
<XMLPayload>
			<Namespaces>
			  <Namespace prefix="sap">http://www.sap.com</Namespace>
			</Namespaces>
			<XPath>
				<Expression>/sap:Greeting/sap:User</Expression>
				<Type>string</Type>
				<Pattern>REGEX PATTERN</Pattern>
				<Pattern>REGEX PATTERN</Pattern>
			</XPath>
		 </XMLPayload>
```



</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

JSONPayload

</td>
<td valign="top">

Specifies the JSON payload from where the information needs to be extracted and evaluated against the provided regular expression.

```
<JSONPayload>
			<JSONPath>
			   <Expression>$.store.book[*].author</Expression>
				<Pattern>REGEX PATTERN</Pattern>
				<Pattern>REGEX PATTERN</Pattern>
			</JSONPath>
		 </JSONPayload>
```



</td>
<td valign="top">

Optional

</td>
</tr>
</table>

RegularExpressionProtection policy type defines the following error codes:


<table>
<tr>
<th valign="top">

Error code

</th>
<th valign="top">

Message

</th>
</tr>
<tr>
<td valign="top">

NothingToEnforce

</td>
<td valign="top">

RegularExpressionProtection \{0\}: at least one of URIPath, QueryParam, Header, FormParam, XMLPayload, JSONPayload is mandatory

</td>
</tr>
<tr>
<td valign="top">

NoPatternsToEnforce

</td>
<td valign="top">

RegularExpressionProtection \{0\}: No patterns to enforce in \{1\}

</td>
</tr>
<tr>
<td valign="top">

EmptyXPathExpression

</td>
<td valign="top">

RegularExpressionProtection \{0\}: Empty XPath expression

</td>
</tr>
<tr>
<td valign="top">

EmptyJSONPathExpression

</td>
<td valign="top">

RegularExpressionProtection \{0\}: Empty JSONPath expression

</td>
</tr>
<tr>
<td valign="top">

DuplicatePrefix

</td>
<td valign="top">

RegularExpressionProtection \{0\}: Duplicate prefix \{1\}

</td>
</tr>
<tr>
<td valign="top">

NONEmptyPrefixMappedToEmptyURI

</td>
<td valign="top">

RegularExpressionProtection \{0\}: Non-empty prefix \{1\} cannot be mapped to empty uri

</td>
</tr>
<tr>
<td valign="top">

ThreatDetected

</td>
<td valign="top">

Regular Expression Threat Detected in \{0\}: regex: \{1\} input: \{2\}

</td>
</tr>
<tr>
<td valign="top">

ExecutionFailed

</td>
<td valign="top">

Failed to execute the RegularExpressionProtection StepDefinition \{0\}. Reason: \{1\}

</td>
</tr>
<tr>
<td valign="top">

VariableResolutionFailed

</td>
<td valign="top">

Failed to resolve variable \{0\}

</td>
</tr>
<tr>
<td valign="top">

NonMessageVariable

</td>
<td valign="top">

Variable \{0\} does not resolve to a Message

</td>
</tr>
<tr>
<td valign="top">

SourceMessageNotAvailable

</td>
<td valign="top">

\{0\} message is not available for RegularExpressionProtection StepDefinition \{1\}

</td>
</tr>
<tr>
<td valign="top">

InvalidRegularExpression

</td>
<td valign="top">

RegularExpressionProtection \{0\}: Invalid Regular Expression \{1\}, Context \{2\}

</td>
</tr>
<tr>
<td valign="top">

InstantiationFailed

</td>
<td valign="top">

Failed to instantiate the RegularExpressionProtection StepDefinition \{0\}

</td>
</tr>
<tr>
<td valign="top">

CannotBeConvertedToNodeset

</td>
<td valign="top">

RegularExpressionProtection \{0\}: Result of xpath \{1\} cannot be converted to nodeset. Context \{2\}

</td>
</tr>
<tr>
<td valign="top">

XPathCompilationFailed

</td>
<td valign="top">

RegularExpressionProtection \{0\}: Failed to compile xpath \{1\}. Context \{2\}

</td>
</tr>
<tr>
<td valign="top">

JSONPathCompilationFailed

</td>
<td valign="top">

RegularExpressionProtection \{0\}: Failed to compile jsonpath \{1\}. Context \{2\}

</td>
</tr>
</table>

