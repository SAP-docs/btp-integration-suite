<!-- loio449f6e94db044b44864a4878c08237d5 -->

# Configure Receiver Channel with ebMS3 Push

Configure the AS4 receiver channel as a sending Message Service Handler \(MSH\) to send business documents.



<a name="loio449f6e94db044b44864a4878c08237d5__prereq_cdl_kdg_tdb"/>

## Prerequisites

-   You must deploy the private key pair in theCloud Integration keystore for signing the AS4 message.

-   You must have configured an integration flow in the editor. For more information, see [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).




## Context

Use the *ebMS3 Push* message protocol to transmit AS4 message.

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



### Connection

Select the *Connection* tab and provide values in the fields as follows.

**Configure the Connection Details of the Receiving MSH**


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

Define the endpoint URL of the receiving MSH.

</td>
</tr>
<tr>
<td valign="top">

*Agreement* 

</td>
<td valign="top">

Define the type of the message exchange pattern as agreed between the MSHs for a specific type of business transaction.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type* 

</td>
<td valign="top">

Select the authentication type to process the outbound message:

-   *None*

-   *Basic Authentication*

-   *Client Certificate*

-   *SAML Authentication*


You can also set the value of this attribute dynamically using the `SAP_AS4_Outbound_Authentication_Type` header.

The valid values are:

-   `saml`

-   `basic`

-   `clientCert`

-   `none`




</td>
</tr>
<tr>
<td valign="top">

*SAML Endpoint URL* 

</td>
<td valign="top">

Provide the specific endpoint URL to support SAML-based authentication that allows access to the sending MSH.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias* 

</td>
<td valign="top">

Determine the private key alias for SAML authentication.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in sec.\)* 

</td>
<td valign="top">

Provide a connection timeout period \(in seconds\) to define how long the receiving MSH waits for the AS4 message to be received by the sending MSH.

</td>
</tr>
<tr>
<td valign="top">

*Compress Message*

</td>
<td valign="top">

Enable if you want to compress the message.

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

Define the ID of the sending MSH.

</td>
</tr>
<tr>
<td valign="top">

*Initiator Party: Party Type* 

</td>
<td valign="top">

Provide the type of the sending MSH. For example: `http://abr.gov.au/PartyIdType/ABN` 

</td>
</tr>
<tr>
<td valign="top">

*Initiator Party: Role* 

</td>
<td valign="top">

Define the role of the sending MSH. For example: `http://sbr.gov.au/ato/Role/Business` 

</td>
</tr>
<tr>
<td valign="top">

*Responder Party: Party ID* 

</td>
<td valign="top">

Define the ID of the receiving MSH.

</td>
</tr>
<tr>
<td valign="top">

*Responder Party: Party Type* 

</td>
<td valign="top">

Provide the type of the receiving MSH. For example: `http://abr.gov.au/PartyIdType/ABN` 

</td>
</tr>
<tr>
<td valign="top">

*Responder Party: Role* 

</td>
<td valign="top">

Define the role of the receiving MSH. For example: `http://sbr.gov.au/agency` 

</td>
</tr>
<tr>
<td valign="top">

*Message Partition Channel* 

</td>
<td valign="top">

Specify the partner channel details to enable the partitioned transfer of AS4 messages between AS4 exchange partners.

</td>
</tr>
<tr>
<td valign="top">

*Service* 

</td>
<td valign="top">

Define the business service of the recipient. For example, payment details of employees for a specific year: `http://sbr.gov.au/ato/payevnt/2017` 

</td>
</tr>
<tr>
<td valign="top">

*Service Type* 

</td>
<td valign="top">

Define the type of service from the recipient.

</td>
</tr>
<tr>
<td valign="top">

*Action* 

</td>
<td valign="top">

Define the type of action that the user message is intended to invoke. For example: `Submit.002.00` 

</td>
</tr>
<tr>
<td valign="top">

*Additional Properties* 

</td>
<td valign="top">

Choose to add the Key, Type, and Value attributes to modify an existing parameter in the property sheet. For example, if you want to modify the MSH details, you must define a key and its value. The *Type* attribute is used in AS4 message in order to identify the payload.

</td>
</tr>
<tr>
<td valign="top">

*Attachment* 

</td>
<td valign="top">

Select whether to add the attachment to the exchange payload of the AS4 message.

