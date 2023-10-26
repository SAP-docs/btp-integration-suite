<!-- loiocd091fc8051d42ee95eda2858ca2a2f0 -->

# SuccessFactors OData V4 Receiver Adapter

The SuccessFactors receiver adapter enables you to communicate with the SuccessFactors system. You use the OData V4 message protocol to connect to the OData V4-based Web services of the SuccessFactors system.

> ### Tip:  
> -   If your input payload has nodes without data, the output also has empty strings. If you want to avoid empty strings in the output, ensure that the input payload doesn’t contain any empty nodes.
> -   You can use headers and exchange properties in the adapter settings to pass values dynamically during runtime. More information: [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md).

Once you’ve created a receiver channel and selected the SuccessFactors OData V4 receiver adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

> ### Note:  
> The adapter only supports SuccessFactors Learning Management System \(LMS\) OData V4 entities.

Select the *General* tab and provide values in the fields as follows.

**General**


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

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

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

URL of the SuccessFactors data center that you want to connect to.

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

-   *OAuth2 Client Credentials* – Use this grant type to access web resources by authorizing the client application to perform required actions on behalf of a user. For more information, see [Deploying an OAuth2 Client Credentials Artifact](deploying-an-oauth2-client-credentials-artifact-801b106.md).

-   *OAuth2 SAML Bearer Assertion* – If you've chosen this option, the sender account forwards the identity of the logged in user or a dedicated technical user to the receiver account. For more information, see [Deploying an OAuth2 SAML Bearer Assertion](deploying-an-oauth2-saml-bearer-assertion-3ee6582.md).




</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Name of the deployed security artifact.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

Type of proxy you want to use to connect to the SuccessFactors system.

Currently, you can only choose *Internet* as the proxy type.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

The option is enabled by default. This option enables the reuse of connection objects from the internal connection pool which in turn improves the network turnaround time for multiple communications to a same end point.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Processing**


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

*Operation* 

</td>
<td valign="top">

Select the operation that you want to perform from the dropdown list.

-   *Query\(GET\)*

-   *Create\(POST\)*

-   *Update\(PUT\)*




</td>
</tr>
<tr>
<td valign="top">

*Resource Path* 

</td>
<td valign="top">

Provide the resource path of the entity that you want to access.

</td>
</tr>
<tr>
<td valign="top">

*Query Options*

Relevant only for *Query\(GET\)* operation

</td>
<td valign="top">

Query options that you want to send to the OData V4 service with operation details.

</td>
</tr>
</table>

