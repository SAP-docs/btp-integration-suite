<!-- loio6f43916f11344d3193ae51341b2d6d4e -->

# Creating Keys for the Usage of PKCS\#7, XML Digital Signature and WS-Security

To set up message level security scenarios based on PKCS\#7, XML Digital Signature or WS-Security, the required keys are created in the same way as for transport level security HTTPS.

Setting up message level security based on PKCS\#7, XML Digital Signature or WS-Security requires the generation of public-private key pairs of type **X.509** – the same standard as is used for transport level security SSL.

Therefore, technically, you can use the same public key pairs for message level and transport level security \(HTTPS\).

Depending on the scenario, however, separate key pairs might be required.

Keep in mind that you can set up message level security on top of another transport security \(like, for example SFTP\). In that case, you in any case have to generate key pairs based on X.509 standard.

To generate a new public-private key pair, proceed as described for transport level security SSL. In particular, proceed in the same way as described for the configuration of certificate-based outbound authentication \(HTTPS\).

Note the following in addition:

-   If you have already generated a keystore file and a separate key pair should be used for message level security, you can use the same keystore file, import the certificates required for message level security, and re-deploy the keystore file on the relevant tenant.
-   To implement digital signature, a certificate from the sender is needed \(the public key of the sender is required to verify the signature – in other words, to decrypt the digest\).
-   To implement digital encryption, a certificate from the receiver is needed \(the public key of the receiver is required to encrypt the symmetric encryption key\).

**Related Information**  


[Message-Level Security](message-level-security-463a908.md "Several standards are supported to protect the message content (message-level security).")

[Creating X.509 Keys](creating-x-509-keys-ec605c7.md "")

