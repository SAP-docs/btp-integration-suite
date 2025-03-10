<!-- loio2da452effb764b3bb28f8e0a2f5bd480 -->

# HTTP Receiver Adapter

Use the HTTP receiver adapter to communicate with target systems using HTTP message protocol.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

> ### Note:  
> -   If you want to dynamically override the configuration of the adapter, you can set the following headers before calling the HTTP adapter:
> 
>     ****
> 
> 
>     <table>
>     <tr>
>     <th valign="top">
> 
>     Header Name
>     
>     </th>
>     <th valign="top">
> 
>     Description
>     
>     </th>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     **HTTP Content-Length header**
>     
>     </td>
>     <td valign="top">
>     
>     -   The HTTP Receiver adapter works well with target systems that supports either chunked transfer encoding or rely on the existence of the HTTP Content-Length header.
>     -   The adapter automatically decompresses the received '.gzip' response, so the HTTP Content-Length header reflects the uncompressed size.
>     -   For versions 1.10 and lower, the adapter works only with target systems that support chunked transfer encoding and may not rely on the existence of the HTTP Content-Length header.
> 
> 
>     
>     </td>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     **CamelHttpUri**
>     
>     </td>
>     <td valign="top">
>     
>     -   Overrides the existing URI set directly in the endpoint.
>     -   This header can be used to dynamically change the URI to be called.
> 
> 
>     
>     </td>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     **CamelHttpQuery**
>     
>     </td>
>     <td valign="top">
>     
>     -   Refers to the query string that is contained in the request URL.
>     -   In the context of a receiver adapter, this header can be used to dynamically change the URI to be called.
> 
>         > ### Example:  
>         > `CamelHttpQuery=abcd=1234`
> 
> 
> 
>     
>     </td>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     **Content-Type**
>     
>     </td>
>     <td valign="top">
>     
>     -   SAP recommends you add content-type header that indicates type of payload before you make an HTTP outbound call.
>     -   HTTP content type that fits to the body of the request.
>     -   The content type is composed of two parts: a type and a subtype.
> 
>         For example, `image/jpeg` \(where `image` is the type and `jpeg` is the subtype\).
> 
>         > ### Example:  
>         > -   `text/plain` for unformatted text
>         > -   `text/html` for text formatted with HTML syntax
>         > -   `image/jpeg` for a jpeg image file
>         > -   `application/json` for data in JSON format to be processed by an application that requires this format
> 
>         More information on the available types: [4 The Content-Type Header Field](https://www.w3.org/Protocols/rfc1341/4_Content-Type.html)
> 
>         The list of available content types is maintained by the Internet Assigned Numbers Authority \(IANA\). For more information, see [Media Types](http://www.iana.org/assignments/media-types/media-types.xhtml).
> 
>     -   If transferring text/\* content types, you can also specify the character encoding in the HTTP header using the charset parameter.
> 
>         > ### Example:  
>         > `Content-Type: text/html; charset=utf-8`
> 
>     -   The default character encoding that will be applied for `text/*` content types depends on the HTTP version: `us-ascii` for HTTP 1.0 and `iso-8859-1` for HTTP 1.1.
> 
>     -   If you want to override the character encoding and avoid encoding issues when you use special characters, you can use the Content Modifier step and specify the `CamelCharsetName` Exchange property.
> 
>         > ### Example:  
>         > If you want to send `iso-8859-1`-encoded data to a receiver, make sure that you specify the `CamelCharsetName` Exchange property \(either header or property\) as `iso-8859-1`.
> 
> 
> 
>     
>     </td>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     **Content-Encoding**
>     
>     </td>
>     <td valign="top">
>     
>     -   HTTP content encoding that indicates the encoding used during message transport.
> 
>         > ### Example:  
>         > `gzip` for GZIP file compression.
> 
>     -   This information is used by the receiver to retrieve the media type that is referenced by the `content-type` header.
>     -   If this header is not specified, the default value `identity` \(no compression\) is used.
> 
>     More information: [Hypertext Transfer Protocol – HTTP/1.1](https://tools.ietf.org/html/rfc2616)
> 
>     The list of available content types is maintained by the Internet Assigned Numbers Authority \(IANA\). For more information, see:[HTTP Content Coding Registry](http://www.iana.org/assignments/http-parameters/http-parameters.xhtml#content-coding).
>     
>     </td>
>     </tr>
>     </table>
>     
> -   The adapter can process payloads having an attachment or MIME multipart messages that are converted to byte array via script steps. For target systems that supports chunked transfer, you need not convert the payload to a byte array.
> -   Adapter tracing is supported for HTTP adapter. For more information, see [Message Processing Log - Adapter Tracing](message-processing-log-adapter-tracing-a9db4ea.md).

Once you've created a receiver channel and selected the HTTP receiver adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the *General* tab and provide values in the fields as follows.

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

**Connection Details**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Address* 

</td>
<td valign="top">

URL of the target system that you're connecting to, for example, `https://mysystem.com`

Note that the authentication method `Client Certificate` requires the HTTPS protocol. For `Basic authentication`, it's recommended that you use the HTTPS protocol.

You can also specify HTTP parameters in the URL. However, if you select the HTTP method `POST`, parameters are sent in the body. You therefore get a warning message if you configure the parameter-value combination.

The following URL parameters are currently not allowed for technical reasons:

-   throwExceptionOnFailure
-   bridgeEndpoint
-   transferException
-   client
-   clientConfig
-   binding
-   sslContextParameters
-   bufferSize

You can dynamically configure the *Address* field of the HTTP adapter.

When you specify the *Address* field of the HTTP adapter as `${header.a}`, at runtime the value of header `a` \(as contained in the incoming message\) is written into the Camel header `CamelHttpUri`.

> ### Remember:  
> By using an `*` in the *Allowed Headers* field of the *Runtime Configuration* tab of the artifact, you allow all headers to pass through, including camel-specific headers. This action overwrites the URL set in the adapter that can lead to runtime errors. To avoid such a scenario when using an `*`, add a Content Modifier before the adapter to remove the `CamelHttpUri` header.
> 
> Also, in case you set the `CamelHttpUri` header in another process step, the *Address* field gets overwritten.

The endpoint URL that is actually used at runtime is displayed in the message processing log \(MPL\) in the message monitoring application \(MPL property `RealDestinationUrl`\). Note that you can manually configure the endpoint URL using the *Address* attribute of the adapter. However, there are several ways to dynamically override the value of this attribute \(for example, by using the Camel header `CamelHttpUri`\).

</td>
</tr>
<tr>
<td valign="top">

*Query* 

</td>
<td valign="top">

Query string that you want to send with the HTTP request.

Query strings must not be entered in the *Address* field.

This parameter can be externalized.

You can dynamically configure the *Query* field of the HTTP adapter.

When you specify the *Query* field of the HTTP adapter as `${header.a}`, at runtime the value of header `a` \(as contained in the incoming message\) is written into the Camel header `CamelHttpQuery`.

> ### Note:  
> When using HTTP Adapter in a CPI iFlow the parameters to be sent to the HTTP target are specified in the Query field. Using some special characters as parameter name or value can result into error during saving the iFlow or processing the request. The parameters with special values need to be URL encoded.
> 
> Every special character in the Query field should be URL encoded using ASCII URL Encoding Reference or similar resources that can be easily found for ASCII characters encoding.
> 
> Example
> 
> If URL request to be sent is: https://mysystem.com?param\[1\]=test+param&param\[2\]="somevalue"
> 
> then in HTTP Adapter setting it looks like:
> 
> Address : https://mysystem.com
> 
> Query : param%5B1%5D=test%2Bparam&param%5B2%5D=%22somevalue%22
> 
> Note that %5B , %5D, %2B and %22 are UTF-8 URL encoded values for special characters \[, \], + and " respectively.
> 
> Individual parameter-value pairs must be separated with an ”&” and there must be an “=” between the name of a parameter and its value as shown in previous example.
> 
> Some special characters need URL encoding as previously shown and some do not such as &.



</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

The type of proxy that you are using to connect to the target system:

-   Select *Internet* if you are connecting to a cloud system.

-   Select *On-Premise* if you are connecting to an on-premise system.

    > ### Note:  
    > If you select the *On-Premise* option, the following restrictions apply to other parameter values:
    > 
    > -   Use HTTP instead of HTTPS when specifying the virtual system url in the *Address* field.
    > 
    > -   Do not use the option *Client Certificate* for the *Authentication* parameter, as it leads to errors when performing consistency checks or during deployment.

    > ### Note:  
    > If you select the *On-Premise* option and use the SAP Cloud Connector to connect to your on-premise system, the *Address* field of the adapter references a virtual address, which has to be configured in the SAP Cloud Connector settings.

-   If you select *Manual*, you can manually specify *Proxy Host* and *Proxy Port* \(using the corresponding entry fields\).

    This option is only available if you have chosen a *Process Orchestration* product profile.




</td>
</tr>
<tr>
<td valign="top">

*Method* 

</td>
<td valign="top">

Action that the HTTP request must perform.

-   *POST*

    Requests that the receiver accepts the data enclosed in the request body.

-   *Dynamic*

    The method is determined dynamically by reading a value from a message header or property such as `${header.abc}` or `${property.abc}` during runtime.

-   *GET*

    Sends a GET request to the receiver.

-   *HEAD*

    Sends a HEAD request that is similar to a GET request but doesn't return a message body.

-   *PATCH*

    Partially updates existing resources.

-   *TRACE*

    Sends a TRACE request to the receiver that sends back the message to the caller.




</td>
</tr>
<tr>
<td valign="top">

*Send Body*

\(only if you select for *Method* the option *GET, DELETE, HEAD*, or *Dynamic*.\)

</td>
<td valign="top">

Select this checkbox if you want to send the body of the message with the request. For methods GET, DELETE, and HEAD, the body isn't sent by default because some HTTP servers don't support this function.

</td>
</tr>
<tr>
<td valign="top">

*Expression*

\(only if you select for *Method* the option *Dynamic*.\)

</td>
<td valign="top">

The expression field allows you to enter a simple expression that specifies the HTTP method for the HTTP call . For example, you can define that the method is determined dynamically by reading a value from a message header or property such as `${header.abc}` or `${property.abc}`. If the header or property doesn’t exist or its value is empty, the **POST** method is used by default.

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Defines how the tenant \(as the HTTP client\) authenticates itself against the receiver.

You can select one of the following authentication methods:

-   *None*

    When not to use any authentication can include, but not limited to, the following cases:

    -   If the target system that you want to communicate doesn't require any authentication.

    -   If you want to set an authorization header via a Content Modifier step before the adapter.

    -   If you want to set an authorization header via a Script step before the adapter.


-   *Basic*

    The tenant authenticates itself against the receiver using user credentials \(user name and password\).

    It's a prerequisite that user credentials are specified in a Basic Authentication artifact and deployed on the related tenant.

-   *Principal Propagation* – only if the *Proxy Type* is *On-premise*.

    The tenant authenticates itself against the receiver by forwarding the principal of the inbound user to the cloud connector, and from there to the back end of the relevant on-premise system.

    Follow the steps to configure technical user in Cloud Foundry:

    -   Add a Certificate to Subaccount - Create a new service instance using the Process Integration Runtime service with an Integration Flow plan. Once the instance is created, generate a new service key. Select key type as External Certificate from the dropdown. In the External Certificate, provide the X590 public certificate. Once the service key is created, the service key will generate a Client ID, which will be used as a technical user.
    -   Configuration in the Cloud Connector - Cloud Connector should read the technical user principal and add it as Common Name \(CN\) in the certificate that is generated by Cloud Connector. To read the technical user principal there are two configuration options:
        1.  Read the principal using the subject pattern \($\{client\_id\}\).
        2.  In case of migration from Neo to Cloud Foundry and you don't want to change existing mapping in the *On-premise* system, then you can read the client\_id and map it against the actual user that is mapped in the *On-premise* system.

            For example: In the *On-premise* system if you have mapped a string MIKE to a business user BSR\_USA, then in Cloud Connector in the condition, provide the pattern $\{client\_id\} and in the value provide the client id generated in CPI subaccount, In the subject pattern provide the string MIKE.


    -   Map the Client ID to the actual user in the *On-premise* system.

    Technical user *Principal Propagation* is supported from the Cloud Connector version 2.15 for Cloud Foundry.

    > ### Remember:  
    > When you want to use Principal Propagation as the authentication method to connect with an on-premise system, don't pass any authorization headers. Follow the approach recommended by SAP BTP Connectivity. See: [Authentication to the On-Premise System](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/67b0b94f09f2446598787eea0855e56b.html).

    > ### Note:  
    > The token for principal propagation expires after 30 minutes. If it takes longer than 30 minutes to process the data between the sender and receiver channel, the token for principal propagation expires, which leads to errors in message processing.

-   *OAuth2 Client Credentials* – Use this grant type to access web resources by authorizing the client application to perform required actions on behalf of a user. For more information, see [Deploying an OAuth2 Client Credentials Artifact](deploying-an-oauth2-client-credentials-artifact-801b106.md).

    > ### Remember:  
    > If the OAuth2 authentication URL that you're going to use is that of an on-premise system, the token fetch fails. You can overcome this issue using a workaround. Use an HTTP Receiver Adapter to fetch the token from your on-premise system and set the token as an authorization header in a Groovy Script step.


Enabled only if you choose *Proxy Type* as *Internet*.

-   *OAuth2 SAML Bearer Assertion*

    If you've chosen this option, the identity of the logged-in user associated with the sender application or a dedicated technical user is forwarded from the sender account to the receiver account. For more information, see [Deploying an OAuth2 SAML Bearer Assertion](deploying-an-oauth2-saml-bearer-assertion-3ee6582.md).

-   *Client Certificate*

    The tenant authenticates itself against the receiver using a client certificate.

    It's a prerequisite that the required key pair is installed and added to a keystore. This keystore has to be deployed on the related tenant. The receiver side has to be configured appropriately.

    > ### Note:  
    > You can externalize all attributes related to the configuration of the authentication option. This includes the attributes with which you specify the authentication option as such, as well as all attributes with which you specify further security artifacts that are required for any configurable authentication option \(*Private Key Alias* or *Credential Name*\).
    > 
    > Apply **one** of the following recommendations when externalizing such attributes.
    > 
    > -   Externalize **all attributes** related to the configuration of all options, for example, *Authentication* and *Credential Name* and *Private Key Alias*.
    > 
    > -   Externalize only one of the following attributes: *Private Key Alias* **or** *Credential Name*.
    > 
    > 
    > **Avoid incomplete externalization**, for example, only externalizing the attribute for the *Authentication* parameter but not the related *Credential Name* parameter. In such cases, the integration flow configuration \(based on the externalized parameters\) cannot work properly.
    > 
    > The reason for this is the following: If you have externalized the *Authentication* parameter and only the *Private Key Alias* parameter \(but not *Credential Name*\), all authentication options in the integration flow configuration dialog \(*Basic*, *Client Certificate*, and *None*\) are selectable in a dropdown list. However, if you now select *Basic* from the dropdown list, no *Credential Name* can be configured.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if you select for *Authentication* the option *Basic*, *OAuth2 Client Credentials*, or *OAuth2 SAML Bearer Assertion*\)

</td>
<td valign="top">

Identifies the *User Credential* artifact that contains the credentials \(user name and password\) for the *Basic* authentication. For *OAuth2 SAML Bearer Assertion* type authentication provides the OAuth2 Credential artifact name. For more information see, [Deploying an OAuth2 Client Credentials Artifact](deploying-an-oauth2-client-credentials-artifact-801b106.md).

You can dynamically configure the *Credential Name* property by specifying either a header or a parameter name in one of the following ways: `${header.headername}` or `${parameter.parametername}`. As an example, you can use a *Script* step before the adapter where you look up the *User Credentials*`Authorization`. The HTTP adapter then uses this header in the HTTP request.

Although you can configure this feature, it is not supported when using the corresponding integration content with the SAP Process Orchestration \(SAP PO\) runtime in releases lower than SAP PO 7.5 SP5.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if you select *Client Certificate* for authentication\)

</td>
<td valign="top">

Enter the private key alias that enables the system to fetch the private key from keystore for authentication.

> ### Restriction:  
> The values `true` and `false` aren't supported for this field.



</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)* 

</td>
<td valign="top">

Maximum time that the tenant waits for a response before terminating message processing.

The default value is 60000 milliseconds \(1 minute\).

Note that the timeout setting has no influence on the Transmission Control Protocol \(TCP\) timeout if the receiver or any additional component interconnected between the Cloud Integration tenant and the receiver has a lower timeout. For example, consider that you have configured a receiver channel timeout of 10 minutes and there is another component involved with a timeout of 5 minutes. If nothing is transferred for a period of time, the connection will be closed after the fifth minute. In HTTP communication spanning multiple components \(for example, from a sender, through the load balancer, to a Cloud Integration tenant, and from there to a receiver\), the actual timeout period is influenced by each of the timeout settings of the individual components that are interconnected between the sender and receiver \(to be more exact, of those components that can control the TCP session\). The component or device with the lowest number set for the idle session timeout will determine the timeout that will be used.

</td>
</tr>
<tr>
<td valign="top">

*Throw Exception on Failure* 

</td>
<td valign="top">

By default, the option is enabled. This option throws an exception when there are failed HTTP responses from the remote server. If there are failed HTTP responses, then the message processing fails too.

To receive the exception and yet continue with the message processing of the integration scenario, disable the option.

This option allows you to receive all responses irrespective of the HTTP status code. The failure responses don't include other failure scenarios like timeout, network, or handshake issues.

> ### Note:  
> If you use the HTTP Receiver adapter in the *End Message Event* and enable this option, the status shown for the message process log is *Completed*.



</td>
</tr>
<tr>
<td valign="top">

*Attach Error Details on Failure*

\(Only if *Throw Exception on Failure* is enabled\)

</td>
<td valign="top">

By default, the option is enabled. This option enables the creation of attachments for request header, response headers, and response body when the message processing fails.

Having these attachments during message processing failures can be unneccesary as it leads to persistence of attachments that doesn't help. Especially, if multiple message processing failures occurs, you have attachments piled up for each failure. If you don't require the attachments for failure scenarios, disable the option. Though you disable the creation of attachments, the content of the same are added to the message processing logs.

If you're using older versions of the adapter where you don't see the option, define the property `SAP.DisableAttachments.HTTP` in the message exchange with the value `true`.

</td>
</tr>
</table>

**Header Details**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Request Headers* 

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), that you want to send to the target system. By default, no custom headers are sent. Alternatively, use an `*` to send all custom headers to the target system. Alternatively, you can dynamically pass on the values by defining a property that includes a list of headers.