-   *Dynamic*: To set the values dynamically using `SAP_AS4_Outbound_Processing_Attachment` header.

    The valid values are:

    -   `notRequired`
    -   `required`

-   *Not Required*: To skip adding the attachment to the exchange payload of the AS4 message.
-   *Required*: To add the attachment to the exchange payload of the AS4 message.



</td>
</tr>
<tr>
<td valign="top">

*Attachment Name* 

\(only if you select *Attachment* as *Dynamic* or *Required*\)

</td>
<td valign="top">

Define the name for the attachment of the AS4 message. You can also enter $\{header.headername\} or $\{property.propertyname\} to read the value dynamically from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*Payload Properties*

</td>
<td valign="top">

Choose *Add* to define the key and value to modify the payload attached to AS4 message.

From adapter version 1.6 onwards, following default properties \(Keys\) are not added in the payload. You must add those explicitly, if required.

-   DocumentType \(value: BULK\)
-   DocumentName \(value: PAYEVNT\)
-   MimeType \(value: text/plain\)
-   PartID \(value: 1\)



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

*Username Token*

</td>
<td valign="top">

Choose the relevant password type to be used when a username token is generated from credentials.

-   *Dynamic*: To set the values dynamically using `SAP_AS4_Outbound_Username_Token` header. The valid values are:
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

*Credential Name* 

