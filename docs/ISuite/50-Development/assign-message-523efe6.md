<!-- loio523efe6d0a9d43beb5d62ad07937578f -->

# Assign Message

This policy allows you to create new or modify an existing HTTP request or response message.

Assign Message policy allows you to add, change, or remove properties of the request/response. It can also be leveraged to create a custom request or response message. This custom request/response message can be used in different policies like [Service Callout](service-callout-6b40873.md) policy.

This policy is so named because you need to assign a message to a variable. To use the Assign Message policy, you must select a variable name and specify the message content to assign to it. If you choose to use the standards names such as request or response, the value will be assigned to the request or response flows. If you use any other name, it will refer to a custom variable that can exist within the API Proxy execution flow.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> 
> <AssignMessage async="true" continueOnError="true" enabled="true">
> 	
> 	<Copy source="{source}">   
> 		<Headers>      
> 			<Header name="{header_name}"></Header>   
> 		</Headers>   
> 		<QueryParams>      
> 			<QueryParam name="{query_param_name}"></QueryParam>   
> 		</QueryParams>   
>           <FormParams>      
> 			<FormParam name="{form_param_name}"></FormParam>   
>           </FormParams>   
>           <Payload>{boolean_value}</Payload>   
>           <Verb>{boolean_value}</Verb>   
>           <Version>{boolean_value}</Version>   
>           <Path>{boolean_value}</Path>   
>           <StatusCode>{boolean_value}</StatusCode>   
>           <ReasonPhrase>{boolean_value}</ReasonPhrase> 
> 	</Copy>
>  
>      <Remove>   
>      	<Headers>      
> 			<Header name="{header_name}"></Header>   
>           </Headers>   
>           <QueryParams>      
> 			<QueryParam name="{query_param_name}"></QueryParam>   
>           </QueryParams>   
>           <FormParams>      
> 			<FormParam name="{form_param_name}"></FormParam>   
>           </FormParams>   
>           <Payload>{boolean_value}</Payload> 
> 	</Remove> 
> 	
> 	<Add>   
> 		<Headers>      
> 			<Header name=" {header_name }">{value}</Header>   
> 		</Headers>   
> 		<QueryParams>      
> 			<QueryParam name="{query_param_name }">{value}</QueryParam>   
>           </QueryParams>   
>           <FormParams>      
> 			<FormParam name="{form_param_name}">{value}</FormParam>   
>           </FormParams> 
> 	</Add> 
> 	
> 	<Set>   
>           <Headers>      
> 			<Header name="{header_name}">{value}</Header>   
>           </Headers>   
>           <QueryParams>      
> 			<QueryParam name="{query_param_name}">{value} </QueryParam>   
>           </QueryParams>   
>           <FormParams>      
> 			<FormParam name="{form_param_name}">{value}</FormParam>   
>           </FormParams>   
>           <Payload/>   
>           <Verb>{verb}</Verb>   
>           <Version>{version}</Version>   
>           <Path>{path}</Path>   
>           <StatusCode>{status_code}</StatusCode>   
>           <ReasonPhrase>{reason_phrase}</ReasonPhrase> 
> 	</Set> 
> 	
> 	<AssignVariable>   
>           <Name>{name}</Name>   
>           <Value>{value}</Value>                              
>           <Ref>{ref value}</Ref> 
>      </AssignVariable> 
> 
>      <IgnoreUnresolvedVariables>{boolean_value}</IgnoreUnresolvedVariables> 
>      <AssignTo createNew="true" transport="http" type="request"></AssignTo>
> </AssignMessage>
> ```


<table>
<tr>
<th valign="top">

**Elements & Attributes**

</th>
<th valign="top">

 

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top" colspan="2">

AssignTo \(Optional\)

</td>
<td valign="top">

Specifies the variable to which the message will be assigned.

If this element is missing, it is treated as request or response, depending on the Flow to which the policy is attached. If attached to a response Flow, for example, the default type is response.

In some cases, you cannot change the object on which this policy works. For example, you cannot change query parameters or form parameters on the response, but can only do so on the request.

> ### Sample Code:  
> Syntax
> 
> ```
> 
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <IgnoreUnresolvedVariables>[true|false]</IgnoreUnresolvedVariables>
>   <AssignTo createNew="[true|false]" transport="http" type="[request|response]">destination_variable_name</AssignTo>
> </AssignMessage>
> 
> ```

> ### Sample Code:  
> Example
> 
> The following example specifies that the target is the original request that will be sent to the target endpoint:
> 
> ```
> 
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
> 	<IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
> 	<AssignTo createNew="false" transport="http" type="request">destination_variable_name</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top" colspan="2">

