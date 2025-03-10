<!-- loio3dc390741ac141df87eca1f430bd25d2 -->

# Configure the Sender Channel with ebMS3 Push

Allows you configure the sender channel with the AS4 adapter with ebMS3 Push as a receiving Message Service Handler \(MSH\).



## Context

You use AS4 message exchange protocol to securely process incoming business documents using Web services.

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

Specify the relative endpoint of the receiving MSH. For example, `/orders`.

> ### Note:  
> When you specify the endpoint address `/path`, a sender can also call the integration flow through the endpoint address `/path/<any string>` \(for example, `/path/test/`\).
> 
> Be aware of the following related implication: When you in addition deploy an integration flow with endpoint address `/path/test/`, a sender using the `/path/test` endpoint address will now call the newly deployed integration flow with the endpoint address `/path/test/`. When you now undeploy the integration flow with endpoint address `/path/test`, the sender again calls the integration flow with endpoint address `/path` \(original behavior\). Therefore, be careful *reusing* paths of services. It is better using completely separated endpoints for services.



</td>
</tr>
<tr>
<td valign="top">

*Agreement* 

</td>
<td valign="top">

Define the message exchange pattern agreed between the MSHs. For example, `urn:fdc:peppol.eu:2017:agreements:tia:ap_provider`.

</td>
</tr>
<tr>
<td valign="top">

*Authorization* 

</td>
<td valign="top">

Select *User Role* if you want to authorize a user to send message based on the `ESBMessaging.send`.

Select *Client Certificate* if you want to authorize a user to send message based on a certificate. If you select this option, you have to add and enter the Subject DN \(information used to authorize the sender\) and Issuer DN \(information about the Certificate Authority who issues the certificate\).

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

*Initiator Party: Party ID* 

</td>
<td valign="top">

Specify the ID of the initiating partner. For example, `APP_10000000100`.

</td>
</tr>
<tr>
<td valign="top">

*Initiator Party: Party Type* 

</td>
<td valign="top">

Specify a party type to identify the initiating partner. For example, `urn:fdc:peppol.eu:2017:identifiers:ap` 

</td>
</tr>
<tr>
<td valign="top">

*Initiator Party: Role* 

</td>
<td valign="top">

Specify the role of the initiating partner. For example, `http://docs.oasis-open.org/ebxml-msg/ebms/v3.0/ns/core/200704/initiator` 

</td>
</tr>
<tr>
<td valign="top">

*Responder Party: Party ID* 

</td>
<td valign="top">

Specify the ID of the responding partner. For example,`APP_10000000200`.

</td>
</tr>
<tr>
<td valign="top">

*Responder Party: Party Type* 

</td>
<td valign="top">

Specify a party type to identify the responding partner. For example, `urn:fdc:peppol.eu:2017:identifiers:ap` 

</td>
</tr>
<tr>
<td valign="top">

*Responder Party: Role* 

</td>
<td valign="top">

Specify the role of the responding partner. For example, `p://docs.oasis-open.org/ebxml-msg/ebms/v3.0/ns/core/200704/responder` 

</td>
</tr>
<tr>
<td valign="top">

*Service* 

</td>
<td valign="top">

Specify the process identifier of the business document. For example, `urn:www.cenbii.eu:profile:bii01:ver2.0`.

</td>
</tr>
<tr>
<td valign="top">

*Service Type* 

</td>
<td valign="top">

Specify the process identifier schema of the business document. For example, `cenbii-procid-ublui`.

</td>
</tr>
<tr>
<td valign="top">

*Action* 

</td>
<td valign="top">

Specify the document type identifier of the business document with the following format: `urn:www.cenbii.eu:profile:bii01:ver2.0` .

</td>
</tr>
</table>

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

*Verify Username Token*

</td>
<td valign="top">

Select the relevant option for username token verification in the AS4 message:

-   *Dynamic*: You can also set the value of this attribute dynamically by using `SAP_AS4_Inbound_Verify_Username_Token` parameter of partner directory. The valid values are:
    -   notRequired
    -   required

-   *Not Required*: To skip the verification of response message.
-   *Required* 



</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

