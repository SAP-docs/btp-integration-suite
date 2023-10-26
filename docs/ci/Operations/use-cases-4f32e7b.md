<!-- loio4f32e7b9cf6b4cb6bc7843570fea7b46 -->

# Use Cases

The following tables provides a list of all use cases and links to the corresponding renewal procedures.



## Transport Level Security Use Cases

**Security Artifact Renewal Use Cases \(Transport Level\)**


<table>
<tr>
<th valign="top">

Protocol

</th>
<th valign="top">

Authentication Option

</th>
<th valign="top">

Direction

</th>
<th valign="top">

Renewal Procedure

</th>
</tr>
<tr>
<td valign="top" rowspan="9">

HTTPS

</td>
<td valign="top" rowspan="5">

Certificate-Based

</td>
<td valign="top" rowspan="3">

Outbound

</td>
<td valign="top">

[Renewal of Tenant Client Root Certificate \(CA\)](renewal-of-tenant-client-root-certificate-ca-8dc5877.md)

</td>
</tr>
<tr>
<td valign="top">

[Renewal of the Tenant Client Certificate](renewal-of-the-tenant-client-certificate-6ec6824.md)

</td>
</tr>
<tr>
<td valign="top">

[Renewal of Receiver Back-End Server Certificate](renewal-of-receiver-back-end-server-certificate-3f4eb83.md) \(also applicable in case a SuccessFactors receiver channel is used\)

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Inbound

</td>
<td valign="top">

[Renewal of Load Balancer Server Certificate](renewal-of-load-balancer-server-certificate-1779401.md)

</td>
</tr>
<tr>
<td valign="top">

[Renewal of Sender Back-End Client Certificate](renewal-of-sender-back-end-client-certificate-2d3cae7.md)

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Basic

</td>
<td valign="top" rowspan="2">

Outbound

</td>
<td valign="top">

[Renewal of User and Password](renewal-of-user-and-password-a1c26c8.md) \(also applicable in case a SuccessFactors receiver channel is used\)

</td>
</tr>
<tr>
<td valign="top">

[Renewal of Password Only](renewal-of-password-only-241428d.md) \(also applicable in case a SuccessFactors receiver channel is used\)

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Inbound

</td>
<td valign="top">

[Renewal of User and Password](renewal-of-user-and-password-da1eeb1.md)

</td>
</tr>
<tr>
<td valign="top">

[Renewal of Password Only](renewal-of-password-only-84dabed.md)

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

SFTP

</td>
<td valign="top" rowspan="3">

Certificate-Based

</td>
<td valign="top" rowspan="3">

Tenant pulls data from SFTP server

Tenant pushes data to SFTP server

</td>
<td valign="top">

[Renewal of the SFTP Server Key](renewal-of-the-sftp-server-key-492687f.md)

</td>
</tr>
<tr>
<td valign="top">

[Renewal of the SFTP Client Key \(on Tenant\)](renewal-of-the-sftp-client-key-on-tenant-5e16205.md)

</td>
</tr>
<tr>
<td valign="top">

[Renewal of User on SFTP Server](renewal-of-user-on-sftp-server-8c5436a.md)

</td>
</tr>
</table>



## Message Level Security Use Cases

**Security Artifact Renewal Use Cases \(Message Level Security\)**


<table>
<tr>
<th valign="top">

Standard

</th>
<th valign="top">

Protection Method

</th>
<th valign="top">

Renewal Procedure

</th>
</tr>
<tr>
<td valign="top" rowspan="4">

CMS/PKCS\#7

</td>
<td valign="top">

Signer

\(Tenant signs outbound message\)

</td>
<td valign="top">

