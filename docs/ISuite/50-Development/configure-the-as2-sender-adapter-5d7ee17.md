<!-- loio5d7ee17e554841df8ef355413b88e056 -->

# Configure the AS2 Sender Adapter

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
> For Edge Integration Cell runtime fetching the values dynamically from partner directory is not supported.

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

> ### Note:  
> -   If you are configuring the sender channel to receive AS2 messages, select the AS2 message protocol.
> -   If you want to call the AS2 sender channel, then use the pattern `https://<host>:<port>/as2/as2`; to call the AS2 MDN sender channel, use `https://<host>:<port>/as2/mdn` .
> -   The JMS queue name contains the name of the AS2 sender channel. To analyze a troubleshooting scenario better, it's recommended to specify the name of the AS2 sender channel.
> -   You must activate [Enterprise Messaging](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/a74cddceacb34abb958e817c1f6782d2.html "Activate SAP Event Mesh.") :arrow_upper_right:/ [Message Queue](managing-message-queues-cdcce24.md) to use AS2 Sender adapter version 1.6 and further. From version 1.7 and before, the activation is not required if you select [Quality of Service](configure-the-as2-sender-adapter-5d7ee17.md#loio5d7ee17e554841df8ef355413b88e056__table_m23_m42_n2b) as *Best Effort*.
> -   The expiration period for stored messages is 90 days, after which the messages are deleted.
> -   The retention threshold for alerting is two days, by which the messages have to be fetched before an alert is raised.

Once you have created a sender channel and selected the AS2 adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

The *General* tab shows general information such as the adapter type, its direction \(sender or receiver\), the transport protocol, and the message protocol.

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

For example, if the URL is `https://<tenant address>/as2/<mdn or as2>/orders`, then enter the value as `/orders`

</td>
</tr>
<tr>
<td valign="top">

*Authorization*

</td>
<td valign="top">

Specifies the authorization option for the sender.

-   *Client Certificate Authorization*

    Allows you to select one or more client certificates \(based on which the inbound authorization is checked\).

    Choose *Add* to add a new certificate for inbound authorization for the selected adapter. You can then select a certificate stored locally on your computer. You can also delete certificates from the list.

    For each certificate, the following attributes are displayed: *Subject DN* \(information used to authorize the sender\) and *Issuer DN* \(information about the certificate authority that issues the certificate\).

    Select Client Certificate if you want to authorize a sender based on a certificate.

-   *User Role*

    Select this option if you want to authorize a sender based on the roles defined on the tenant for the user associated with inbound request.

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

For more information on user roles, see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md) .

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

-   *Dynamic*: If you select dynamic, you must specify `authorizedUser` or `as2PartnerID` value in `SAP_AS2_Pid_Resolution_Mode` parameter of partner directory with pid of authorized user. To learn more, see [Parameterizing Integration Flows Using the Partner Directory](parameterizing-integration-flows-using-the-partner-directory-b7812a5.md).

> ### Note:  
> This field does not impact any *Private Key Alias* fields.



</td>
</tr>
<tr>
<td valign="top">

*Message ID Left Part* 

</td>
<td valign="top">

Specify the left side of the AS2 message ID. Regular expression or '.\*' is allowed.

</td>
</tr>
<tr>
<td valign="top">

*Message ID Right Part* 

</td>
<td valign="top">

Specify the right side of the AS2 message ID. Regular expression or '.\*' is allowed.

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

*Message Subject* 

</td>
<td valign="top">

Specify the AS2 message subject. Regular expression or '.\*' is allowed.

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
<td valign="top" colspan="2">

*Message Settings* 

</td>
</tr>
<tr>
<td valign="top">

*Mandatory File Name* 

</td>
<td valign="top">

Select to check that the incoming AS2 message containsthe a filename. If not found, then a negative MDN is sent as per the request of the AS2 sender.

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Message ID* 

</td>
<td valign="top">

Select to ensure that the AS2 message with the same message ID isn't processed more than once.

Define the *Persist Duration* instant in minutes to store messages for duplicate check. You can also select the appropriate *MDN Response* type when you encounter a duplicate message ID.

> ### Tip:  
> We recommend you enable duplicate message handling on the receiver system to prevent duplicate messages being processed in the overall integration scenario.



</td>
</tr>
<tr>
<td valign="top">

*Duplicate File Name* 

</td>
<td valign="top">

Select to ensure that the AS2 message with the same filename isn't processed more than once.

Define the *Persist Duration* instant in minutes to store messages for duplicate check. You can also select the appropriate *MDN Response* type when you encounter a duplicate filename.

</td>
</tr>
</table>

> ### Note:  
> -   Ensure that the combination of *Message ID Left Part*, *Message ID Right Part*, *Partner AS2 ID*, *Own AS2 ID*, and *Message Subject* parameters is unique across all AS2 sender channels.
> -   If you use regular expressions for the above-mentioned AS2 sender parameters, then you must ensure that the regular expression configuration is unique across the endpoints.
> -   The runtime identifies the relevant channel and integration flow for the incoming AS2 sender message based on the above-mentioned parameters.