\(only if *Verify Username Token* isn't selected as *Not Required*\)

</td>
<td valign="top">

Define the credential name of the username-password pair specified during the deployment of the security artifact.

</td>
</tr>
<tr>
<td valign="top">

*Verify Signature* 

</td>
<td valign="top">

Select the checkbox to ensure that the signature is verified using one of the following options:

-   *Not Required*

-   *Trusted Certificate*: Used to verify the signature.

-   *Trusted Root Certificate*: The trust chain begins with the use of the public alias as an intermediate certificate to verify the inbound certificate. After successful verification, the inbound certificate is used to verify the signature.

    > ### Note:  
    > If *Trusted Root Certificate* is selected, mention the immediate root certificate of the public key alias of the incoming message.




</td>
</tr>
<tr>
<td valign="top">

*Decrypt Message* 

</td>
<td valign="top">

Used to decrypt AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias* 

</td>
<td valign="top">

Determine the private key alias to decrypt the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias*

\(only if you select *Trusted Certificate*\)

</td>
<td valign="top" rowspan="2">

Define the public key alias or aliases to verify the signature of the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Public Key Aliases*

\(only if you select *Trusted Root Certificate*\)

</td>
</tr>
</table>

Select the *Receipt* tab and provide values in the fields as follows.

**Receipt**


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

*Username Token*

</td>
<td valign="top">

Choose the relevant password type to be used when a username token is generated from credentials.

-   *Dynamic*: To set the values dynamically using `SAP_AS4_Inbound_Receipt_Username_Token` parameter in partner directory. The valid values are:
    -   none
    -   hashedPasswordWithTimestamp
    -   plainTextPassword
    -   plainTextPasswordWithTimestamp


-   *Not Required*: To skip the username token generation.
-   *With Hashed Password and Timestamp*: The username and password from the token are added to the XML payload as a plain text and hashed value respectively along with the timestamp. This is the most secure way of adding the username to the payload.
-   *With Plain Text Password*: The username and password from the token are added to the XML payload as a plain text.
-   *With Plain Text Password and Timestamp*: The username and password from the token are added to the XML payload as a plain text along with the timestamp.

    > ### Recommendation:  
    > Transmit such payloads over HTTPS transport layer.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name* \(

only if *Username Token* isn't selected as *Not Required*\)

</td>
<td valign="top">

Define the credential name of the username-password pair specified during the deployment of the security artifact.

</td>
</tr>
<tr>
<td valign="top">

*Signing* 

</td>
<td valign="top">

Ensures that the outgoing AS4 message is signed.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if you select *Required* in *Signing*\)

</td>
<td valign="top">

Specify the private key alias to sign the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Signature Algorithm*

\(only if you select *Required* in *Signing*\)

</td>
<td valign="top">

Use the relevant algorithm to sign the AS4 message.

</td>
</tr>
</table>

Select the *Response* tab and provide values in the fields as follows.

**Response**


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

*Type* 

</td>
<td valign="top">

Select the response type:

-   *Dynamic*: To set the values dynamically using `SAP_AS4_Inbound_Response_Option` parameter of partner directory. The valid values are:
    -   `noresponse`
    -   `pushAndPush`
    -   `twoWaySync`

-   *No Response*: To not send a response to the receiver.
-   *Push and Push*: To use asynchronous communication pattern for message exchange.
-   *Two Way Sync*: To use the same request channel for responding\(with a user message\) to the incoming user message from exchange.



</td>
</tr>
<tr>
<td valign="top" colspan="2">

The following options are available only if you select *Push and Push* in *Type*.

</td>
</tr>
<tr>
<td valign="top">

*Target URL* 

</td>
<td valign="top">

Specify receipient's URL to which the AS4 message is transmitted.

</td>
</tr>
<tr>
<td valign="top">

*Agreement* 

</td>
<td valign="top">

Provide the message exchange pattern agreed between the MSHs. For example,`https://sbr.gov.au/agreement/Gateway/1.0/Push/PKI`.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type* 

</td>
<td valign="top">

Defines the tenant authenticates itself against the sender.

There are the following options:

-   *None*: No authentication is configured.

-   *Basic Authentication*: The tenant authenticates itself against the sender based on user credentials \(user and password\).

    > ### Note:  
    > When this authentication option is selected, the required security artifact \(User Credentials\) has to be deployed on the tenant.

-   *Client Certificate*: The sender authenticates itself \(as trusted server\) against the tenant when the connection is being set up.

    > ### Note:  
    > As prerequisite for this authentication process, the client root certificate of the tenant has to be imported into the senders keystore \(prior to the connection set up\).


You can set the values dynamically using `SAP_AS4_Inbound_Response_Authentication_Type` parameter of partner directory. The valid values are:

</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Provide the alias you used while deploying basic authentication credentials.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if you select *Authentication Type* as *Client Certificate*\)

</td>
<td valign="top">

Specify the private key alias, used to sign the incoming AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Compress Message*

</td>
<td valign="top">

Compresses the AS4 message. You can set the values dynamically using `SAP_AS4_Inbound_Response_Compress_Message` parameter of partner directory. The valid values are:

-   `true`
-   `false`



</td>
</tr>
<tr>
<td valign="top">

*Save Receipt* 

</td>
<td valign="top">

Check to save the receipt in the message store. You can also set the values dynamically using `SAP_AS4_Inbound_Response_Receipt_Save` parameter of partner directory. The valid values are:

-   `true`
-   `false`