createNew \(Optional\)

</td>
<td valign="top">

It is a Boolean value which indicates if the request or response object should be newly created or if the existing message should be modified.

If the value is `true`, the policy creates a new request or response object, based on the type specified. If no name is specified for the new variable, the policy creates a new request or response object, based on the value of type.

> ### Note:  
> When a new request or response object is created, it deletes the existing one and replaces it completely.

If the value is `false`, the policy responds in one of the following ways:

-   If the variable name to a request or response is resolved, the processing continues.
-   If the variable name to a request or response is not resolved, or is resolved to a non-message type, the policy throws an error.

If the value of `createNew` is not specified, the policy responds in one of the following ways:

-   If `createNew` resolves to a message, the processing continues.
-   If `createNew` is not resolved, or is resolved to a non-message type, a new variable of type specified in `type` is created.



</td>
</tr>
<tr>
<td valign="top" colspan="2">

transport \(Optional\)

</td>
<td valign="top">

It is a string which indicates the transport method for request and response messages. The only supported value is HTTP.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

type \(Optional\)

</td>
<td valign="top">

It is a string that specifies the type of the new message, when `createNew` is `true`.

Valid values: `request` or `response`

Default value: `request`

</td>
</tr>
<tr>
<td valign="top" colspan="2">

IgnoreUnresolvedVariables \(Optional\)

</td>
<td valign="top">

If `IgnoreUnresolvedVariables` is set to `false` and any variable cannot be resolved, then the policy throws an error.

If it is set to `true` and any variable is unresolvable, the variable is treated as empty string \(Null\).

Valid values: `true` or `false`

Default value: `false`

> ### Sample Code:  
> Syntax
> 
> ```
> 
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <IgnoreUnresolvedVariables>[true|false]</IgnoreUnresolvedVariables>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets `IgnoreUnresolvedVariables` to `true`:
> 
> ```
> 
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="response">
>     ...
>     <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
>   </Copy>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top" rowspan="10">

Copy \(Optional\)

</td>
<td valign="top">

source

</td>
<td valign="top">

Copies the specified information from the <source\> to the variable specified in the <AssignTo\> element.

If the source is not specified, it is treated as a simple message. If the source variable cannot be resolved, or resolves to a non-message type, <Copy\> fails to respond.

</td>
</tr>
<tr>
<td valign="top">

Headers

</td>
<td valign="top">

Copies HTTP headers.

To copy multiple headers, mention the header name in the name attribute as below:

`<Copy source='request>`

`<Headers>`

`<Header name="headerA"/>`

`<Header name="headerB"/>`

`</Headers>`

`</Copy>`

To copy all headers, specify `<Copy><Headers/></Copy>`.

> ### Sample Code:  
> Syntax
> 
> ```
> 
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="[request|response]">
>     <!-- Can also be an empty array (<Headers/>) -->
>     <Headers>
>       <Header name="header_name">header_value</Header>
>       ...
>     </Headers>
>   </Copy>
> <IgnoreUnresolvedVariables>[true|false]</IgnoreUnresolvedVariables>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example copies the temp header from the request to the new CustomReq object:
> 
> ```
> 
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="request">
>     <Headers>
>       <Header name="temp"/>
>     </Headers>
>   </Copy>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="request">CustomReq</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

QueryParams

</td>
<td valign="top">

Copies query parameters.

Note that the QueryParams is copied only when both the source and AssignTo type are request.

To copy all query parameters, specify `<Copy><QueryParams/></Copy>`.

You can use query parameters only when the message type is Request and the HTTP verb is GET.

> ### Sample Code:  
> Syntax
> 
> ```
> 
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="[request|response]">
>     <!-- Can also be an empty array (<QueryParams/>) -->
>     <QueryParams>
>       <QueryParam name="queryparam_name">queryparam_value</QueryParam>
>       ...
>     </QueryParams>
>   </Copy>
> <IgnoreUnresolvedVariables>[true|false]</IgnoreUnresolvedVariables>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example copies the `temp_param` query parameter from the request into a new CustomReq object:
> 
> ```
> 
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>  <Copy source="request">
>     <QueryParams>
>       <QueryParam name="temp_param"/>
>     </QueryParams>
>   </Copy>
> 	<IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="request">CustomReq</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

