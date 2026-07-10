<!-- loio9e63c015a69f4c85b3273cc566bb5633 -->

# Handling URL Redirects in an API Proxy Using Policies

**Symptom**: The API proxy URL redirects to a different target endpoint.

This topic explains how to handle URL redirects in an API proxy using policies.

Let’s say you’ve deployed a simple API proxy, wherein the target endpoint is pointing to the backend service located at the following URL:

`https://services.odata.org/V2/Northwind/Northwind.svc`

For more information on creating an API proxy, see [Different Methods of Creating an API Proxy](different-methods-of-creating-an-api-proxy-4ac0431.md).

When you click on the API proxy URL, if your browser displays the service URL instead of the proxied URL, it indicates that the service URL that you are trying to access has been moved temporarily or permanently to a new location. When this scenario occurs, Integration Suite doesn’t display the proxied URL. It instead displays the redirected URL of the backend service you provided.

You can handle this URL redirects by adding policies to your API proxy. These policies determine how URL direction is handled within Integration Suite.

In this illustration, we provide two approaches for handling URL redirects. One, wherein we use a Fault Raise policy to stop redirection when the backend service you’re trying to access is moved temporarily to a new location, and additionally send a response to the client indicating what is the new redirected URL of the service. Two, wherein we use a combination of various policies such as, Extract Variables policy, Service Callout policy, and Assign Message policy to gracefully handle the URL redirection without user intervention.



<a name="loio9e63c015a69f4c85b3273cc566bb5633__section_ybg_kbz_fnb"/>

## Stop URL Redirection Using Fault Raise Policy

Add a Fault Raise policy to your API proxy with the following configuration. Add this policy in the target endpoint \(PostFlow/Outgoing Response\).

> ### Sample Code:  
> ```
> <RaiseFault async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
> 	<!-- Defines the response message returned to the requesting client -->
> 	<FaultResponse>
> 		<Set>
> 			<!-- Sets or overwrites HTTP headers in the respone message -->
> 			<Headers/>
> 			<Payload contentType="text/plain"> Sorry for the inconvenience!
> 			The target URL that you have provided has been redirected to "{response.header.Location}". The URL redirection has been stopped due to security reasons. Please provide a target URL that doesn't redirect.</Payload> <StatusCode>500</StatusCode>
> 			<!-- sets the reason phrase of the response -->
> 			<ReasonPhrase>Server Error</ReasonPhrase>
> 		</Set>
> 	</FaultResponse>
> 	<IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
> </RaiseFault>
> 
> ```

Add a condition to indicate when this policy must execute. In our illustration, we want to execute this policy only when the backend service URL that you provided is being redirected to a new URL. We achieve this by including the following condition string:

> ### Sample Code:  
> ```
> response.status.code=307
> ```

The above condition string indicates that when the http response code received from a backend service is 307, the policy gets executed. The http response code 307 indicates that the service/resource you want access can’t be accessed from its canonical location, but can be accessed from a new temporary location.

If the above policy executes, the client would get the following response, where `{response.header.location}` would actually be replaced with the redirected URL of the backend service you provided.

> ### Sample Code:  
> ```
> Sorry for the inconvenience!
> 			The target URL that you have provided has been redirected to "{response.header.Location}". The URL redirection has been stopped due to security reasons. Please provide a target URL that doesn't redirect.
> 
> ```

Similarly, if the backend service that you want to access is permanently moved to a new location, then you change the condition string statement to `response.status.code=302`.



<a name="loio9e63c015a69f4c85b3273cc566bb5633__section_ryx_lbz_fnb"/>

## Handle URL Redirection Gracefully

Add an Extract Variables policy to your API proxy with the following configuration. Add this policy to the proxy endpoint \(PreFlow/Outgoing Response\).

> ### Sample Code:  
> ```
> <ExtractVariables async="true" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
> 	<Source>response</Source>
> 	<Header name="Location">
>       <Pattern ignoreCase="true">https://{redirectUrl}/{redirectUrlPath}</Pattern>
>      </Header>
> </ExtractVariables>
> ```

Add a condition to indicate when this policy must execute. In our illustration, we want to execute this policy only when the backend service URL that you provided is being redirected to a new URL. We achieve this by including the following condition string:

> ### Sample Code:  
> ```
> response.status.code=307
> ```

If the above policy executes, the value of the Location header tagged to the response is extracted and stored in the `redirectUrl` and `redirectUrlPath` variables. For example, if the backend service URL \(redirected URL\) you’re trying to access is `https://services.odata.org/V2/Northwind/Northwind.svc/`, then the value `services.odata.org` is stored in the `redirectUrl` variable and the value `V2/Northwind/Northwind.svc/` is stored in the `redirectUrlPath` variable.

Use the extracted `redirectUrl` and `redirectUrlPath` variables in the Service Callout policy as described further.

Add a Service Callout policy to your API proxy with the following configuration. Add this policy to the proxy endpoint \(PreFlow/Outgoing Response\).

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <ServiceCallout async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <Request clearPayload="true" variable="myRequest">
>         <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>     </Request>
>     <Response>calloutResponse</Response>
>     <HTTPTargetConnection>
>         <URL>https://{redirectUrl}/{redirectUrlPath}</URL>
>     </HTTPTargetConnection>
> </ServiceCallout>
> 
> ```

Add a condition to indicate when this policy must execute. In our illustration, we want to execute this policy only when the backend service URL that you provided is being redirected to a new URL. We achieve this by including the following condition string:

> ### Sample Code:  
> ```
> response.status.code=307
> ```

If the above policy executes, the response message received from the external service indicated in the `URL` element of the policy, is stored in the `calloutResponse` variable. For example, if the values stored in `redirectUrl` and `redirectUrlPath` variables are `services.odata.org` and `V2/Northwind/Northwind.svc/`, respectively, then the response from the URL \(redirected URL\) `https://services.odata.org/V2/Northwind/Northwind.svc/` will be stored in the `calloutResponse` variable.

In the next step, send the response message obtained from the service callout policy to the client using the Assign Message policy as shown further.

Add an Assign Message policy to your API proxy with the following configuration. Add this policy to the proxy endpoint \(PreFlow/Outgoing Response\).

> ### Sample Code:  
> ```
> 
> <AssignMessage async="false" continueOnError="false" enabled="true" xmlns='http://www.sap.com/apimgmt'>
> 	<Set>
> 		<Payload>{calloutResponse.content}</Payload>
> 	</Set>
> 	<IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
> 	<AssignTo createNew="true" type="response">response</AssignTo>
> </AssignMessage>
> ```

If the above policy executes, the client receives the response message stored in the `calloutResponse` variable.

Save the API proxy after adding the above policies. You can also create a policy template with the above policies so that you can easily attach the policy template to your API proxies to gracefully handle URL redirection. For more information on policy templates, see [Create a Policy Template](create-a-policy-template-c5d1872.md).

