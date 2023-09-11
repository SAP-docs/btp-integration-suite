<!-- loio018aa88b6d284ca2b8476b6e6053cfeb -->

# Configure the IDoc Receiver Adapter

The IDoc receiver adapter enables SAP Integration Suite to send Intermediate Document \(IDoc\) messages to a receiver.

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

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



<a name="loio018aa88b6d284ca2b8476b6e6053cfeb__section_ern_c21_sgb"/>

## Supported Headers

-   SOAPAction Header

    This header is part of the Web service specification.


The IDoc receiver adapter sends a request and gets an XML response. This response is standardized. It has the same structure for all IDocs, with the exception of the type.

The following specific headers are set by the IDoc receiver adapter.

-   SapIDocType

-   SapIDocTransferId

-   SapIDocDbId

-   SapMessageId


More information: [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)



<a name="loio018aa88b6d284ca2b8476b6e6053cfeb__section_jrh_b21_sgb"/>

## Configuring the Adapter

Once you have created a receiver channel and selected the IDoc adapter, you can configure the following attributes.

The *General* tab shows general information such as the adapter type, its direction \(sender or receiver\), the transport protocol, and the message protocol.

**Connection**


<table>
<tr>
<th valign="top">

Parameters



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

Endpoint address on which Cloud Integration posts the outbound message, for example `http://<host>:<port>/payment`.

You can dynamically configure this field by entering an expression such like `${header.a}` or `${property.a}`, depending on whether you like to use a header or an Exchange property for dynamic configuration.

If you do that, at runtime the value of \(header or exchange property\)`a`, as contained in the incoming message, will be written into the Camel header `CamelDestinationOverrideUrl` and will be used to send the message to.

Also in case the `CamelDestinationOverrideUrl` header has been set by another process step \(for example, a Content Modifier\), its value will be overwritten.

The endpoint URL that is actually used at runtime is displayed in the message processing log \(MPL\) in the message monitoring application \(MPL property `RealDestinationUrl`\). Note that you can manually configure the endpoint URL using the *Address* attribute of the adapter. However, there are several ways to dynamically override the value of this attribute \(for example, by using the Camel header `CamelHttpUri`\).



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

    Furthermore, with the parameter *URL to WSDL* you can specify a Web Service Definition Language \(WSDL\) file defining the WS provider endpoint \(of the receiver\). You can specify the WSDL by either uploading a WSDL file from your computer \(option *Upload from File System*\) or by selecting an integration flow resource \(which needs to be uploaded in advance to the *Resources* view of the integration flow\).

    This option is only available if you have chosen a *Process Orchestration* product profile.




</td>
</tr>
<tr>
<td valign="top">

*IDoc Content Type*



</td>
<td valign="top">

There are the following options:

*Application/x-sap.doc*

-   Allows only single IDoc record for each request.

-   Enables message sequencing.

-   Enables Exactly-Once processing.

    > ### Note:  
    > Enables Exactly-Once processing in the backend, if the header `SapMessageId` is set.


*Text/XML*

-   Allows multiple IDoc records for each request.



</td>
</tr>
<tr>
<td valign="top">

*Authentication* 



</td>
<td valign="top">

You can select one of the following authentication methods:

-   *Basic*

    The tenant authenticates itself against the receiver using user credentials \(user name and password\).

    It is a prerequisite that user credentials are specified in a *User Credentials* artifact and deployed on the related tenant. Enter the name of this artifact in the *Credential Name* field of the adapter.

-   *Client Certificate*

    The tenant authenticates itself against the receiver using a client certificate.

    This option is only available if you have selected *Internet* for the *Proxy Type* parameter.

    It is a prerequisite that the required key pair is installed and added to a keystore. This keystore has to be deployed on the related tenant. The receiver side has to be configured appropriately.

-   *None*
-   *Principal Propagation*

    The tenant authenticates itself against the receiver by forwarding the principal of the inbound user to the cloud connector, and from there to the back end of the relevant on-premise system.

    > ### Remember:  
    > When you want to use Principal Propagation as the authentication method to connect with an on-premise system, don't pass any authorization headers. Follow the approach recommended by SAP BTP Connectivity. See: [Authentication to the On-Premise System](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/67b0b94f09f2446598787eea0855e56b.html).

    > ### Note:  
    > This authentication method can only be used with the following sender adapters: HTTP, SOAP, IDoc, AS2.

    > ### Note:  
    > Note that the token for principal propagation expires after 30 minutes.
    > 
    > If it takes longer than 30 minutes to process the data between the sender and receiver channel, the token for principal propagation expires, which leads to errors in message processing.


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

*Credential Name* \(only available if you have selected *Basic* for the *Authentication* parameter\)



</td>
<td valign="top">

Name of the *User Credentials* artifact that contains the credentials for basic authentication



</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias* \(only available if you have selected *Client Certificate* for the *Authentication* parameter\)



</td>
<td valign="top">

Specifies an alias to indicate a specific key pair to be used for the authentication step.

You can dynamically configure the *Private Key Alias* parameter by specifying either a header or a property name in one of the following ways: `$ {header.headername}` or `$ {property.propertyname}`.

Be aware that in some cases this feature can have a negative impact on performance.



</td>
</tr>
<tr>
<td valign="top">

*Timeout*



</td>
<td valign="top">

Specifies the time \(in milliseconds\) that the client will wait for a response before the connection is being interrupted.

The default value is 60000 milliseconds \(1 minute\).



</td>
</tr>
<tr>
<td valign="top">

*Compress Message*



</td>
<td valign="top">

Enables the WS endpoint to send compressed request messages to the WS Provider and to indicate the WS Provider that it can handle compressed response messages.



</td>
</tr>
<tr>
<td valign="top">

*Allow Chunking*



</td>
<td valign="top">

Used for enabling HTTP chunking of data while sending messages.



</td>
</tr>
<tr>
<td valign="top">

*Return HTTP Response Code as Header*



</td>
<td valign="top">

When selected, writes the HTTP response code received in the response message from the called receiver system into the header `CamelHttpResponseCode`.

This feature is disabled by default.

> ### Note:  
> You can use this header, for example, to analyze the message processing run \(when level Trace has been enabled for monitoring\). Furthermore, you can use this header to define error handling steps after the integration flow has called the IDoc SOAP receiver.
> 
> You cannot use the header to change the return code since the return code is defined in the adapter and cannot be changed.



</td>
</tr>
<tr>
<td valign="top">

*Clean-up Request Headers*



</td>
<td valign="top">

Select this option to clean up the adapter specific- headers after the receiver call.



</td>
</tr>
</table>

**Related Information**  


[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md "")

[Setting Up Outbound HTTP Connections](../40-RemoteSystems/setting-up-outbound-http-connections-92dd2a6.md "You can use various receiver adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a receiver system through the HTTP protocol.")

