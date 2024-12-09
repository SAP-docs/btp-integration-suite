<!-- loio9d8a60ba3679426a99ad09acf17258be -->

# Keys Provided by SAP



When SAP first provides a tenant to a customer, it delivers an X.509 certificate chain, which has to be renewed every 1 year.

SAP key pairs delivered with the tenant have the following aliases: sap\_cloudintegrationcertificate, hcicertificate, or hcicertificate1.

You can use them in the following channels and integration flow steps:

-   HTTPS outbound connections with client-certificate authentication

-   Signature creator steps \(XML Signature, CMS/PKCS\#7, WS Security in SOAP adapter\)

-   Decryptor steps \(CMS/PKCX\#7, WS Security in SOAP adapter\)


In all use cases, the corresponding X.509 certificate has to be made available to the sender or receiver system to enable the following steps:

-   Configuring the required certificate-user mapping \(HTTPS communication\)

-   Verifying the signature

-   Encrypting the message


If the key pair is renewed without exchanging the certificate with the receiver or sender system, message processing will fail.

