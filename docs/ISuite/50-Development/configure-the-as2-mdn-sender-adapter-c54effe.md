<!-- loioc54effed7f1643979326e6a461899904 -->

# Configure the AS2 MDN Sender Adapter

> ### Note:  
> -   If you are configuring the sender channel to receive asynchronous AS2 MDN, select the AS2 MDN message protocol.
> -   If you want to call the AS2 MDN sender channel, use http://<host\>:<port\>/as2/mdn .
> -   You must [Activate Enterprise Messaging](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/activating-enterprise-messaging?locale=en-US&version=Cloud)/ [Message Queue](managing-message-queues-cdcce24.md) to use this adapter.

> ### Note:  
> For Edge Integration Cell runtime fetching the values dynamically from partner directory is not supported.

Once you have created a sender channel and selected the AS2 MDN adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

The General tab shows general information such as the adapter type, its direction \(sender or receiver\), the transport protocol, and the message protocol.

Select the *Connection* tab and provide the sender system information.

**Connection**


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

Specify the relative path of the endpoint URL.

For example, if the URL is `http://<tenant address>/as2/<mdn or as2>/orders`, then enter the value as `/orders`

</td>
</tr>
<tr>
<td valign="top">

*Authorization*

</td>
<td valign="top">

Specifies the authorization option for the sender.

-   *Client Certificate*

    Allows you to select one or more client certificates \(based on which the inbound authorization is checked\).

    Choose *Add* to add a new certificate for inbound authorization for the selected adapter. You can then select a certificate stored locally on your computer. You can also delete certificates from the list.

    For each certificate, the following attributes are displayed: *Subject DN* \(information used to authorize the sender\) and *Issuer DN* \(information about the certificate authority that issues the certificate\).

    Select Client Certificate if you want to authorize a sender based on a certificate.

-   *User Role*

    Select this option if you want to authorize a sender based on the roles defined on the tenant for the user associated with the inbound request.

    The role *ESBMessaging.send* is provided by default. It is a predefined role provided by SAP, which authorizes a sender system to process messages on a tenant.




</td>
</tr>
<tr>
<td valign="top">

*User Role*

\(only if you select *User Role* for *Authorization*\)

</td>
<td valign="top">

The user role that you are using for inbound authorization. Choose *Select* to get a list of all the available user roles for your tenant and select the one that you want to use.

The default value is `ESBMessaging.send`. This role authorizes a sender system to process messages on a tenant.

> ### Caution:  
> The role name must not contain any umlaut characters \(for example, `ä`\).

For more information on user roles, see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

</td>
</tr>
<tr>
<td valign="top">

*Client Certificate Authorization*

\(only if you select *Client Certificate* for *Authorization*\).

</td>
<td valign="top">

The client certificates that you are using for inbound authorization. Choose *Add* to add a new row and then choose *Select* to select a certificate stored locally on your computer. You can also delete certificates from the list.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

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

*Source*

</td>
<td valign="top">

Select among the following values to determine the source of Partner ID:

-   *AS2 Partner ID Header*: to use the AS2 Partner ID header as partner ID.
-   *Authorized User*: to fetch the partner ID from values specified in partner directory.

-   *Dynamic*: If you select dynamic, you must specify `authorizedUser` or `as2PartnerID` value in `SAP_AS2_MDN_Inbound_Pid_Resolution_Mode` parameter of partner directory with pid of authorized user. To learn more, see [Parameterizing Integration Flows Using the Partner Directory](parameterizing-integration-flows-using-the-partner-directory-b7812a5.md).

> ### Note:  
> The source of partner ID determines the behaviour of other dynamic supported fields of AS2 MDN Sender adapter like *Verify Signature*, *Verify MIC* and *Public Key Alias*.



</td>
</tr>
<tr>
<td valign="top">

*Partner AS2 ID* 

</td>
<td valign="top">

Specify your partner's AS2 ID. Regular expression or '.\*' is allowed.

</td>
</tr>
<tr>
<td valign="top">

*Own AS2 ID* 

</td>
<td valign="top">

Specify your own AS2 ID. Regular expression or '.\*' is allowed.

</td>
</tr>
<tr>
<td valign="top">

*Number of Concurrent Processes* 

</td>
<td valign="top">

Define how many processes can run in parallel for each worker node. The value depends on the number of worker nodes, the number of queues on the tenant, and the incoming load, and must be less than 99.

</td>
</tr>
<tr>
<td valign="top">

*Verify Signature* 

</td>
<td valign="top">

Enable this option to verify AS2 MDN Signature. You can set the value of this attribute dynamically by specifying `SAP_AS2_Inbound_Mdn_Verify_Signature` parameter in partner directory. The valid values are *<true\>* and *<false\>*.

</td>
</tr>
<tr>
<td valign="top">

*Pulic Key Alias*\(only if you select *Verify Signature*\)

</td>
<td valign="top">

Specify Public Key Alias to verify AS2 MDN Signature. To fetch details from partner directory, use pd:xxxx syntax.

</td>
</tr>
<tr>
<td valign="top">

*Verify MIC*

</td>
<td valign="top">

Enable this option to verify Message Integrity Check \(MIC\) from AS2 MDN. You can set the value of this attribute dynamically by specifying `SAP_AS2_Inbound_Mdn_Verify_Mic` parameter in partner directory. The valid values are *<true\>* and *<false\>*.

</td>
</tr>
<tr>
<td valign="top">

*Message Failure on Negative MDN*

</td>
<td valign="top">

Enable this option to set the message status to **Failed** to negative MDN.

</td>
</tr>
</table>

Select the *Retry* tab and specify the parameters as follows.

**Retry**


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

*Retry Interval \(in min\)* 

</td>
<td valign="top">

Define how many minutes to wait before retrying message delivery.

</td>
</tr>
<tr>
<td valign="top">

*Exponential Backoff* 

</td>
<td valign="top">

Select this checkbox to double the retry terval after each unsuccessful retry.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Retry Interval \(in min\)* \(onlz if zou select *Exponential Backoff*\)

</td>
<td valign="top">

Specify the maximum amount of time to wait before retrying message delivery.

</td>
</tr>
<tr>
<td valign="top">

*Dead-Letter Queue* 

</td>
<td valign="top">

Select this checkbox to store those messages that cannot be successfully processed after the second retry during a tenant crash. This helps you to analyze and resolve the cause of failure.

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Message During Persistence* 

</td>
<td valign="top">

Select this option to encrypt the message in the data store.

</td>
</tr>
</table>

-   The AS2 MDN sender passes the following headers to the integration flow for message processing:
    -   AS2PartnerID
    -   AS2OwnID
    -   AS2MessageID
    -   AS2MessageContentType
    -   AS2OriginalMessageID


-   Use the following attributes to reference the values that are associated with MPL:

    -   AS2 MDN sender adapter attributes:

        -   `AdapterId`

        -   `adapterMessageId`

        -   `SAP_MplCorrelationId`

        -   `MDNStatus`

        -   `Message Id`

        -   `ErrorDescription`


        For example:

        ```
        {AdapterId=AS2 MDN Sender,
        adapterMessageId=<qwesdt_123sourcewe_AS2-1479283341389-0@endionAS2_CPIAS2>,
        SAP_MplCorrelationId=AFgsEou7oJYm7AqQHsV2lM2T6iTT,
        MDNStatus=error, 
        Message Id=<c31b53255-d799-4219-9f1c-5e63a044e4@CPIAS2>,
        ErrorDescription=insufficient-message-security}
        
        ```