FormParams

</td>
<td valign="top">

Copies the form parameters from the request specified in the <source\> attribute of <Copy\> to the request specified by AssignTo.

Note that the FormParams is copied only when the contentType is source and AssignTo is application/x-wwwform-urlencoded.

To copy all form parameters, specify `<Copy><FormParams/></Copy>`.

You can use query parameters only when the message type is Request and the HTTP verb is POST. Additionally, you should meet one \(or both\) of the following criteria:

-   Set the Form data to some value, or `'''` \(empty string\). For example, with `curl`, add `-d ""` to your request.
-   Set the `Content-Length` header to [0\] if there is no data in the original request; otherwise, set it to the current length in bytes. For example, with `curl`, add `-H "Content-Length: 0"` to your request.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="[request|response]">
>     <!-- Can also be an empty array (<FormParams/>) -->
>     <FormParams>
>       <FormParam name="formparam_name">formparam_value</FormParam>
>       ...
>     </FormParams>
>   </Copy>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example copies three form parameters to the custom request `CustomReq`:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>    <Copy source="request"> 
> 	<FormParams>
>       <FormParam name="pName1"/>
>       <FormParam name="pName2"/>
>       <FormParam name="pName3"/>
>     </FormParams>
>   </Copy>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="request">CustomReq</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

Payload

</td>
<td valign="top">

Valid values: `true` or `false`.

If true, the Content-Type header is copied.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="[request|response]">
>     <Payload>[false|true]</Payload>
>   </Copy>
> </AssignMessage>>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets <Payload\> to "true" so that the request payload is copied from the request to the response:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="request">
>     <Payload>true</Payload>
>   </Copy>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="response"/>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

Version

</td>
<td valign="top">

Valid values: `true` or `false`.

If true, the HTTP version is copied.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="[request|response]">
>     <Version>[false|true]</Version>
>   </Copy>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets <Version\> to "true" on the request, which copies the version from the default request object to a new custom request object:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="request">
>     <Version>true</Version>
>   </Copy>
>   <AssignTo createNew="true" transport="http" type="request">CustomReq</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

Verb

</td>
<td valign="top">

Valid values: `true` or `false`.

