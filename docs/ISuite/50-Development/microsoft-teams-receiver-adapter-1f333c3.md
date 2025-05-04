<!-- loio1f333c33badf46f5be386b3976894b5c -->

# Microsoft Teams Receiver Adapter

The Microsoft Teams Receiver adapter enables seamless integration between Microsoft Teams and SAP Integration Suite facilitating communication and automating workflows.



<a name="loio1f333c33badf46f5be386b3976894b5c__section_bhw_cmj_k2c"/>

## How the Microsoft Teams Receiver Adapter works

If you have configured the Microsoft Teams Receiver Adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Microsoft Teams \(this is a receiver system\), Microsoft Teams Receiver Adapter works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio1f333c33badf46f5be386b3976894b5c__section_lx1_zmj_k2c"/>

## Configure the Microsoft Teams Receiver Adapter

Once you have created a receiver channel and selected the Microsoft Teams Receiver Adapter, you can configure its parameters as shown below:

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

Specify the address for the Microsoft Teams service.

Example: `https://graph.microsoft.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the authentication method and permission type: 'Delegated' for user-level access, 'Application' for app-level access:

-   *OAuth2 Client Credentials \(Application Permissions\)*
-   *OAuth2 Authorization Code \(Delegated Permissions\)*



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the security artifact for the selected authentication type to connect to the Microsoft Teams account.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection* 

</td>
<td valign="top">

Enable to reuse the connection.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received.

</td>
</tr>
</table>

**Processing**


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

*Resource*

</td>
<td valign="top">

Select the resource on which to perform an operation:

-   *Team*
-   *Channel*
-   *Member*
-   *Message*
-   *Chat*



</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*Team ID*

</td>
<td valign="top">

Specify the Team ID to perform the operation.

Example: `e7cfbfaf-0a6c-44c2-93dd-128ec93fcbcf`

</td>
</tr>
<tr>
<td valign="top">

*Channel ID*

</td>
<td valign="top">

Specify the Channel ID to perform the operation.

Example: `19:BMfgIlmyW0dJMrom10A5l0OJZpUXIa_RLegsRRh9eBg1@thread.tacv2`

</td>
</tr>
<tr>
<td valign="top">

*Message ID*

</td>
<td valign="top">

Specify the Message ID to perform the operation.

Example:`1738252695781`

</td>
</tr>
<tr>
<td valign="top">

*Chat ID*

</td>
<td valign="top">

Specify the Chat ID to perform the operation.

Example: `19:c8812be898a34da3a1b390738569daea@thread.v2`

</td>
</tr>
<tr>
<td valign="top">

*Membership ID*

</td>
<td valign="top">

Specify the Membership ID to perform the operation.

Example: `MCMjMCMjZmE2YWZkZDAtZjNmYi00NmQ5LThiMTYtZWRjMjQ4NDcxYzA5IyMxOTpjODgxMmJlODk4ZDM0YWEzYTFiMzkwNzM3NTYyZGFlYUB0aHJlYWQudjIjI2UyOTQwMGE1LWU5YzctNGE5Ni04ZDk2LTQ4OTE5YTkwYzI3NA==`

> ### Note:  
> The Membership ID varies across different resource types. For example, the Membership ID for a channel resource is different from the Membership ID for a chat resource.



</td>
</tr>
<tr>
<td valign="top">

*User ID*

</td>
<td valign="top">

Specify the User ID or principal name to perform the operation.

Example: `6ad943cb-2cfd-8275-9d07-57a5e4d27cf3` or

`johndoe@contoso.com`

</td>
</tr>
<tr>
<td valign="top">

*Reply ID*

</td>
<td valign="top">

Specify the message Reply ID to perform the operation.

Example: `1738851885090`

</td>
</tr>
<tr>
<td valign="top">

*Query Parameters*

</td>
<td valign="top">

Specify the query parameter value, multiple parameters are separated by &.

Example: `$top=20&$expand=members`

</td>
</tr>
<tr>
<td valign="top">

*Start Date Time*

</td>
<td valign="top">

Specify the date and time from when the messages should be fetched.

Example: `2024-08-27T07:13:28.000z`

> ### Note:  
> Ensure that the format used is \(YYYY-MM-DDTHH:mm:ss.sssz\)



</td>
</tr>
<tr>
<td valign="top">

*Delta Link \(URL\)*

</td>
<td valign="top">

Specify the Delta Link \(URL\) to perform the operation; leave blank for the initial request.

</td>
</tr>
<tr>
<td valign="top">

*Shared Channel Team ID*

</td>
<td valign="top">

Specify the ID \(shared-with-channel-team-info-id\) of the team with whom the channel is shared to perform the operation.

</td>
</tr>
<tr>
<td valign="top">

*Next Link URL*

</td>
<td valign="top">

Specify the Next Link URL to perform the operation. Example: `https://graph.microsoft.com/v1.0/users/27eaf6fcb110-445b-b220-0c239cee2776/chats?$top=1`

> ### Note:  
> The "Next Link" URL is used for pagination through the "Get next page result" operation.



</td>
</tr>
<tr>
<td valign="top">

*Async Operation Location*

</td>
<td valign="top">

Specify the Async Operation Location to perform the operation. Example: `/teams('e6cfbfav-0a6c-44c2-93ed152fc93acbcf')/operations('bd352c21-2kse-4ae9-aba3-25c3b9hd30ec')`

> ### Note:  
> The location header retrieved from an asynchronous operation can be used in this field to check the status of the task.



</td>
</tr>
<tr>
<td valign="top">

*Wait Retry Interval \(ms\)*

</td>
<td valign="top">

Specify the time \(in milliseconds\) between each status check performed by the adapter.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Wait Time \(ms\)*

</td>
<td valign="top">

Specify the maximum time \(in milliseconds\) the adapter will wait for the final status of the async operation.

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value. All Camel specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
</table>

