<!-- loio9db62be7f6024c45b36ded818b75e6c8 -->

# Configure the AS2 Receiver Adapter

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

> ### Note:  
> In Neo environment, AS2 Receiver adapter version 1.7 and above can be used without [Enterprise Messaging](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/activating-enterprise-messaging?locale=en-US&version=Cloud)/ [Message Queue](managing-message-queues-cdcce24.md) activation.
> 
> In Cloud Foundry environment, all versions of the adapter can be used without [Enterprise Messaging](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/activating-enterprise-messaging?locale=en-US&version=Cloud)/ [Message Queue](managing-message-queues-cdcce24.md) activation.

Once you have created a receiver channel and selected the AS2 receiver adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

The *General* tab shows general information such as the adapter type, its direction \(sender or receiver\), the transport protocol, and the message protocol.

Select the *Connection* tab and provide the recipient information.

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

*Receipient URL* 

</td>
<td valign="top">

Enter the URL of the receiver system.

</td>
</tr>
<tr>
<td valign="top">

*URL Parameters Pattern* 

</td>
<td valign="top">

Define query parameters that are attached to the end of recipient URL.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

In the *Cloud Integration* runtime, select the type of proxy you want to use for connecting to receiver system.

-   *Dynamic*: To set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Proxy_Type`. The valid values are *<sapcc\>* and *<default\>*
-   *Internet*: To connect to a cloud system.
-   *On-Premise*: To connect to an on-premise system.

If you have activated *Edge Integration Cell* runtime, select the type of proxy you want to use for connecting to receiver system.

-   *Dynamic*: If you select Dynamic, you must define *<default\>* or *<manual\>* value in `SAP_AS2_Inbound_Proxy_Type` key in partner directory.
-   *Internet*: To connect to a cloud system.
-   *Manual*: You can manually specify Proxy Host and Proxy Port \(using the corresponding entry fields\).



</td>
</tr>
<tr>
<td valign="top">

*Location ID*

\(for *Cloud Integration* runtime, if *On-Premise* is selected for *Proxy Type*\)

</td>
<td valign="top">

Enter the location ID to identify a specific Cloud Connector that is unique to your subaccount.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Host* 

\(only if *Edge Integration Cell* runtime is activated and *Proxy Type* is selected as *Manual* and *Dynamic*\)

</td>
<td valign="top">

Enter the name of the proxy host you are using to connect to a receiver system.

You can also enter $\{header.headername\} or $\{property.propertyname\} to read the value dynamically from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Port* 

\(only if *Edge Integration Cell* runtime is activated and *Proxy Type* is selected as *Manual* and *Dynamic*\)

</td>
<td valign="top">

Enter the port number you are using to connect to a receiver system.

You can also enter $\{header.headername\} or $\{property.propertyname\} to read the value dynamically from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type* 

</td>
<td valign="top">

Select one of the following authentication methods:

-   *None*: To skip authentication method.
-   *Basic authentication*: To use alias of deployed user credentials for this authentication.
-   *Client Certificate*\(only if *Internet* is selected for *Proxy Type*.\): To use private key alias of deployed keyStore for this authentication.
-   *Dynamic*: You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Authentication_Type`. The valid values are *<None\>*, *<BasicAuthentication\>*, and *<ClientCertificate\>*



</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if you select *Client Certificate*\)

</td>
<td valign="top">

Enter the private key alias that enables the system to fetch the private key from keystore for authentication.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if you select *Basic authentication*\)

</td>
<td valign="top">

Provide the name of the *User Credentials* artifact that contains the credentials for basic authentication.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum time \(in milliseconds\) the adapter waits for receiving a response before terminating the connection.

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

*File Name* 

</td>
<td valign="top">

Specify the AS2 file name. If no file name is specified, the default file name `<Own AS2 ID>_File` is used. Simple expressions, `${header.<header-name>}`, or`${property.<property-name>}` are allowed.

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

*Own AS2 ID* 

</td>
<td valign="top">

Specify your own AS2 ID. Regular expression or '.\*' is allowed.

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

*Message Subject* 

</td>
<td valign="top">

Specify the AS2 message subject. Regular expression or '.\*' is allowed.

</td>
</tr>
<tr>
<td valign="top">

