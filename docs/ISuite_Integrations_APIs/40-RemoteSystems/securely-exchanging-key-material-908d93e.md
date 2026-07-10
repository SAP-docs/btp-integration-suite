<!-- loio908d93e6d6964bce8b2f02425f7e74cc -->

# Securely Exchanging Key Material

In many cases, communication partners need to exchange public keys in order to establish a secure connection.

To establish a secure communication between software systems, communication partners use asymmetric \(or public\) key technology and work with private/public key pairs. In some cases, public keys have to be exchanged between the partners at certain points of the configuration process.

You need to apply certain measures when exchanging key material to ensure that you do not compromise the security of your scenario.



## Public Keys

When exchanging public keys \(for example, X.509 certificates\), make sure that the keys cannot be manipulated by a third party during the transfer.

You have the following options:

-   Use a secure communication channel for the key exchange.

    For example, you can use PGP-encrypted and -signed e-mail or a secure collaboration platform like SAP Jam.

-   Verify the sender \(for example,using a signature\) and check whether the sender is authorized to provide this key material.

-   Verify that the content was not manipulated \(usually using a signature\).


If you can’t use a secure communication channel, check the integrity of the keys by other means, such as the following:

-   In the case of X.509 certificates, check that the certificate is valid and that it has been issued by a trusted certification authority \(CA\).

-   Use a separate communication channel \(for example, phone\) to verify the fingerprint of the key with the sender.




## Private Keys

Private keys are even more sensitive than public keys. Sharing your private key with others will allow them to read your encrypted messages and sign messages with your signature.

**Whenever possible, avoid exchanging private key material.**

In exceptional cases where you have to exchange private keys, apply one of the following measures:

-   Use an encrypted container with a password \(like PKCS\#12 or Java Keystore\).

-   Transfer the password through a separate communication channel \(for example, phone\).

-   Use secure communication channels. **Never** use plain e-mail or plain HTTP.

-   SAP can provide you with a process for exchanging keys in a secure manner.




## Example: Exchanging a Public Key

To configure a scenario that includes digital encryption of message content, the following main steps are required, including the exchange of a public key:

1.  A potential receiver R of the message generates a public/private key pair \(that contains the receiver's public key **PubKey\_R** and the associated private key **PrivKey\_R**\).

2.  R provides a potential sender S of messages with the public key **PubKey\_R**. To do this, R communicates with S using a private SAP Jam group that is only accessible for dedicated people associated with R and S.

    However, R does not disclose the private key.

3.  S imports **PubKey\_R** into the keystore of the software system that is involved in the scenario on the sender side.

4.  S encrypts the message with public key **PubKey\_R** and sends the encrypted message to the receiver.

5.  R decrypts the message with the private key **PrivKey\_R**.