Select the *Security* tab and provide values in the fields as follows.

**Security**


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

*Decryption Configuration Type*

</td>
<td valign="top">

Select the type of decryption configuration.

-   *Channel Configuration*: Decryption is determined from the input of *Decrypt Message* checkbox.
-   *Incoming AS2 Headers*: Decryption is determined by the incoming message \(headers\) at the runtime.
-   *Dynamic*: If you select *Dynamic*, you must define `incomingAS2Headers` or `channelConfiguration` value in `pd:SAP_AS2_Inbound_Decryption_Configuration_Type`.



</td>
</tr>
<tr>
<td valign="top">

*Decrypt Message*

</td>
<td valign="top">

Select this checkbox to ensure that the message is decrypted.

You can also set the value of this attribute dynamically by specifying `SAP_AS2_Inbound_Decrypt_Message` parameter in partner directory.

The valid values are:

-   true
-   false

> ### Note:  
> If the value is set in partner directory, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if you select *Decrypt Message* or *Decryption Configuration Type* as *Dynamic* or *Incoming AS2 Headers*\).

</td>
<td valign="top">

Specify the private key alias to decrypt the AS2 message. To fetch details from partner directory, use pd:xxxx or pd:AS2OwnId:<certalias\> syntax.

> ### Note:  
> The private key alias for Cloud Integration is, `sap_cloudintegrationcertificate`



</td>
</tr>
<tr>
<td valign="top">

*Verify Signature* 

</td>
<td valign="top">

Select this checkbox to ensure that the signature is verified using one of the following options:

-   *Not Required*

-   *Trusted Certificate*: Used to verify the Signature.

-   *Trusted Root Certificate*: The trust chain begins with the use of the public alias as an intermediate certificate to verify the inbound certificate. After successful verification the inbound certificate is used to verify the Signature.

    > ### Note:  
    > If *Trusted Root Certificate* is selected, mention the public key alias immediate root certificate of the incoming message.

    When verification is successful by using trusted root certificate the following exchange properties are generated:

    -   `SAP_AS2_Inbound_Certificate`

    -   `SAP_AS2_Inbound_Certificate_DN`



You can also set the value of this attribute dynamically by specifying `SAP_AS2_Inbound_Verify_Signature` parameter in partner directory. The valid values are:

-   notRequired
-   trustedCertificate
-   trustedRootCertificate

> ### Note:  
> If the value is set in partner directory, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias*

\(only if you select *Verify Signature*\).

</td>
<td valign="top">

Specify the public key alias to verify the signature of the AS2 message. To fetch details from partner directory, use `pd:<certAlias>` syntax.

</td>
</tr>
<tr>
<td valign="top">

*Public Key Aliases*

\(only if you select *Verify Signature* as *Trusted Root Certificate*\).

</td>
<td valign="top">

Specify the public key alias values \(comma separated\) to verify the signature of the AS2 message. To fetch details from partner directory, use `pd:<certAlias>` or `pd:AS2PartnerId:<certalias>` syntax.

</td>
</tr>
</table>

Select the *MDN* tab and provide values in the fields as follows.

**MDN**


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

*Private Key Alias for Signature* 

</td>
<td valign="top">

Specify the private key alias to sign the MDN on partner's request. To fetch details from partner directory, use `pd:xxxx` syntax.

</td>
</tr>
<tr>
<td valign="top">

*Signature Encoding*

</td>
<td valign="top">

Select the MDN signature encoding type.

-   *binary*
-   *base64*
-   *Dynamic*

To define this attribute dynamically, set *<binary\>* or *<base64\>* value in `SAP_AS2_Inbound_Signature_Encoding` key in partner directory.

</td>
</tr>
<tr>
<td valign="top">

*Propagate MDN Details to Exchange*

</td>
<td valign="top">

Select whether to include the generated MDN details in Camel Exchange property.

-   *Required*
-   *Not Required*
-   *Dynamic*

To define this attribute dynamically, set *<required\>* or *<notRequired\>* value in `SAP_AS2_Inbound_Propagate_MDN_Details` key in partner directory.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

In the *Cloud Integration* runtime, select the type of proxy you want to use to connect asynchronously to an AS2 sender system.

-   Select *Internet* if you are connecting to a cloud system.

-   If you select *Dynamic*, you must define *<default\>* or *<sapcc\>* value in `SAP_AS2_Inbound_Proxy_Type` key in partner directory.


If you have activated *Edge Integration Cell* runtime, select the type of proxy you want to use for connecting to receiver system.

-   *Dynamic*: If you select *Dynamic*, you must define *<default\>* or *<manual\>* value in `SAP_AS2_Inbound_Proxy_Type` key in partner directory.
-   *Internet*: To connect to a cloud system.
-   *Manual*: You can manually specify Proxy Host and Proxy Port \(using the corresponding entry fields\).



</td>
</tr>
<tr>
<td valign="top">

