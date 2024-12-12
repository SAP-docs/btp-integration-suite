<!-- loio4f5ddb3dd8164e599745243029db1bf0 -->

# Configure the Sender Channel with ebMS3 Pull

Configure the sender channel with the AS4 adapter with ebMS3 Pull as a sending Message Service Handler \(MSH\).



## Context

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

You use AS4 message exchange protocol to securely process incoming business documents using Web services.

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

Select the *Processing* tab and provide values in the fields as described.

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
<tr>
<td valign="top">

*Attachment Name* 

</td>
<td valign="top">

Define the name for the payload attached to the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Additional Message Properties* 

</td>
<td valign="top">

Define a key and value to modify an existing message parameter in the property sheet. For example, if you want to modify the MSH details, you must define a key and its value.

</td>
</tr>
<tr>
<td valign="top">

*Payload Properties* 

</td>
<td valign="top">

Define a key and value to modify the payload attached to AS4 message.

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

-   Dynamic: You can also set the value of this attribute dynamically by using `SAP_AS4_Inbound_Pull_Verify_Response_Username_Token` parameter of partner directory. The valid values are:
    -   notRequired
    -   required

-   Not Required: To skip the verification of response message.
-   Required



</td>
</tr>
<tr>
<td valign="top">

*Credential Name* only if *Verify Username Token* isn't selected as *Not Required*

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

*Public Key Alias*

\(only if you select *Trusted Certificate*.\)

</td>
<td valign="top" rowspan="2">

Define the public key alias or aliases to verify the signature of the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Public Key Aliases*

\(only if you select *Trusted Root Certificate*.\)

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

*Username Token*

</td>
<td valign="top">

Choose the relevant password type to be used when a username token is generated from credentials.

-   *Dynamic*: To set the values dynamically using `SAP_AS4_Inbound_Response_Username_Token` parameter of partner directory. The valid values are:
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

*Credential Name* only if *Username Token* isn't selected as *Not Required*

</td>
<td valign="top">

Define the credential name of the username-password pair specified during the deployment of the security artifact.

</td>
</tr>
<tr>
<td valign="top">

*Compress Message* 

</td>
<td valign="top">

Compresses the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*WS-Security Type* 

</td>
<td valign="top">

Specify either of the folllowing WS-Security type to protect message integrity and confidentiality:

-   *None*

-   *Sign and Encrypt Message*: Signs and encrypts the payload of a message \(to be decrypted by the receiver\).

-   *Sign Message*: Signs the payload of a message \(to be verified by the receiver\).


> ### Note:  
> For exchange of message specific communication rules apply as been agreed between the administrators of the Web service client and Web service provider \(for example, if certificates are to be sent with the message\).



</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias for Signing* 

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

Use the relevant algorithm to sign the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias for Encryption*

\(only if you select *Sign and Encrypt Message*.\)

</td>
<td valign="top">

Specify the public key alias to sign the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Encryption Algorithm*

\(only if you select *Sign and Encrypt Message*.\)

</td>
<td valign="top">

Select the algorithm you want to use to encrypt the payload.

</td>
</tr>
<tr>
<td valign="top">

*Key Encryption Algorithm*

\(only if you select *Sign and Encrypt Message*.\)

</td>
<td valign="top">

Select the key encryption algorithm and the system uses the related mask generation functions \(MGFs\) to encrypt the payload.

</td>
</tr>
<tr>
<td valign="top">

*Security Token Type* 

</td>
<td valign="top">

Select the type of security token reference to encode the payload.

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