[Renewal of Keys for CMS/PKCS\#7 Signer - Outbound](renewal-of-keys-for-cms-pkcs-7-signer-outbound-fe4d37f.md) \(key pair renewed on tenant\)

</td>
</tr>
<tr>
<td valign="top">

Verifier

\(Tenant verifies inbound message\)

</td>
<td valign="top">

[Renewal of Keys for CMS/PKCS\#7 Verifier - Inbound](renewal-of-keys-for-cms-pkcs-7-verifier-inbound-c573538.md) \(key pair renewed by sender\)

</td>
</tr>
<tr>
<td valign="top">

Encryptor

\(Tenant encrypts outbound message\)

</td>
<td valign="top">

[Renewal of Keys for CMS/PKCS\#7 Encryptor - Outbound](renewal-of-keys-for-cms-pkcs-7-encryptor-outbound-39afbfa.md) \(key pair renewed by receiver\)

</td>
</tr>
<tr>
<td valign="top">

Decryptor

\(Tenant decrypts outbound message\)

</td>
<td valign="top">

[Renewal of Keys for CMS/PKCS\#7 Decryptor - Inbound](renewal-of-keys-for-cms-pkcs-7-decryptor-inbound-1cdab75.md) \(key pair renewed on tenant\)

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

OpenPGP

</td>
<td valign="top">

Encryption key

\(Tenant encrypts outbound message\)

</td>
<td valign="top">

[Renewal of OpenPGP Encryption Key - Outbound](renewal-of-openpgp-encryption-key-outbound-500bd53.md) \(encryption key renewed by receiver\)

</td>
</tr>
<tr>
<td valign="top">

Encryption key

\(Tenant decrypts inbound message\)

</td>
<td valign="top">

[Renewal of OpenPGP Encryption Key - Inbound](renewal-of-openpgp-encryption-key-inbound-66cbb51.md) \(encryption key renewed on tenant\)

</td>
</tr>
<tr>
<td valign="top">

Signer Key

\(Tenant decrypts outbound message\)

</td>
<td valign="top">

[Renewal of OpenPGP Signer Key - Outbound](renewal-of-openpgp-signer-key-outbound-b2b54df.md) \(signer key renewed on tenant\)

</td>
</tr>
<tr>
<td valign="top">

Signer key

\(Tenant verifies inbound message\)

</td>
<td valign="top">

[Renewal of OpenPGP Signer Key - Inbound](renewal-of-openpgp-signer-key-inbound-db96a4c.md) \(signer key renewed by sender\)

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

XML Digital Signature

</td>
<td valign="top">

Signer

\(Tenant signs outbound message\)

</td>
<td valign="top">

[Renewal of Keys for XML Digital Signature Signer - Outbound](renewal-of-keys-for-xml-digital-signature-signer-outbound-aaeaa2f.md)

</td>
</tr>
<tr>
<td valign="top">

Verifier

\(Tenant verifies inbound message\)

</td>
<td valign="top">

[Renewal of Keys for XML Digital Signature Verifier - Inbound](renewal-of-keys-for-xml-digital-signature-verifier-inbound-e35a3be.md)

</td>
</tr>
<tr>
<td valign="top" rowspan="8">

WS-Security

</td>
<td valign="top">

Signer

\(Tenant signs outbound request message\)

</td>
<td valign="top">

[Security Artifact Renewal for WS-Security \(Tenant Signs Outbound Request\)](security-artifact-renewal-for-ws-security-tenant-signs-outbound-request-10c32fe.md)

</td>
</tr>
<tr>
<td valign="top">

Signer

\(Tenant signs response message \(to an inbound request\)\)

</td>
<td valign="top">

[Security Artifact Renewal for WS-Security \(Tenant Signs Inbound Response\)](security-artifact-renewal-for-ws-security-tenant-signs-inbound-response-a6ccced.md)

</td>
</tr>
<tr>
<td valign="top">

Verifier

\(Tenant verifies inbound request message\)

</td>
<td valign="top">

[Security Artifact Renewal for WS-Security \(Tenant Verifies Inbound Request\)](security-artifact-renewal-for-ws-security-tenant-verifies-inbound-request-266470d.md)

</td>
</tr>
<tr>
<td valign="top">

Verifier

\(Tenant verifies response message \(to an outbound request\)\)

</td>
<td valign="top">

[Security Artifact Renewal for WS-Security \(Tenant Verifies Outbound Response\)](security-artifact-renewal-for-ws-security-tenant-verifies-outbound-response-289b653.md)

</td>
</tr>
<tr>
<td valign="top">

Encryptor

\(Tenant encrypts outbound request message\)

</td>
<td valign="top">

[Security Artifact Renewal for WS-Security \(Tenant Encrypts Outbound Request\)](security-artifact-renewal-for-ws-security-tenant-encrypts-outbound-request-efb83b3.md)

</td>
</tr>
<tr>
<td valign="top">

Encryptor

\(Tenant encrypts response message \(to an inbound request\)\)

</td>
<td valign="top">

[Security Artifact Renewal for WS-Security \(Tenant Encrypts Inbound Response\)](security-artifact-renewal-for-ws-security-tenant-encrypts-inbound-response-fdea960.md)

</td>
</tr>
<tr>
<td valign="top">

Decryptor

\(Tenant decrypts inbound request message\)

</td>
<td valign="top">

[Security Artifact Renewal for WS-Security \(Tenant Decrypts Inbound Request\)](security-artifact-renewal-for-ws-security-tenant-decrypts-inbound-request-192762b.md)

</td>
</tr>
<tr>
<td valign="top">

Decryptor

\(Tenant decrypts response message\(to an outbound request\)\)

</td>
<td valign="top">

[Security Artifact Renewal for WS-Security \(Tenant Decrypts Outbound Response\)](security-artifact-renewal-for-ws-security-tenant-decrypts-outbound-response-90b85ec.md)

</td>
</tr>
</table>