\(only if *Username Token* isn't selected as *Not Required*\)

</td>
<td valign="top">

Enter the credential name of the username-password pair specified during the deployment of the security artifact. You can also enter $\{header.headername\} or $\{property.propertyname\} to read the value dynamically from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*WS-Security Type* 

</td>
<td valign="top">

Ensures security implemented in web services for SOAP based messages.

</td>
</tr>
<tr>
<td valign="top">

*Sign and Enrypt Message* 

</td>
<td valign="top">

Used to sign and encrypt the payload.

You can also set the value of this attribute dynamically by using `SAP_AS4_Outbound_Security_Type` header.

The valid values are:

-   `sign`

-   `signAndEncrypt`

-   `none`




</td>
</tr>
<tr>
<td valign="top">

*Sign Message* 

</td>
<td valign="top">

Ensures that the outgoing AS4 message is signed.

You can also set the value of this attribute dynamically by using `SAP_AS4_Outbound_Sign_Message` header.

The valid values are:

-   `true`

-   `false`




</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias for Signing* 

</td>
<td valign="top">

Specify an alias for the tenant private key that is to be used to sign the message. The tenant private key is used to sign the request message \(that is sent to the WS provider \(receiver\)\). The tenant private key has to be part of the tenant keystore.

</td>
</tr>
<tr>
<td valign="top">

*Signature Algorithm* 

</td>
<td valign="top">

Use the relevant algorithm to sign the AS4 message.

You can also set the value of this attribute dynamically by using `SAP_AS4_Outbound_Signing_Algorithm` header.

The valid values are:

-   `SHA256/RSA`

-   `SHA384/RSA`

-   `SHA512/RSA`




</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias for Encryption*

\(only if you select *Sign and Encrypt Message*\)

</td>
<td valign="top">

Specify an alias for the public key that is to be used to encrypt the message.

The receiver \(WS provider\) public key is used to encrypt the request message \(that is sent to the receiver\). This key has to be part of the tenant keystore.

You can also set the value of this attribute dynamically by using `SAP_AS4_Outbound_Encryption_Cert` header. Use this header to set the certificate value to X509 certificate object.

</td>
</tr>
<tr>
<td valign="top">

*Encryption Algorithm*

\(only if you enable *Sign and Encrypt Message*\)

</td>
<td valign="top">

Specify a encryption algorithm to be applied when encrypting the message.

You can also set the value of this attribute dynamically using `SAP_AS4_Outbound_Encryption_Algorithm` header.

The valid values are:

-   `3DES`

-   `AES128`

-   `AES256`




</td>
</tr>
</table>

Select the *Response* tab and provide values in the fields as follows.

> ### Note:  
> For this adapter, version 1.6 onwards all received compressed response messages will be decompressed before sending to the exchange.

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

*Response Type* 

</td>
<td valign="top">

Select the type of expected response.

-   *Dynamic*: To set the values dynamically using `SAP_AS4_Outbound_Response_Type` header. The valid values are:
    -   `receipt`
    -   `userMessage`

-   *Receipt*: To receive a response as a signal message.
-   *User Message*: To receive a response as user message.



</td>
</tr>
<tr>
<td valign="top" colspan="2">

*Receipt Configuration* \(only if you select *Receipt* in the *Response Type*\)

</td>
</tr>
<tr>
<td valign="top">

*Save Incoming Receipt* 

</td>
<td valign="top">

Saves incoming receipt in the *Message Store* for 90 days. You can refer these receipts for auditing purposes.

You can also set the value of this attribute dynamically using `SAP_AS4_Outbound_Save_Receipt` header. The valid values are:

-   `true`

-   `false`




</td>
</tr>
<tr>
<td valign="top">

*Verify Username Token*

</td>
<td valign="top">

Select the relevant option for username token verification in AS4 receipt.

-   *Dynamic*: You can also set the value of this attribute dynamically by using `SAP_AS4_Outbound_Verify_Receipt_Username_Token` header. The valid values are:
    -   `notRequired`
    -   `required`

-   *Not Required*: To skip username token verification.
-   *Required*: To verify the username token for the receipt configuration response obtained from the receiver system.



</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

\(only if you select *Verify Username Token* as *Dynamic* or *Required*\)

</td>
<td valign="top">

Enter the credential name of the username-password pair specified during the deployment of the security artifact. You can also enter $\{header.headername\} or $\{property.propertyname\} to read the value dynamically from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*Verify the Receipt Signature* 

</td>
<td valign="top">

Choose to verify the incoming receipt signature against the public key alias.

You can also set the value of this attribute dynamically using `SAP_AS4_Outbound_Verify_Receipt` header. The valid values are:

-   `true`

-   `false`


> ### Note:  
> You can use the `SAP_AS4_Outbound_Verify_Receipt_Cert` header to set the certificate value to X509 certificate object.



</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias* 

\(Only if you select *Verify the Receipt Signature*\)

</td>
<td valign="top">

Enter an alias name to select a public key and corresponding certificate.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

*User Message Configuration* \(only if you select *User Message* as *Response Type*\)

</td>
</tr>
<tr>
<td valign="top">

*Verify Username Token*

</td>
<td valign="top">

Select the relevant option for username token verification in AS4 message.

-   *Dynamic*: You can also set the value of this attribute dynamically by using `SAP_AS4_Outbound_Push_Verify__User_Message_ Receipt_Username_Token` header. The valid values are:
    -   `notRequired`
    -   `required` 

-   *Not Required*: To skip username token verification.
-   *Required*: To verify username token in AS4 message.



</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

\(only if you select *Verify Username Token* as *Dynamic* or *Required*\)

</td>
<td valign="top">

Enter the credential name of the username-password pair specified during the deployment of the security artifact. You can also enter $\{header.headername\} or $\{property.propertyname\} to read the value dynamically from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*Verify Signature* 

</td>
<td valign="top">

Select to verify the user message signature.

-   *Dynamic*: You can set the value of this attribute dynamically using `SAP_AS4_ Outbound_Push_Verify_User_Message_Signature` header. The valid values are:
    -   `notRequired`
    -   `trustedCertificate`

-   *Not Required*: To skip verifying the user message signature.
-   *Trusted Certificate*: To verify the signature for the user message response obtained from the receiver system.



</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias* 

\(Only if you select *Verify Signature* as *Dynamic* or *Trusted Certificate*\)

</td>
<td valign="top">

Enter an alias name to select a public key and corresponding certificate.

</td>
</tr>
<tr>
<td valign="top">

*Decrypt Message* 

</td>
<td valign="top">

Select an alias to decyrpt the message.

-   *Dynamic*: You can set the value of this attribute dynamically using `SAP_AS4_Outbound_Push_Decrypt_Message` header. The valid values are:
    -   `notRequired`
    -   `required`

-   *Not Required*: To skip the message decryption.
-   *Required*: To decrypt the message.



</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias* 

\(Only if you select *Decrypt Message* as *Dynamic* or *Required*\)

</td>
<td valign="top">

Enter an alias name to select a private key and corresponding certificate.

</td>
</tr>
</table>

> ### Note:  
> Set the value, provided by ATO, to the `SAP_AS4_Outbound_ATO_SAML_AppliesTo` header for *AppliesTo* parameter to fetch SAML token from Vanguard.

**Related Information**  


[Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md "")