*Location ID*

\(for *Cloud Integration* rutime, if *Proxy Type* is *On-Premise* or *Dynamic*\)

</td>
<td valign="top">

If you use the SAP Cloud Connector to connect to your on-premise system, specify the virtual address that is configured in the SAP Cloud Connector settings. To fetch details from partner directory, use `pd:xxxx` syntax.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Host* 

\(only if *Edge Integration Cell* runtime is activated and *Proxy Type* is selected as *Manual* and *Dynamic*\)

</td>
<td valign="top">

Enter the name of the proxy host you are using to connect to a receiver system.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Port* 

\(only if *Edge Integration Cell* runtime is activated and *Proxy Type* is selected as *Manual* and *Dynamic*\)

</td>
<td valign="top">

Enter the port number you are using to connect to a receiver system.

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Select the authentication type for asynchronous MDN.

You can select one of the following authentication methods:

-   *None*

-   *Basic Authentication*

-   *Client Certificate* \(only if *Proxy Type* *Internet* or *Dynamic*\)

-   If you select *Dynamic*, you must define *<BasicAuthentication\>* or *<ClientCertificate\>* or *<None\>* value in `SAP_AS2_Inbound_Authentication` key in partner directory.



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if you select *Authentication* as *Basic Authentication* or *Dynamic*.

</td>
<td valign="top">

Specify the deployed user credentials alias for basic authentication. The tenant authenticates itself against the receiver using user credentials \(user name and password\).

It'sis a prerequisite that user credentials are specified in a Basic Authentication artifact and deployed on the related tenant.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if you select *Authentication* as *Client Certificate* or *Dynamic*.

</td>
<td valign="top">

Specify the private key alias for client certificate authentication. To fetch details from partner directory, use `pd:xxxx` syntax.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)* 

</td>
<td valign="top">

Specify how long in milliseconds the client has to accept the asynchronous MDN. Enter the value '0' if you want the client to wait indefinitely.

</td>
</tr>
</table>

Select the *Delivery Assurance* tab and specify the parameters as follows.

**Delivery Assurance**


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

*Quality of Service* 

</td>
<td valign="top">

Defines how the message from the AS2 sending partner is processed by the tenant.

Based on your requirements you can select one of the following options:

-   *Exactly Once*

    The AS2 message is temporarily stored in the JMS queue and an MDN is transmitted to the sending partner. If an error occurs during processing, the message is retried from the JMS queue.

-   *Best Effort*

    This option allows you to transmit customized MDN acknowledgments to the AS2 sending partner. The AS2 messages are processed immediately and the MDN is only transmitted to the sending partner if the processing is successful.

    By introducing a **Script** into the integration flow, you can customize the original MDN found in the exchange property `SAP_AS2_MDN`. For more information, see [Define a Local Script Step](define-a-local-script-step-03b32eb.md).




</td>
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

Select this checkbox to double the retry interval after each unsuccessful retry.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Retry Interval \(in min\)* 

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

Select the *Conditions* tab and provide values in the fields as follows.

**Conditions**


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
<td valign="top" colspan="2">

The parameters in allowing *Maximum Message Size* you to set a maximum size limit for processing inbound messages. All inbound messages that exceed the configured limit are rejected from further processing and the sender receives an error message.

> ### Note:  
> The minimum allowable size limit is 1 MB.



</td>
</tr>
<tr>
<td valign="top">

*Body Size \(in MB\)* 

</td>
<td valign="top">

Define the allowable size limit for processing the message body.

</td>
</tr>
<tr>
<td valign="top">

*Attachments Size \(in MB\)* 

</td>
<td valign="top">

Define the allowable size limit for processing the attachment.

</td>
</tr>
</table>

-   The AS2 sender passes the following headers to the integration flow for message processing:
    -   AS2PartnerID
    -   AS2OwnID
    -   AS2MessageSubject
    -   AS2Filename
    -   AS2MessageID
    -   AS2PartnerEmail
    -   AS2MessageContentType


-   Use the following attributes to reference the values that are associated with MPL:

    -   AS2 sender adapter attributes:

        -   `AdapterId`

        -   `adapterMessageId`

        -   `ReceiverAS2Name`

        -   `MessageDirection`

        -   `MDNType`

        -   `MDNStatus`

        -   `MPL ID`

        -   `MDNRequested`

        -   `SenderAS2Name`

        -   `AS2MessageID`


        For example:

        ```
        {AdapterId=AS2 Sender,
        adapterMessageId=<define _AS2-147665710-6@endionAS2_CPIAS2>,
        ReceiverAS2Name=HCIAS2,
        MessageDirection=Inbound,
        MDNType=Sending,
        MDNStatus=Success,
        MPL ID=AFgsPspcD-eYhvHFdfOZYKydBmzw,
        MDNRequested=Synchronous,
        SenderAS2Name=endionAS2,
        AS2MessageID=<define _AS2-147665710-6@endionAS2_HCIAS2>}
        
        ```