*Own E-mail Address*

</td>
<td valign="top">

Specify your own e-mail ID. Simple expressions, `${header.<header-name>}`, or `${property.<property-name>}` are allowed.

</td>
</tr>
<tr>
<td valign="top">

*Content Type* 

</td>
<td valign="top">

Specify the content type of the outgoing message. For example: application/edi-x12. Simple expressions,`${header.<header-name>}`, or `${property.<property-name>}` are allowed.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Content_Type`.

> ### Note:  
> If the header value is set, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Custom Headers Pattern* 

</td>
<td valign="top">

Specify a regular expression to pick message headers and add them as AS2 custom headers.

For example, if you want to pick all EDI headers starting with the name EDI, specify the expression as `EDI.*`.

</td>
</tr>
<tr>
<td valign="top">

*Content Transfer Encoding* 

</td>
<td valign="top">

Specify the AS2 message encoding type as:

-   base64
-   binary

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Content_Transfer_Encoding`.

The allowed values are *<binary\>* and *<base64\>*.

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

*Compress Message*

</td>
<td valign="top">

Select this checkbox to ensure that the outgoing AS2 message is compressed.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Compress_Message`.

The valid values are:

-   true
-   false

> ### Note:  
> If the header value is set, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Sign Message* 

</td>
<td valign="top">

Select this checkbox to ensure that the outgoing AS2 message is signed.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Sign_Message`.

The valid values are:

-   true
-   false

> ### Note:  
> If the header value is set, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Algorithm*

\(only if you select *Sign Message*.\)

</td>
<td valign="top">

Select the AS2 message signing algorithm.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Signing_Algorithm`.

The valid values are:

-   SHA1
-   SHA224
-   SHA256
-   SHA384
-   SHA512
-   MD5

> ### Note:  
> If the header value is set, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

\(only if you select *Sign Message*.\)

</td>
<td valign="top">

Specify the private key alias to sign the AS2 message. Simple expressions, `${header.<header-name>}`, or `${property.<property-name>}` are allowed.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Signing_Private_Key_Alias`.

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Message* 

</td>
<td valign="top">

Select this checkbox to ensure that the message is encrypted.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Encrypt_Message`.

The valid values are:

-   true
-   false

> ### Note:  
> If the header value is set, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Algorithm*

\(only if you select *Encrypt Message*\).

</td>
<td valign="top">

Select the AS2 message encryption algorithm.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Encryption_Algorithm`.

The valid values are:

-   3DES
-   AES128
-   AES192
-   AES256
-   RC2

> ### Note:  
> If the header value is set, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias*

\(only if you select *Encrypt Message*\).

</td>
<td valign="top">

Specify the public key alias to encrypt the AS2 message. Simple expressions, `${header.<header-name>}`, or `${property.<property-name>}` are allowed. The header or property can contain a public key alias or X509 certificate.

</td>
</tr>
<tr>
<td valign="top">

*Key Length*

\(only if you select *Encrypt Message* and select ***RC2*** in the *Algorithm*field\).

</td>
<td valign="top">

Specify the public key length.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Encryption_Key_Length`.

> ### Note:  
> If the header value is set, it takes precedence over the actual value configured in the channel.



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

*Type* 

</td>
<td valign="top">

Enable this option to request the partner to send a Message Integrity Check \(MIC\) in AS2 MDN.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Mdn_Type`. The allowed values are *<synchronous\>*, *<asynhronous\>*, and *<none\>*.

> ### Note:  
> If the header value is set, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Target URL*

\(only if you select the *Asynchronous* MDN type\).

</td>
<td valign="top">

Specify the URL where the AS2 MDN will be received from the partner. Simple expressions, $\{header.<header-name\>\}, or $\{property.<property-name\>\} are allowed.

</td>
</tr>
<tr>
<td valign="top">

*Request Signing*

\(only if you select the *Asynchronous* or *Synchronous* MDN type.\)

</td>
<td valign="top">

Enable this option to request the partner to sign AS2 MDN.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Mdn_Request_Signing`.

</td>
</tr>
<tr>
<td valign="top">

*Algorithm*

\(only if you enable the *Request Signing* option.\)

</td>
<td valign="top">

Select the appropriate algorithm.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Mdn_Signing_Algorithm`.

> ### Note:  
> If the header value is set, it takes precedence over the actual value configured in the channel.



</td>
</tr>
<tr>
<td valign="top">

*Verify Signature*

\(only if you select the *Synchronous* MDN type.\)

</td>
<td valign="top">

You can enable this option to verify the signature of AS2 MDN.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Mdn_Verify_Signature`

</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias*

\(only if you select *Verify Signature*.\)

</td>
<td valign="top">

Specify the public key alias to verify the MDN signature. Simple expressions, $\{header.<header-name\>\}, or $\{property.<property-name\>\} are allowed. The header or property can contain a public key alias or X509 certificate.

</td>
</tr>
<tr>
<td valign="top">

*Request MIC* 

</td>
<td valign="top">

Enable this option if you want to request an integrity check.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Mdn_Request_Mic`.

</td>
</tr>
<tr>
<td valign="top">

*Verify MIC*

\(only if you select the *Synchronous* MDN type.\)

</td>
<td valign="top">

Enable this option to verify the MIC of AS2 MDN.

You can also enable this option if you enable the *Request MIC* option and want to verify the integrity of the message.

You can also set the value of this attribute dynamically using the header `SAP_AS2_Outbound_Mdn_Verify_Mic`.

</td>
</tr>
<tr>
<td valign="top">

*Message Failure on Negative MDN*

\(only if you select the *Synchronous* MDN type.\)

</td>
<td valign="top">

Enable this option to set message status to *Failed* on negative MDN.

</td>
</tr>
</table>

> ### Note:  
> -   You can configure the AS2 receiver channel for the *Request-Reply* integration flow element. The AS2 receiver adapter \(version 1.8 and above\) will set the exchange header `Sap_AS2MessageID` with originalMessageID.
>     -   If you request synchronous MDN, the adapter sets the received MDN response as the message payload.
> 
> -   If you request synchronous MDN in the receiver channel, you may receive positive or negative MDN. In both cases, the status of the message on the *Message Monitoring* tab is *COMPLETED*. You can process the MDN message on your own and take the required action for positive or negative MDN, post AS2 call for synchronous MDN.
> 
>     Alternatively, you can also enable *Message Failure on Negative MDN* checkbox to set the message status to **Failed** on negative MDN.
> 
> -   In an MDN message, positive MDN is represented as follows:
> 
>     > ### Sample Code:  
>     > ```
>     > <?xml version="1.0" encoding="UTF-8"?>
>     > <MDNDeliveryReport>
>     > 
>     >  ................
>     > 
>     >  <MDNDispositionNotification>
>     > 
>     >   ...............
>     > 
>     > 
>     >   <Disposition>
>     > 
>     >    <DispositionMode ActionMode="automatic-action" SendingMode="MDN-sent-automatically"/>
>     >    <DispositionType>processed</DispositionType>
>     > 
>     >   </Disposition>
>     > 
>     >   <ReceivedContentMIC mic="9I2W0DSFpQOVRH75/1sLGpWAgtc=" alg="sha1"></ReceivedContentMIC>
>     > 
>     >  </MDNDispositionNotification>
>     > 
>     > </MDNDeliveryReport>
>     > ```
> 
> -   In an MDN message, negative MDN is represented as follows:
> 
>     > ### Sample Code:  
>     > ```
>     > <?xml version="1.0" encoding="UTF-8"?>
>     > <MDNDeliveryReport>
>     > 
>     >  ................
>     > 
>     >  <MDNDispositionNotification>
>     > 
>     >   ................
>     > 
>     >   <Disposition>
>     > 
>     >    <DispositionType>processed</DispositionType>
>     >    <DispositionModifier>error</DispositionModifier></Disposition>
>     >    <Error>insufficient-message-security</Error>
>     > 
>     >   </Disposition>
>     > 
>     >   <ReceivedContentMIC mic="9I2W0DSFpQOVRH75/1sLGpWAgtc=" alg="sha1"></ReceivedContentMIC>
>     > 
>     >  </MDNDispositionNotification>
>     > 
>     > </MDNDeliveryReport>
>     > ```
> 
> -   If MDN signature validation fails or an incorrect message integrity check \(MIC\) is received, the status of the message is *FAILED*.

