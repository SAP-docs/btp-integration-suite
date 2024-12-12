<!-- loio7cdde30dda764614baa96b4a2f25c395 -->

# Configure Receiver Channel with ebMS3 Pull

Configure the AS4 receiver channel as a receiving MSH to exchange business documents.



<a name="loio7cdde30dda764614baa96b4a2f25c395__prereq_nyt_m2g_tdb"/>

## Prerequisites

-   You must deploy the public certificate in the Cloud Integration keystore for verification of the business response.

-   You must have configured an integration flow in the editor. For more information, see [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).




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

Use the *ebMS3 Pull* message protocol to receive AS4 message \(User Message\).

Select the *Connection* tab and provide values in the fields as follows.

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

Define the endpoint URL of the sending MSH.

</td>
</tr>
<tr>
<td valign="top">

*Reference Message ID* 

</td>
<td valign="top">

Define the reference ID of the signal message.

</td>
</tr>
<tr>
<td valign="top">

*Message Partition Channel* 

</td>
<td valign="top">

Define the partition for the AS4 message that needs to be exchanged between the participants.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type* 

</td>
<td valign="top">

Authentication method that you want to use for connecting to the sending MSH. You can select one of the following:

-   *None*

-   *Basic Authentication*

-   *Client Certificate*

-   *SAML Authentication*




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if you select *Basic Authentication*.\)

</td>
<td valign="top">

Provide the alias you used while deploying basic authentication credentials.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if you select *Client Certificate*.\)

</td>
<td valign="top">

Specify the private key alias to sign the message.

</td>
</tr>
<tr>
<td valign="top">

*SAML Endpoint URL*

\(only if you select *SAML Authentication*.\)

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

Provide a connection timeout period \(in seconds\) to define how long the sending MSH waits for the AS4 message to be received by the receiving MSH.

</td>
</tr>
</table>

Select the *Security*tab and provide values in the fields as follows.

**Security**


<table>
<tr>
<th valign="top">

Paramter

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

-   *Dynamic*: To set the values dynamically using `SAP_AS4_Outbound_Pull_Username_Token` header. The valid values are:
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

Enter the credential name of the username-password pair specified during the deployment of the security artifact. You can also enter $\{header.headername\} or $\{property.propertyname\} to read the value dynamically from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*Sign Message* 

</td>
<td valign="top">

Ensures that the outgoing message is signed.

You can also set the value of this attribute dynamically by using the header `SAP_AS4_Inbound_Sign_Message`.

The valid values are:

-   `true`

-   `false`




</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if *Sign Message* is enabed\)

</td>
<td valign="top">

Specify the private key alias to sign the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Signature Algorithm*

\(only if *Sign Message* is enabled\)

</td>
<td valign="top">

Use the relevant algorithm to sign the AS4 message.

You can also set the value of this attribute dynamically by using the header `SAP_AS4_Inbound_Signing_Algorithm`.

The valid values are:

-   `sha256rsa`

-   `sha384rsa`

-   `sha512rsa`




</td>
</tr>
<tr>
<td valign="top">

*Verify Signature* 

</td>
<td valign="top">

Ensures that the signature is verified.

You can also set the value of this attribute dynamically by using the header `SAP_AS4_Inbound_Verify_Sign`.

The valid values are:

-   `true`

-   `false`




</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias*

\(only if *Verify Signature* is enabled\)

</td>
<td valign="top">

Provide the public key alias to verify the signature of the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Verify Username Token*

</td>
<td valign="top">

Select the relevant option for username token verification:

-   Dynamic: You can also set the value of this attribute dynamically by using the header `SAP_AS4_Outbound_Verify_Response_Username_Token`. The valid values are:
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

Enter the credential name of the username-password pair specified during the deployment of the security artifact. You can also enter $\{header.headername\} or $\{property.propertyname\} to read the value dynamically from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*Decrypt Message* 

</td>
<td valign="top">

Select to decrypt outgoing AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if *Decrypt Message* is enabled\)

</td>
<td valign="top">

Provide the private key alias used to decipher the outgoing AS4 message.

</td>
</tr>
</table>

> ### Note:  
> Set the value, provided by ATO, to the `SAP_AS4_Outbound_ATO_SAML_AppliesTo` header for *AppliesTo* parameter to fetch SAML token from Vanguard.

Select the *Receipt*tab and provide values in the fields as follows.

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

*Receipt* 

</td>
<td valign="top">

Ensures that the outgoing AS4 message is signed.

</td>
</tr>
<tr>
<td valign="top">

*Target URL*

</td>
<td valign="top">

Provide the URL of the relevant host system for authenticating the user against the system.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Defines the tenant authenticates itself against the receiver.

There are the following options:

-   *None*

    No authentication is configured.

-   *Basic Authentication*

    The tenant authenticates itself against the receiver based on user credentials \(user and password\).

    > ### Note:  
    > When this authentication option is selected, the required security artifact \(User Credentials\) has to be deployed on the tenant.

-   *Client Certificate*

    The receiver authenticates itself \(as trusted server\) against the tenant when the connection is being set up.

    > ### Note:  
    > As prerequisite for this authentication process, the client root certificate of the tenant has to be imported into the receiver keystore \(prior to the connection set up\).




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if you select *Required* in *Basic Authentication*.\)

</td>
<td valign="top">

Provide the alias you used while deploying basic authentication credentials.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if you select *Required* in *Client Certificate*.\)

</td>
<td valign="top">

Specify the private key alias to sign the AS4 message.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in sec\)*

</td>
<td valign="top">

Specifies the time \(in seconds\) that the client will wait for a response before the connection is interrupted.

</td>
</tr>
<tr>
<td valign="top">

*Signing*

</td>
<td valign="top">

Select *Required* if you want to sign the outgoing AS4 message. This guarantees your identity by signing the messages with one or more private keys using a signature algorithm.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

</td>
<td valign="top">

Provide an alias for selecting a private key from the keystore.

</td>
</tr>
<tr>
<td valign="top">

*Signature Algorithm*

\(only if you select *Required* in *Signing*.\)

</td>
<td valign="top">

Use the relevant algorithm to sign the AS4 message.

</td>
</tr>
</table>

**Related Information**  


[Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md "")