</td>
</tr>
<tr>
<td valign="top" colspan="2">

*Message Security* \(for Push and Push or Two Way Sync\)

</td>
</tr>
<tr>
<td valign="top">

*Username Token* 

</td>
<td valign="top">

Choose the relevant option to be used while generarting username token from credential.

-   *Dynamic*: To set the values dynamically using `SAP_AS4_Inbound_Response_Username_Token` parameter of partner directory. The valid values are:
    -   `notRequired`
    -   `withhashedpasswordandtimestamp`
    -   `withplaintextpassword`
    -   `withplaintextpasswordandtimestamp`

-   *Not Required*: To skip the username token generation.
-   *With Hashed Password and Timestamp*: The username and password from the token are added to the XML payload as a plain text and hashed value respectively along with the timestamp. This is the most secure way of adding the username to the payload.
-   *With Plain Text Password*: The username and password from the token are added to the XML payload as a plain text.
-   *With Plain Text Password and Timestamp*: The username and password from the token are added to the XML payload as a plain text along with the timestamp.



</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

\(only if you select *Username Token* as *Dynamic* or *With Hashed Password and Timestamp* or *With Plain Text Password* or *With Plain Text Password and Timestamp*\)

</td>
<td valign="top">

Enter the credential name specified during the deployment of the security artifact.

</td>
</tr>
<tr>
<td valign="top">

*WS-Security Type* 

</td>
<td valign="top">

Specify either of the following WS-Security type to protect message integrity and confidentiality:

-   *None*

-   *Sign and Encrypt Message*: Signs and encrypts the payload of a message \(to be decrypted by the receiver\).

-   *Sign Message*: Signs the payload of a message \(to be verified by the receiver\).


> ### Note:  
> For exchange of message specific communication rules apply as been agreed between the administrators of the Web service client and Web service provider \(for example, if certificates are to be sent with the message\).

You can also set the values dynamically using `SAP_AS4_Inbound_Response_WS_Security` parameter of partner directory. The valid values are:

-   `sign`
-   `none`
-   `signAndEncrypt`



</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias for Signing* 

\(only if you select *WS-Security Type* as *Sign and Encrypt Message* or *Sign Message*\)

</td>
<td valign="top">

Specify the private key alias to sign the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Signature Algorithm* 

</td>
<td valign="top">

Select the relevant algorithm to sign the AS4 message.

You can also set the value of this attribute dynamically by using `SAP_AS4_Inbound_Response_Signing_Algorithm` parameter of the partner directory. The valid values are:

-   `SHA256/RSA`
-   `SHA384/RSA`
-   `SHA512/RSA`



</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias for Encryption*

\(only if you select *WS-Security Type* as *Sign and Encrypt Message*\)

</td>
<td valign="top">

Specify the public key alias to sign the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Encryption Algorithm*

\(only if you select *WS-Security Type* as *Sign and Encrypt Message*\)

</td>
<td valign="top">

Select the algorithm you want to use to encrypt the payload.

You can also set the value of this attribute dynamically by using `SAP_AS4_Inbound_Response_Encryption_Algorithm` parameter of the partner directory. The valid values are:

-   `3DES`
-   `AE128`
-   `AE256`



</td>
</tr>
<tr>
<td valign="top">

*Key Encryption Algorithm*

\(only if you select *WS-Security Type* as *Sign and Encrypt Message*\)

</td>
<td valign="top">

Select the key encryption algorithm and the system uses the related mask generation functions \(MGFs\) to encrypt the payload.

You can also set the value of this attribute dynamically by using `SAP_AS4_Inbound_Response_Key_Encryption_Algorithm` parameter of the partner directory. The valid values are:

-   `RSA-OAEP [SHA256]`
-   `RSA-OAEP [SHA384]`
-   `RSA-OAEP [SHA512]`
-   `RSA-OAEP-MGF1P`



</td>
</tr>
<tr>
<td valign="top" colspan="2">

*Two Way Payload Processing* \(only if you select *Type* as *Dynamic* or *Two Way Sync*\)

</td>
</tr>
<tr>
<td valign="top">

*Compress Message*

</td>
<td valign="top">

Select to compress the AS4 message.

-   *Dynamic*: You can set the values dynamically using `SAP_AS4_Inbound_Response_Compress_Message`. The valid values are:
    -   `notRequired`
    -   `required`

-   *Not Required*: To send an uncompressed AS4 message to the receiver.
-   *Required*: To compress the AS4 message sent to the receiver.



</td>
</tr>
</table>

Select the *Delivery Assurance* tab and provide values in the fields as follows.

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

Defines how the message is processed by the tenant.

There are the following options:

-   *Best Effort*

    The message is sent synchronously; this means that the tenant waits for a response before it continues processing.

    No temporary storage of the message needs to be configured, as message request and response are processed immediately after another.

