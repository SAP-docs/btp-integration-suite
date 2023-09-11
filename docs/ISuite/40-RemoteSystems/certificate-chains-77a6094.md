<!-- loio77a609451dbd46a58991e685c37350d8 -->

# Certificate Chains

The trust relationship between a client and a server using TLS authentication is usually based on chain certificates.

When using the X.509 standard, a key pair used for the TLS handshake is usually signed by a certification authority \(CA\). This means that the server can assume that the public key \(included in the certificate\) provided by the client originates from a trusted source.

The X.509 standard allows you to build up hierarchical trust models. In such a model \(also referred to as a *certificate chain*\), many certification authorities \(CAs\) are involved on different hierarchy levels. This means that the certificate that identifies the CA as a trusted participant can itself be signed by a CA at a higher level in the hierarchy. This means that a number of \(intermediate\) CAs can be arranged above the actual client certificate. The highest level CA is called the root CA.

The following figure shows a certificate chain with two intermediate CAs:

![](images/Certificate_Chain_fc7e762.png)

We assume that the tenant is connected as a client to an external component \(which can be referred to as the server or receiver system\).

To establish SSL connectivity, the server is provided with the root CA certificate and nothing else. To make sure that a trust relationship between client and server can be established nevertheless, the client certificate \(of the tenant\) used for the SSL handshake has to contain the whole certificate chain. In other words, the client certificate has to include all intermediate CAs \(excluding the root CA\). This enables the server to evaluate and calculate the whole chain of trust.

Therefore, during connection setup \(onboarding\), the tenant key pair \(client certificate\) has to be assigned the whole certificate chain.

> ### Tip:  
> To find out the certificate chain of the server, you can use the TLS Outbound Connection Test \(accessible in the Monitoring application\). This test also helps you to find out whether you have the correct CA certificate in the keystore to validate the server certificate chain \(see option *Validate Server Certificate* of the Outbound Connection Test\).

**Related Information**  


[TLS Connectivity Tests](../50-Development/tls-connectivity-tests-03bbb5d.md "When you've chosen the TLS connection, the test tool checks the following:")