> ### Remember:  
> Use an `*` separately. If you use an `*` and custom header together that are separated by a pipe \(|\), only the custom header is considered.
> 
> You must have defined the custom headers in the previous flow steps like content modifiers or scripts before you mention them in the HTTP Receiver Adapter.

The adapter doesn't support regular expressions like `SAP*`.

All Camel-specific headers \(that starts with `camel` or `org.apache.camel`\) and the below listed HTTP protocol headers are excluded even if you specify them.

-   content-length

-   host

-   cache-control

-   connection

-   pragma

-   trailer

-   transfer-encoding

-   upgrade

-   via

-   warning




</td>
</tr>
<tr>
<td valign="top">

*Response Headers* 

</td>
<td valign="top">

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an `*` to receive all the headers from the target system, which is also the default value.

</td>
</tr>
</table>

> ### Note:  
> If integration flows are OData API artifacts, you can save the integration flow and deploy the OData API.

**Related Information**  


[Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md "")

[Dynamic Parameters \(Example\)](dynamic-parameters-example-5705f2b.md)

[Script Example for Exception Handling in HTTP Receiver](script-example-for-exception-handling-in-http-receiver-a443efe.md "You can use the Script step to identify exceptions that arise when sending messages using the HTTP receiver adapter.")

[Setting Up Principal Propagation \(Example Scenario\)](../40-RemoteSystems/setting-up-principal-propagation-example-scenario-34eff84.md "Use principal propagation to forward the principal (identity of a user) across several connections in a complex system landscape.")

