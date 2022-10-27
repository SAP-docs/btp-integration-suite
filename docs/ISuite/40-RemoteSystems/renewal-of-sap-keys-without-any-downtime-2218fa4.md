<!-- loio2218fa4ad2e24e4a950d8392d58165bc -->

# Renewal of SAP Keys Without Any Downtime



In certain cases it is possible to avoid a downtime in message processing when renewing keys. See the following use-case descriptions:

[Renewal of Keys for CMS/PKCS\#7 Signer - Outbound](renewal-of-keys-for-cms-pkcs-7-signer-outbound-fe4d37f.md)

[Renewal of Keys for CMS/PKCS\#7 Decryptor - Inbound](renewal-of-keys-for-cms-pkcs-7-decryptor-inbound-1cdab75.md)

[Renewal of OpenPGP Signer Key - Outbound](renewal-of-openpgp-signer-key-outbound-b2b54df.md)

[Renewal of OpenPGP Encryption Key - Inbound](renewal-of-openpgp-encryption-key-inbound-66cbb51.md)

[Renewal of Keys for XML Digital Signature Signer - Outbound](renewal-of-keys-for-xml-digital-signature-signer-outbound-aaeaa2f.md)

[Security Artifact Renewal for WS-Security \(Tenant Decrypts Inbound Request\)](security-artifact-renewal-for-ws-security-tenant-decrypts-inbound-request-192762b.md)

[Security Artifact Renewal for WS-Security \(Tenant Signs Inbound Response\)](security-artifact-renewal-for-ws-security-tenant-signs-inbound-response-a6ccced.md)

[Security Artifact Renewal for WS-Security \(Tenant Encrypts Outbound Request\)](security-artifact-renewal-for-ws-security-tenant-encrypts-outbound-request-efb83b3.md)

[Security Artifact Renewal for WS-Security \(Tenant Decrypts Outbound Response\)](security-artifact-renewal-for-ws-security-tenant-decrypts-outbound-response-90b85ec.md)

> ### Note:  
> These topics describe separate processes for renewing the various keys that are involved in an integration scenario using SAP Integration Suite . The topics cover situations where a key is owned either by the tenant administrator or by the administrator of the sender/receiver system connected to the tenant.
> 
> To keep things simple, the individual topics describe idealized situations where a key pair is used in a **single** step or only in **one** communication channel. In real-life situations, however, a key pair is typically used in several integration flows, integration flow steps, and communication channels. The tenant administrator needs to know all the steps and channels where the key pair is used to be able to correctly define the key renewal process.