-   *At Least Once*

    The message is sent asynchronously. This means that the tenant does not wait for a response before continuing processing. It is expected that the receiver guarantees that the message is processed exactly once.

    This option guarantees that the message is processed at least once on the tenant. If a message with identical message ID is received multiple times from a sender, all of them will be processed.

    If you choose this option, the message needs to be temporarily stored on the tenant \(in the storage configured under *Temporary Storage*\). As soon as the message is store there, the sender receives successfully received status message. If an error occurs, the message is retried from the temporary storage.

-   *Exactly Once* \(Only possible if as *Temporary Storage* the option *Data Store* is selected\)

    The message is sent asynchronously. This means that the tenant does not wait for a response before continuing processing.

    This option guarantees that the message is processed exactly once on the tenant. If a message with identical message ID is received multiple times from a sender, only the first one will be processed. The subsequent messages can be identified as duplicates and will not be processed.

    If you choose this option, the message needs to be temporarily stored on the tenant \(in the storage configured under *Temporary Storage*\). As soon as the message is store there, the sender receives successfully received status message. If an error occurs, the message is retried from the temporary storage.




</td>
</tr>
<tr>
<td valign="top">

*Temporary Storage*

\(only if as *Quality of Service* the option *Exactly Once* or *At Least Once* is selected\)

</td>
<td valign="top">

Temporary storage location for messages that are processed asynchronously. Messages for which processing runs into an error can be retried from the temporary storage.

You can choose among the following storage types:

-   *Data Store*

    The message is temporarily stored in the database of the tenant \(in case of an error\). In case of successful message processing, the message is immediately removed from the data store.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Data Stores* tile.

    > ### Note:  
    > The data store name is automatically generated and contains the following parts:
    > 
    > `<name of participant connected with AS4 adapter>_< AS4 channel name>`
    > 
    > This automatically generated name is subject to a length restriction and must be no more than 40 characters \(including the underscore\). If the data store name exceeds this limit, you must shorten the participant name or channel name accordingly.
    > 
    > Below the data store name, you find a reference to the associated integration flow in the following form: `<integration flow name>/AS4`

-   *JMS Queue*

    The message is stored temporarily in a JMS queue on the configured message broker.

    If possible, use this option as it comes with a better performance.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Message Queues* tile.

    > ### Note:  
    > The name of the JMS queue is automatically generated and contains the following parts:
    > 
    > `AS4.<Integration Flow Name>.<Channel Name>.<Guide>` 

    > ### Note:  
    > This option is only available if you have an *Enterprise Edition* license.




</td>
</tr>
<tr>
<td valign="top">

*Lock Timeout \(in min\)*

\(only configurable if *Data Store* is selected

</td>
<td valign="top">

Enter a value for the retry timeout of the in-progress repository.

</td>
</tr>
<tr>
<td valign="top">

*Retry Interval \(in min\)*

</td>
<td valign="top">

Enter a value for the amount of time to wait before retrying message delivery.

</td>
</tr>
<tr>
<td valign="top">

*Exponential Backoff*

</td>
<td valign="top">

Select this option to double the retry interval after each unsuccessful retry.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Retry Interval \(in min\)*

\(only configurable when *Exponential Backoff* is selected\)

</td>
<td valign="top">

You can set an upper limit on that value to avoid an endless increase of the retry interval. The default value is 60 minutes. The minimum value is 10 minutes.

</td>
</tr>
<tr>
<td valign="top">

*Dead-Letter Queue*

\(only if as *Temporary Storage* the option *JMS Queue* is selected\)

</td>
<td valign="top">

Select this option to place the message in the dead-letter queue if it cannot be processed after three retries caused by an out-of-memory. Processing of the message is stopped then.

In such cases, a lock entry is created which you can view and release in the *Monitor* section of the Web UI under *Managing Locks*.

Use this option to avoid out-of-memory situations \(caused in many cases by large messages\).

For more information, read the SAP Community blog [Cloud Integration – Configure Dead Letter Handling in JMS Adapter](https://blogs.sap.com/2017/07/17/cloud-integration-configure-dead-letter-handling-in-jms-adapter/).

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Message During Persistence* 

</td>
<td valign="top">

Select this option in case the messages should be stored in an encrypted way during certain processing steps.

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

The parameters in *Maximum Message Size* allow you to set a maximum size limit for processing inbound messages. Any inbound message that exceeds the configured limit is rejected from further processing and the sender receives an error message.

</td>
</tr>
<tr>
<td valign="top">

*Body Size \(in MB\)* 

</td>
<td valign="top">

Define the size limit for processing the message body.

</td>
</tr>
<tr>
<td valign="top">

*Attachment Size \(in MB\)* 

</td>
<td valign="top">

Define the size limit for processing the attachment.

</td>
</tr>
</table>