If true, the verb of the request gets assigned to the new request message, which is indicated by the AssignTo variable. This element is applicable only for HTTP request and not for response.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="[request|response]">
>     <Verb>[false|true]</Verb>
>   </Copy>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets <Verb\> to "true", which copies the verb from the default request to a new custom request:
> 
> ```
> <AssignMessage name="copy-verb-1">
>   <Copy source="request">
>     <Verb>true</Verb>
>   </Copy>
>   <AssignTo createNew="true" transport="http" type="request">MyCustomRequest</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

Path

</td>
<td valign="top">

If true, the path of the request gets assigned to the path of the new request object, which is indicated by the AssignTo variable. This element is applicable only for HTTP request and not for response.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="[request|response]">
>     <Path>[false|true]</Path>
>   </Copy>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example indicates that Assign Message should copy the path from the source request to the new custom request object:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="request">
>     <Path>true</Path>
>   </Copy>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="request">CustomReq</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

StatusCode

</td>
<td valign="top">

Valid values: `true` or `false`. If true, the response status gets assigned to the new response message, which is indicated by the AssignTo variable. This element is applicable only for HTTP request and not for response.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="[request|response]">
>     <StatusCode>[false|true]</StatusCode>
>   </Copy>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets <StatusCode\> to "true", which copies the status code from the default response object to a new custom response object:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="response">
>     <StatusCode>true</StatusCode>
>   </Copy>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="response">CustomReq</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

Reason Phrase

</td>
<td valign="top">

If true, the reason phrase of the response gets assigned to the new response message, which is indicated by the AssignTo variable. This element is applicable only for HTTP request and not for response.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="[request|response]">
>     <ReasonPhrase>[false|true]</ReasonPhrase>
>   </Copy>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets <ReasonPhrase\> to "true", which causes <Copy\> to copy the reason phrase from the default response to a custom response object:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Copy source="response">
>     <ReasonPhrase>true</ReasonPhrase>
>   </Copy>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="response">CustomReq</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Remove \(Optional\)

</td>
<td valign="top">

Headers

</td>
<td valign="top">

Removes HTTP headers from the variable specified in the <AssignTo\>element. To remove all the headers, specify `<Remove><Headers/></Remove>`.

To remove specific headers, provide the header name in the name attribute as below:

`<Remove>`

`<Headers>`

`<Header name="headerA"/>`

`<Header name="headerB"/>`

`</Headers>`

`</Remove>`

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Remove>
>     <!-- Can also be an empty array (<Headers/>) -->
>     <Headers>
>       <Header name="header_name">header_value</Header>
>       ...
>     </Headers>
>   </Remove>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example removes the `temp` header from the request:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Remove>
>     <Headers>
>       <Header name="temp"/>
>     </Headers>
>   </Remove>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="false" transport="http" type="request"/>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

QueryParams

</td>
<td valign="top">

Removes the query parameters.

Note that the QueryParams are removed only when the AssignTo type is request and the HTTP verb is GET. To remove all query parameters, specify `<Remove><QueryParams/></Remove>`.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Remove>
>     <!-- Can also be an empty array (<QueryParams/>) -->
>     <QueryParams>
>       <QueryParam name="queryparam_name">queryparam_value</QueryParam>
>       ...
>     </QueryParams>
>   </Remove>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example removes all query parameters from the request:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Remove>
>       <QueryParams/>
>   </Remove>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="false" transport="http" type="request"/>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

FormParams

</td>
<td valign="top">

Removes the form parameters.

Note that the FormParams are removed only when the contentType of AssignTo is application/x-www-formurlencoded. To remove all query parameters, specify `<Remove><FormParams/></Remove>`.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Remove>
>     <!-- Can also be an empty array (<FormParams/>) -->
>     <FormParams>
>       <FormParam name="formparam_name">formparam_value</FormParam>
>       ...
>     </FormParams>
>   </Remove>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example removes three form parameters from the request:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Remove>
>     <FormParams>
>       <FormParam name="form_param_1"/>
>       <FormParam name="form_param_2"/>
>       <FormParam name="form_param_3"/>
>     </FormParams>
>   </Remove>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="false" transport="http" type="application/x-www-form-urlencoded"/>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

Payload

</td>
<td valign="top">

Valid values: `true` or `false`. If true, the payload is cleared.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Remove>
>     <Payload>[false|true]</Payload>
>   </Remove>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets <Payload\> to "true" so that the request payload is cleared:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Remove>
>     <Payload>true</Payload>
>   </Remove>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="false" transport="http" type="request"/>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Add \(Optional\)

</td>
<td valign="top">

Headers

</td>
<td valign="top">

Adds the headers in the variable specified in the <AssignTo\> element.

Note that the empty header `<Add><Headers/></Add>` does not add any header. The same holds true for QueryParams and FormParams.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Add>
>     <Headers>
>       <Header name="header_name">header_value</Header>
>       ...
>     </Headers>
>   </Add>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example adds the temp header to the request message, and assigns the value of the request.temp flow variable to that header:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Add>
>     <Headers>
>       <Header name="temp">{request.temp}</Header>
>     </Headers>
>   </Add>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="false" transport="http" type="request"/>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

QueryParams

</td>
<td valign="top">

Adds the query parameters.

You can use query parameters only when the message type is Request and the HTTP verb is GET.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Add>
>     <QueryParams>
>       <QueryParam name="queryparam_name">queryparam_value</QueryParam>
>       ...
>     </QueryParams>
>   </Add>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example adds the query parameter `tempParam` to the request and assigns the value [82\] to it:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Add>
>     <QueryParams>
>       <QueryParam name="tempParam">82</QueryParam>
>     </QueryParams>
>   </Add>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="false" transport="http" type="request"/>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

FormParams

</td>
<td valign="top">

Adds the form parameters and the contentType of message is changed to application/x-www-form-urlencoded.

You can use form parameters only when the message type is Request and the HTTP verb is POST. Additionally, you should meet one \(or both\) of the following criteria:

-   Set the Form data to some value, or `'''` \(empty string\). For example, with `curl`, add `-d ""` to your request.
-   Set the `Content-Length` header to [0\] if there is no data in the original request; otherwise, set it to the current length in bytes. For example, with `curl`, add `-H "Content-Length: 0"` to your request.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Add>
>     <FormParams>
>       <FormParam name="formparam_name">formparam_value</FormParam>
>       ...
>     </FormParams>
>   <AssignTo createNew="[true|false]" transport="http"
>     type="[request|response]">destination_variable_name</AssignTo>
>   </Add>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example adds a single form parameter \(`"answer"`\) and a static value \(`"42"`\) to the request:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Add>
>     <FormParams>
>       <FormParam name="answer">42</FormParam>
>     </FormParams>
>   </Add>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo transport="http" type="request"></AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top" rowspan="9">

Set \(Optional\)

</td>
<td valign="top">

Headers

</td>
<td valign="top">

Sets or overwrites the HTTP headers in the variable specified in the <AssignTo\> element.

Note that the empty header `<Set><Headers/></Set>` does not set any header. The same holds true for QueryParams and FormParams.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <Headers>
>       <Header name="header_name">header_value</Header>
>       ...
>     </Headers>
>   </Set>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets the user-agent header to the value of the request.header.user-agent variable:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Headers>
>     <Header name="user-agent">{request.header.user-agent}</Header>
>   </Headers>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="response"/>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

QueryParams

</td>
<td valign="top">

Sets or overwrites the query parameters in a request.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <QueryParams>
>       <QueryParam name="queryparam_name">queryparam_value</QueryParam>
>       ...
>     </QueryParams>
>   </Set>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets the "temp" query parameter to the value of the request.header.temp variable:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <QueryParams>
>     <QueryParam name="temp">{request.header.temp}</QueryParam>
>   </QueryParams>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

FormParams

</td>
<td valign="top">

Sets or overwrites the form parameters and the contentType of message changes to application/x-www-form-urlencoded.

You can use form parameters only when the message type is Request and the HTTP verb is POST.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <FormParams>
>       <FormParam name="formparam_name">formparam_value</FormParam>
>       ...
>     </FormParams>
>   </Set>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets a form parameter called "tempparam" to the value of the request.header.tempparam variable in a new custom request:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <FormParams>
>     <FormParam name="tempparam">{request.header.tempparam}</FormParam>
>   </FormParams>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="request">CustomReq</AssignTo>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

Payload

</td>
<td valign="top">

Enter the payloads of type json, xml, plain text, and so on, within this element.

Following are the attributes \(optional\) of <Payload\>:

-   `contentType`: It is a string which if specified, assigns the value of `contentType` to the Content-Type HTTP header.
-   `variablePrefix`: It is a character which optionally specifies the leading delimiter on a flow variable. The default is `"{"`.
-   `variableSuffix`: It is a character which optionally specifies the trailing delimiter on a flow variable. The default is `"}"`.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <Payload contentType="content_type" variablePrefix="prefix"
>         variableSuffix="suffix">new_payload</Payload>
>   </Set>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example sets a JSON payload:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <Payload contentType="application/json">
>       {"name":"foo", "type":"bar"}
>     </Payload>
>   </Set>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
> </AssignMessage>
> ```

> ### Note:  
> If the payload content is of the type XML, and gets changed unexpectedly during API proxy execution, please wrap it in <!\[CDATA\[`…` \]\]\> element.
> 
> This way, you can ensure that the payload content is treated as a string and thereby it is not getting processed by the API Proxy back-end system as XML.
> 
> You can still process the dynamic data like query parameters or variables within the content wrapped in CDATA.
> 
> > ### Sample Code:  
> > ```
> > <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
> >               <Set>
> >                   <Payload contentType="text/xml"><![CDATA[
> >                      .
> >                      . <!—xml content here
> >                     .
> >                  ]]>
> >                 </Payload>
> >              </Set>
> > </AssignMessage>
> > 
> > ```



</td>
</tr>
<tr>
<td valign="top">

Version

</td>
<td valign="top">

Sets the HTTP version on a request.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <Version>[1.0|1.1|{variable}]</Verb>
>   </Set>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example uses a variable in curly braces to set the version number:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <Version>{my_version}</Version>
>   </Set>
>  <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="request"/>
> </AssignMessage>
> ```
> 
> The content of <Version\>, wrapped in curly braces is a message template and is replaced at runtime with the value of the referenced variable.



</td>
</tr>
<tr>
<td valign="top">

Reason Phrase

</td>
<td valign="top">

Sets the reason phrase only when AssignTo type is response. This is generally used in combination with the status code for debugging.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <ReasonPhrase>reason_for_error or {variable}</ReasonPhrase>
>   </Set>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example uses a variable to populate a reason phrase:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <ReasonPhrase>{calloutresponse.reason.phrase}</ReasonPhrase>
>   </Set>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="response"/>
> </AssignMessage>
> ```
> 
> The content of <ReasonPhrase\>, wrapped in curly braces is a message template and is replaced at runtime with the value of the referenced variable.



</td>
</tr>
<tr>
<td valign="top">

Status Code

</td>
<td valign="top">

Sets the status code only when AssignTo type is response.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <StatusCode>HTTP_status_code or {variable}</StatusCode>
>   </Set>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example uses a variable to populate a status code:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <StatusCode>{calloutresponse.status.code}</StatusCode>
>   </Set>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="response"/>
> </AssignMessage>
> ```
> 
> The content of <StatusCode\>, wrapped in curly braces is a message template and is replaced at runtime with the value of the referenced variable.



</td>
</tr>
<tr>
<td valign="top">

Verb

</td>
<td valign="top" rowspan="2">

Sets the HTTP verb and path only when AssignTo type is request.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <Verb>[GET|POST|PUT|PATCH|DELETE|{variable}]</Verb>
>   </Set>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example uses a variable to populate a verb:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <Set>
>     <Verb>{my_variable}</Verb>
>   </Set>
>  <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="request"/>
> </AssignMessage>
> ```
> 
> The content of <Verb\>, wrapped in curly braces is a message template and is replaced at runtime with the value of the referenced variable.



</td>
</tr>
<tr>
<td valign="top">

Path

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

AssignVariable

</td>
<td valign="top">

Name \(Required\)

</td>
<td valign="top">

It is a string that specifies the name of the variable. If the variable named in `AssignVariable` does not exist, the policy creates one with that name.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <AssignVariable>
>     <Name>variable_name</Name>
>   </AssignVariable>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example specifies the destination variable as `var` and sets it to the value `"83"`:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <AssignVariable>
>     <Name>var</Name>
>     <Value>83</Value>
>   </AssignVariable>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignTo createNew="true" transport="http" type="request"/>
> </AssignMessage>
> ```
> 
> If `myvar` does not exist, `AssignVariable` creates it.



</td>
</tr>
<tr>
<td valign="top">

Ref \(Optional\)

</td>
<td valign="top">

Reference that assigns value \(as a flow variable and not a string variable\) to the variable.

If you want to assign a literal string value to the variable, use the `Value` element instead.

-   Do this \(no brackets\): `<Ref>client.host</Ref>`
-   Do NOT do this \(brackets\): `<Ref>{client.host}</Ref>`

Define the default value for the destination flow variable by using `<Value>` along with `<Ref>`. If the flow variable specified by `<Ref>` does not exist, is not readable, or is null, then the value of `<Value>` is assigned to the destination flow variable instead.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <AssignVariable>
>     <Name>variable_name</Name>
>     <Ref>source_variable</Ref>
>   </AssignVariable>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example assigns the value of the flow variable `request.header.temp` to the destination flow variable `var` and the value of the query parameter `test` to the `test` variable:
> 
> ```
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
>   <AssignVariable>
>     <Name>var</Name>
>     <Ref>request.header.temp</Ref>
>   </AssignVariable>
>   <AssignVariable>
>     <Name>test</Name>
>     <Ref>request.queryparam.test</Ref>
>   </AssignVariable>
>  <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>  <AssignTo createNew="true" transport="http" type="request"/>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

Template \(Optional\)

</td>
<td valign="top">

It is a string that specifies the message template, which support functions like escaping and case conversion.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <AssignVariable>
>     <Template>message_template</Template>
>   </AssignVariable>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example uses the message template syntax to concatenate two context variables with a literal string \(hyphen\) between them:
> 
> ```
> <AssignMessage name='template-1'>
>   <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>   <AssignVariable>
>     <Name>my_destination_variable</Name>
>     <Value>BADDBEEF</Value>
>     <Template>{system.uuid}-{messageid}</Template>
>   </AssignVariable>
> </AssignMessage>
> ```



</td>
</tr>
<tr>
<td valign="top">

Value \(Optional\)

</td>
<td valign="top">

It is a string that specifies the value of the variable.

If you use a combination of the <Value\> and <Ref\> elements, <Value\> acts as default. If <Ref\> is not specified or is unresolvable, this literal string value is assigned to the variable.

> ### Sample Code:  
> Syntax
> 
> ```
> <AssignMessage async="false|true" continueOnError="[true|false]" enabled="[true|false]" xmlns='http://www.sap.com/apimgmt'>
>   <AssignVariable>
>     <Name>variable_name</Name>
>     <Value>variable_value</Value>
>   </AssignVariable>
> </AssignMessage>
> ```

> ### Sample Code:  
> Example
> 
> The following example assigns the value of the flow variable `request.header.temp` to the destination flow variable `var` and the value of the query parameter `test` to the `test` variable:
> 
> ```
> <AssignMessage name="assignvariable-2">
>   <AssignVariable>
>     <Name>var</Name>
>     <Value>ErrorOnCopy</Value>
>     <Ref>request.header.temp</Ref>
>   </AssignVariable>
>   <AssignVariable>
>     <Name>test</Name>
>     <Value>ErrorOnCopy</Value>
>     <Ref>request.queryparam.test</Ref>
>   </AssignVariable>
> </AssignMessage>
> ```
> 
> If either assignment fails, the value "ErrorOnCopy" is assigned to the variable.



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

UnresolvedVariable

</td>
<td valign="top">

A flow variable referenced in the policy does not exist. Be sure that the variable is in scope - some of the built-in variables are only available in certain flow contexts.

</td>
</tr>
<tr>
<td valign="top">

VariableOfNonMsgType

</td>
<td valign="top">

The policy tried to assign a value to a non-message type variable. Message type variables include request and response. They also can be custom variables that are of type message. You might see this in the <Copy\> element if you set the source attribute to a variable that is not of type Message.

</td>
</tr>
<tr>
<td valign="top">

SetVariableFailed

</td>
<td valign="top">

The policy was not able to set a variable. See the fault string for the name of the unresolved variable

</td>
</tr>
<tr>
<td valign="top">

InvalidIndex

</td>
<td valign="top">

The index must be greater than zero when specified in the Copy and Remove operations. For example, a query parameter can have multiple values. This error occurs if you specify an invalid index, such as 0 or a negative number.

</td>
</tr>
<tr>
<td valign="top">

InvalidVariableName

</td>
<td valign="top">

The policy schema validation failed because a variable name is invalid.

</td>
</tr>
<tr>
<td valign="top">

InvalidPayload

</td>
<td valign="top">

A payload specified in the policy is invalid.

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

The \[prefix\] is assignmessage.

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

assignmessage.AM-SetResponse.failed = true

</td>
</tr>
<tr>
<td valign="top">

fault.name = \[error\_name\]

</td>
<td valign="top">

\[error\_name\] is the specific error name to check for as listed in the table above.

</td>
<td valign="top">

fault.name = "UnresolvedVariable"

</td>
</tr>
</table>

Following is an example of an error response:

> ### Sample Code:  
> ```
> {  
>    "fault":{  
>       "detail":{  
>          "errorcode":"steps.assignmessage.VariableOfNonMsgType"
>       },
>       "faultstring":"AssignMessage[AM-SetResponse]: value of variable is not of type Message"
>    }
> }
> ```

Following is an example of a fault rule:

> ### Sample Code:  
> ```
> <faultrule name="VariableOfNonMsgType"></faultrule><FaultRule name="Assign Message Faults">
>     <Step>
>         <Name>AM-CustomNonMessageTypeErrorResponse</Name>
>         <Condition>(fault.name Matches "VariableOfNonMsgType") </Condition>
>     </Step>
>     <Step>
>         <Name>AM-CustomSetVariableErrorResponse</Name>
>         <Condition>(fault.name = "SetVariableFailed")</Condition>
>     </Step>
>     <Condition>(assignmessage.failed = true) </Condition>
> </FaultRule>
> ```

**Related Information**  


[Access Entity](access-entity-e5837f4.md "")

