<!-- loiode7aee5160134b74a949ac2b84cb7412 -->

# Configure the OData Sender Adapter

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

The OData sender adapter supports externalization. To externalize the parameters of this adapter, choose *Externalize* and follow the steps mentioned in [Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md).

Once you've created a sender channel and selected the OData sender adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

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

Select the *Adapter Specific* tab and provide values in the fields as follows.

**Adapter Specific**


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

*Authorization* 

</td>
<td valign="top">

Select *User Role* if you want to authorize a user to send OData requests based on the ESBMessaging.send.

Select *Client Certificate* if you want to authorize a user to send OData requests based on a certificate. If you select this option, you've to add and enter the *Subject DN* \(information used to authorize the sender\) and *Issuer DN* \(information about the Certificate Authority who issues the certificate\).

</td>
</tr>
<tr>
<td valign="top">

*User Role*

\(only if you select *Authorization* as *User Role*\).

</td>
<td valign="top">

The user role that you're using for authorization. Choose *Select* to get a list of all the available user roles for your tenant and select the one that you want to use.

For more information on user roles, see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

</td>
</tr>
<tr>
<td valign="top">

*Client Certificate*

\(only if you select *Authorization* as *Client Certificate*\).

</td>
<td valign="top">

The client certificate that you're using for authorization. Choose *Add* to add a new row and then choose *Select* to add the *Subject DN* and *Issuer DN*.

</td>
</tr>
<tr>
<td valign="top">

*EDMX* 

</td>
<td valign="top">

Select the EDMX file that contains the OData API definition.

</td>
</tr>
<tr>
<td valign="top">

*Operation* 

</td>
<td valign="top">

Select the operation that you want to perform on the selected *Entity Set* in the OData API.

</td>
</tr>
<tr>
<td valign="top">

*Entity Set* 

</td>
<td valign="top">

Entity set in the OData API that you want to perform the operation on.

</td>
</tr>
</table>

> ### Note:  
> The adapter doesn't support empty response payloads. If used, the invoking of the integration flow results in an error.
> 
> For more information on limitations in the OData sender adapter, refer the note [2919230](https://me.sap.com/notes/2919230).

To know more about using the adapter from external clients, see:

-   [Use CSRF Protection](use-csrf-protection-a0765d5.md)

-   [Setting Up OAuth Inbound Authentication with Client Credentials Grant for API Clients](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/040d8110293d44b1bfaa75674530d395.html "The API is protected by basic authentication and OAuth.") :arrow_upper_right:


> ### Note:  
> Upon deployment, the endpoint of an integration artifact with OData Sender Adapter is derived from the name of the artifact.

**Related Information**  


[Setting Up Inbound HTTP Connections (Integration Flow Processing), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/778c7e7835ff46408aafe0d499720dc7.html "You can use various sender adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a sender system so that the sender can send messages to Cloud Integration over the HTTP protocol.") :arrow_upper_right:

