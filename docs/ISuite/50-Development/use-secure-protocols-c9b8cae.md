<!-- loioc9b8cae7ec3e475bb8efaef8e8de28e9 -->

# Use Secure Protocols

To ensure secure communication with remote systems, check which protocols are supported by the system. We recommend that you use encrypted protocols, if supported by the system.

Transport Layer Security \(TLS\) protects data in point-to-point communications in the following ways:

-   Encryption of the transmitted data prevents eavesdropping.

-   Secured protocols also include verification of the hostname that prevents man-in-the-middle attacks.


The character of TLS to protect point-to-point communication implies that data is only protected during the transfer. Endpoints automatically decrypt messages so that data isn't protected during processing on the server.

In case you need end-to-end encryption check the guideline for message level security described at [Apply Message-Level Security](apply-message-level-security-9036c0c.md).



<a name="loioc9b8cae7ec3e475bb8efaef8e8de28e9__section_nkm_bn3_4mb"/>

## Implementation

**Recommended Protocols and Adapter-Specific Configuration Measures**


<table>
<tr>
<th valign="top">

Adapters

</th>
<th valign="top">

Unprotected Protocols \(Avoid\)

</th>
<th valign="top">

Encrypted Protocols \(Recommended\)

</th>
<th valign="top">

Configuration Measures

</th>
</tr>
<tr>
<td valign="top">

HTTP-based receiver adapters

\(HTTP, SOAP, AS2, AS4, IDOC, OData, ODC, XI\)

> ### Note:  
> You can configure the protocol for outbound connections only.
> 
> Inbound connections \(when a sender sends a message to Cloud Integration\) are always protected via HTTPS.



</td>
<td valign="top">

HTTP

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Specify `https://` as protocol in the URL specified with the *Address* parameter.

</td>
</tr>
<tr>
<td valign="top">

FTP

</td>
<td valign="top">

FTP

</td>
<td valign="top">

FTPS or SFTP

</td>
<td valign="top">

As *Encryption*, select either *Explicit FTS* or *Implicit FTPS*.

Alternatively, you can also use the SFTP adapter that is based on the Secure Shell \(SSH\) protocol.

</td>
</tr>
<tr>
<td valign="top">

Mail receiver

</td>
<td valign="top">

SMTP

</td>
<td valign="top">

SMTPS or STARTTLS

</td>
<td valign="top" rowspan="3">

As *Authentication*, select either the secure protocol variant \(ending with *s*: *SMTPS*, *POP3S*, *IMAPS*\) or *STARTTLS Mandatory*.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Mail sender

</td>
<td valign="top">

POP3

</td>
<td valign="top">

POP3S or STARTTLS

</td>
</tr>
<tr>
<td valign="top">

IMAP

</td>
<td valign="top">

IMAPS or STARTTLS

</td>
</tr>
<tr>
<td valign="top">

AMQP

</td>
<td valign="top">

AMQP

</td>
<td valign="top">

AMQP via TLS

</td>
<td valign="top">

Select the *Connect with TLS* flag.

</td>
</tr>
<tr>
<td valign="top">

LDAP

> ### Note:  
> LDAP is currently only available via an SAP Cloud Connector that transmits data through a secure tunnel.



</td>
<td valign="top">

n/a

</td>
<td valign="top">

LDAPS

</td>
<td valign="top">

 

</td>
</tr>
</table>

> ### Note:  
> [Security Aspects of Data, Data Flow for Cloud Integration](../60-Security/security-aspects-of-data-data-flow-for-cloud-integration-7895724.md) 

> ### Note:  
> Most Internet protocols initially started simple to support unencrypted cleartext message formats. Only later when security became more important, additional encrypted protocol versions were introduced. For compatibility with legacy systems, Cloud Integration includes a long list of both encrypted and unencrypted protocol variants.



<a name="loioc9b8cae7ec3e475bb8efaef8e8de28e9__section_zms_k43_4mb"/>

## Server Certificate Verification

Protocols with transport level security usually verify that the public key of the server is issued by a trusted root certificate authority \(CA\). Therefore, make sure that the SAP Integration Suite keystore contains the right root CA certificates. You can use the connectivity test tool to get the CA certificates.

More information:

[Performing Connectivity Tests](performing-connectivity-tests-d5b2fae.md)

[Cloud Integration – How to Setup Secure Outbound HTTP Connection using Keystore Monitor](https://blogs.sap.com/2017/06/19/cloud-integration-how-to-setup-secure-outbound-http-connection-using-keystore-monitor/) \(SAP Community blog\)



<a name="loioc9b8cae7ec3e475bb8efaef8e8de28e9__section_pmn_cm3_4mb"/>

## Using SAP Cloud Connector

Several adapters allow you to select proxy type *On-Premise*. If selected, data traffic is tunneled via a secure connection to an SAP Cloud Connector in an on-premise network \(see: [Outbound: SAP Cloud Connector](../40-RemoteSystems/outbound-sap-cloud-connector-642e87f.md)\).

There are different kinds of connections in SAP Cloud Connector:

-   HTTP-based connections \(when using an HTTP-based adapter such like the SOAP adapter, for example\):

    For such connections, you've to use the unprotected default protocol \(for example, HTTP\) in the endpoint configuration of SAP Integration Suite . SAP Cloud Connector ensures a secure, TLS-protected transport via the tunnel to the on-premise landscape. For the last part of the communication from SAP CloudConnector to the backend system, you can configure either HTTP or HTTPS in SAP Cloud Connector. In this case, HTTPS is recommended.

-   LDAP connections:

    The same rules as described for HTTP-based connections apply for LDAP connections via SAP Cloud Connector. Select the plain LDAP protocol in Cloud Integration. The data is protected in transit via TLS tunnel, and in SAP Cloud Connector you've the choice between LDAP or LDAPS.

    More information: [SAP Cloud Integration – Cloud Connector & LDAP Integration](https://blogs.sap.com/2017/11/05/sap-cloud-integration-cloud-connector-ldap-integration/) \(SAP Community blog\)

-   Socks5-based connections \(when using the following adapters: FTP, SFTP, Mail, AMQP\):

    In this case, SAP Cloud Connector acts as a transparent TCP tunnel. When using such a connection, you directly configure the protocol used by the backend system in the SAP Integration Suite endpoint. In this case, it's recommended to select the corresponding secure protocol variant \(mentioned in the table above\) in the configuration of the receiver channel.




<a name="loioc9b8cae7ec3e475bb8efaef8e8de28e9__section_rzw_543_4mb"/>

## More Information

Connectivity tests help you to find configuration errors in TLS setup: [Performing Connectivity Tests](performing-connectivity-tests-d5b2fae.md).

For more information on message-level security, see [Message-Level Security](../40-RemoteSystems/message-level-security-463a908.md).

