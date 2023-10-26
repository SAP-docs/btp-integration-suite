<!-- loio0ae4a78909c4479cbc3cc414250919de -->

# HTTPS Sender Adapter



## Context

You use the HTTPS sender adapter to communicate with receiver systems using HTTPS message protocol.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](../IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Supported Header:

> ### Remember:  
> The adapter adds the headers that follow and you can't add them manually. The adapter removes any custom header that you send with the prefix `camel` even if you add them as *Allowed Headers* in the *Runtime Configuration* of the integration flow.
> 
> Also, any query parameter \(with a key and value\) that you send to the adapter is automatically converted to a header. So, if you send a query and a header with same name, the adapter appends the query to the header.

-   SapAuthenticatedUserName

    Contains the user name of the client that calls the integration flow.


The following HTTPS request headers for the sample HTTPS endpoint `https://test.bsn.neo.ondemand.com/http/hello?abcd=1234` are added to exchange headers for further processing in integration flow:

-   **CamelHttpUrl**

    Refers to the complete URL called, without query parameters.

    For example, `CamelHttpUrl=https://test.bsn.neo.ondemand.com/http/hello`.

-   **CamelHttpQuery**

    Refers to the query string that is contained in the request URL.

    In the context of a receiver adapter, this header can be used to dynamically change the URI to be called.

    For example, `CamelHttpQuery=abcd=1234`.

-   **CamelHttpMethod**

    Refers to the incoming method names used to make the request. These methods are *GET*, *POST*, *PUT*, *DELETE*, and so on.

-   **CamelServletContextPath**

    Refers to the path specified in the address field of the channel.

    For example, if the address in the channel is*/abcd/1234*, then *CamelServletContextPath* is */abcd/1234*.


> ### Note:  
> -   Adapter tracing is supported for HTTPS adapter. For more information, see [Message Processing Log - Adapter Tracing](../Operations/message-processing-log-adapter-tracing-a9db4ea.md).
> -   When you deploy an integration flow with HTTPS sender adapter, you can see the endpoint information of this integration flow in *Manage Integration Content* section of operations view.

When you have created a sender channel with HTTPS adapter, you can configure the following attributes:



### Connection

**Parameters of the HTTPS Sender Adapter**


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

Enter the URL of the HTTP system to connect to.

> ### Note:  
> -   Use the following pattern: `http://<host>:<port>/http` . This should be appended by the unique address specified in the channel.
> -   The field value supports these characters **~, -, . , $** and **\*** .
> -   The *Address* field should start with '/ ' and can contain alphanumeric values, '\_' and '/ '. For example a valid address is */test/123*.
> -   In the example mentioned above, you can use **~** only for the address part which succeeds */test/*
> -   You can use **$** only at the beginning of the address after **/**.
> -   You cannot begin address with**.**, **\-** or **~**. Alphanumeric value or**\_** must succeed these characters.
> -   You can use **\*** only at the extreme end of the address and no characters are allowed after **\***. A **\*** can only be preceded with**/**.
> -   If you are using **/\***, it implies that URI containing the prefix preceding the **/\*** is supported. For example. if the address is */Customer/\** then URIs supported are *http://<host\>:<port\>/http/Customer/<Any-url\>*.
> -   If you are using **/path /\***, then no other integration flows with the addresses `/path/any-URL` or `/path/any-URL/text` can be deployed across the tenant.
> -   URIs are case insensitive. So, *http://<host\>:<port\>/http/test* and *http://<host\>:<port\>/http/Test* is treated as same.



</td>
</tr>
<tr>
<td valign="top">

*Authorization* 

</td>
<td valign="top">

Specifies the authorization option for the sender.

You can select one of the following options:

-   *Client Certificate*: Sender authorization is checked on the tenant by evaluating the subject/issuer distinguished name \(DN\) of the certificate \(sent together with the inbound request\). You can use this option together with the following authentication option: *Client-certificate authentication \(without certificate-to-user mapping\)*.

-   *User Role*: Sender authorization is checked based on roles defined on the tenant for the user associated with the inbound request. You can use this option together with the following authentication options:

    -   *Basic authentication* \(using the credentials of the user\)

        The authorizations for the user are checked based on user-to-role assignments defined on the tenant.

    -   *Client-certificate authentication and certificate-to-user mapping*

        The authorizations for the user derived from the certificate-to-user mapping are checked based on user-to-role assignments defined on the tenant.



Depending on your choice, you can also specify one of the following properties:

-   *Client Certificate Authorization*

    Allows you to select one or more client certificates \(based on which the inbound authorization is checked\).

    Choose *Add* to add a new certificate for inbound authorization for the selected adapter. You can then select a certificate stored locally on your computer. You can also delete certificates from the list.

    For each certificate, the following attributes are displayed: *Subject DN* \(information used to authorize the sender\) and *Issuer DN* \(information about the certificate authority that issues the certificate\).

-   *User Role*

    Allows you to enter a role based on which the inbound authorization is checked.

    The role *ESBMessaging.send* is provided by default. It is a predefined role provided by SAP which authorizes a sender system to process messages on a tenant.




</td>
</tr>
<tr>
<td valign="top">

*CSRF Protected* 

</td>
<td valign="top">

This option prevents Cross-Site Request Forgery \(CSRF\), which is a malicious online attack. Such attacks exposes user content without their authorization.

> ### Note:  
> -   During an inbound HTTPS communication, if the sender adapter receives a GET or HEAD request to fetch the CSRF token value and you have the enabled CSRF Protected then the adapter will return the CSRF token and stop processing the message further.
> 
> -   Include X-CSRF-Token in the HTTP header field for all modifying requests and these requests are validated during runtime. If the validation fails then the server returns “HTTP 403 Forbidden” status code.



</td>
</tr>
</table>



### Conditions

The parameters in *Maximum Message Size* allows you to set a maximum size limit for processing inbound messages. All inbound messages that exceeds the configured limit are rejected and the sender receives an error message.

> ### Note:  
> The minimum allowable size limit is 1MB.

**Configure to set size limit**


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

Body Size \(in MB\)

</td>
<td valign="top">

Define the allowable size limit for processing the message body.

</td>
</tr>
</table>

Save the settings.

> ### Note:  
> -   Additional incoming request headers and URL parameters can be added to exchange headers for further processing in integration flow. You must define these headers and paramters in *Allowed Headers* list at integration flow level.
> -   Once the integration flow processing completes, the HTTPS sender adapter returns header and body to end user and sets the response code. You can use *Content Modifier* element to send back specific http response and customize the response.
> -   The sample integration flow is as shown below:![](images/HTTP3_e763f14.png)
> -   Address URLs for http endpoints across integration flow must be unique. If it is not unique then the integration flow does not start.
> -   Adapter returns the following HTTP response code:
> 
>     -   200 - Processing is successful
> 
>     -   503 - Service is not available
> 
>     -   500 - Exception during integration flow processing
> 
> 
>     Also, you can set the header *CamelHttpResponseCode* to customize the response code.
> 
> -   You can invoke the HTTP endpoints using the syntax **<Base URI\>/http/<Value of address field\>**. You can get *Base URI* value from *Services* tab in *Properties* view of a worker node.
> 
>     Atleast one integration flow with SOAP endpoint must be deployed to view details in *Services* tab.
> 
> -   You should use *Script* element to customise which headers can be sent in response to the HTTP call. It is a recommendation that you must remove internal headers and sent back only required headers.
> -   If an exception occurs during a HTTPS call, due to which the message is not processed and you have selected *Return Exception to Sender*, then the exception is sent back to the sender. For more information, see [Define Error Configuration](define-error-configuration-77d0041.md).
> -   If an exception occurs during the HTTPS call and you have not selected *Return Exception to Sender*, it throws back a message and MPL ID explaining the exception, rather than displaying the stack trace.

**Related Information**  


[Authentication and Authorization Options \(Inbound\)](../ConnectionSetup/authentication-and-authorization-options-inbound-983f2a5.md "When a client calls a server using a secure communication channel, two different kinds of checks are performed subsequently.")

[OData API](odata-api-a617d6f.md "The Cloud Integration application programming interface (API) allows you to access Cloud Integration resources, for example, monitoring data.")

[Sender-Initiated Scenario \(with HTTPS Sender Adapter\)](sender-initiated-scenario-with-https-sender-adapter-ccdb189.md "Create a simple integration scenario that is initiated by a sender (using the HTTPS sender adapter).")

[Setting Up Inbound HTTP Connections \(Integration Flow Processing\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-integration-flow-processing-neo-environment-778c7e7.md "You can use various sender adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a sender system so that the sender can send messages to Cloud Integration over the HTTP protocol.")

