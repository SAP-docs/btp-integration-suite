<!-- loio6f563086cc0f4a92bf31681f31f8290a -->

# Examples

You can use the Extract variables policy to choose the names of the variables to be set.

You choose the source of the variable, and how many variables to extract and set. Below are some examples to illustrate how this policy works:

> ### Remember:  
> When an XML variable is not resolved via an XPath expression, the ExtractVariables policy will result in an error. So, continueOnError or IgnoreUnresolvedVariables should be set to true to allow the execution of the policy.



## Extract a variable from a query parameter

Consider an example where your API design specifies that incoming requests must carry a query parameter named code, which holds a term that looks like ABCXXXXX, where ABC is fixed, and the XXXXX denotes a varying string.

> ### Sample Code:  
> ```
> 
> <ExtractVariables>
> 	<QueryParam name="code">
> 		<Pattern ignoreCase="true">ABC{abccode}</Pattern>
> 	</QueryParam>
> 	<VariablePrefix>queryinfo</VariablePrefix>
> 	<IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
> </ExtractVariables>
> ```

Say, after a GET call, API Management sets the variable queryinfo.abccode to the value XXXXX.After API Management executes this Extract Variables policy, subsequent policies, or code in the processing flow can refer to the variable named queryinfo.abccode to get the string value XXXXX\(for example, 12345\).



## Extract variables from a JSON payload

The Extract Variables policy can also extract values from JSON messages. The example below illustrates how to extract a variable from a portion of a JSON message payload. Consider this response payload:

> ### Sample Code:  
> ```
> {
> "results": [{
> "key1":"value1",
> "key2":"value2"
> }]
> }
> ```

An element in the Extract Variables policy tells it to extract from a JSON payload. Rather than using text patterns, as you would when extracting values from headers, URI paths or query parameters, with JSON specify the portion to extract via a JSON path expression in which the $ character refers to the root node of the JSON. Here's an example policy to illustrate:

> ### Sample Code:  
> ```
> <ExtractVariables>
> 	<Source>response</Source>
> 	<VariablePrefix>myresp</VariablePrefix>
> 	<JSONPayload>
> 		<Variable name="first_key">
> 			<JSONPath>$.results[0].key1</JSONPath>
> 		</Variable>
> 	</JSONPayload>
> </ExtractVariables>
> ```

With this policy applied to the above message, API Management will extract a variable called `myresp.first_key` which will contain the value `value1`.



## Extract variables from an XML message

You can extract variables from an XML payload, using XPath and explicitly named variables. Consider the below payload:

> ### Sample Code:  
> ```
> <RootElement>       
> 	<Element1>              
> 		<Element2 attr="myattr"/>       
> 	</Element1>
> <RootElement>
> ```

> ### Sample Code:  
> ```
> <ExtractVariables>
> 	<Source>response</Source>
> 	<VariablePrefix>myprefix</VariablePrefix>
> 	<XMLPayload>
> 		<Variable name="attrvalue" type="string">
> 		<XPath>/RootElement/Element1/Element2/@attr</XPath>
> 		</Variable>
> 	</XMLPayload>
> </ExtractVariables>
> ```

With this policy, SAP API Management will set a variable called `myprefix.attrvalue` with the value `myattr`".

