<!-- loiofe87373a9f0149d4bbcb942378e494b3 -->

# Example: Renewal of Key Pairs Provided by SAP \(Avoiding Downtime\)

In the following example, an SAP key pair is used in the following steps and channels \(in several integration flows\):

-   CMS signer

-   CMS decryptor

-   HTTPS outbound channel


In addition, the sender and receiver systems meet the requirement that they can cope with two certificates at the same time.

The tenant administrator refers to the general key renewal documentation and finds out that key renewal can be accomplished without any downtime if the following conditions apply:

-   All sender systems encrypting the message are capable of sending CMS messages encrypted by several public keys.

-   All receiver systems verifying the CMS signature are capable of verifying CMS signatures signed with several private keys.

-   All receiver systems called by the outbound HTTPS channels can cope with different client certificates coming from the same tenant \(by using multiple certificate-user mappings\).


To prepare for the renewal process, the tenant administrator asks all the administrators of the sender and receiver systems whether their systems meet these requirements. If the answer is *yes*, the keys can be renewed by following three major steps:

1.  The tenant administrator provides all administrators of the sender and receiver systems with the X.509 certificate and the X.509 certificate chain of the new key pair.

    The administrators of the sender and receiver systems install these certificates in their systems so that the following conditions are met:

    -   The CMS decryptor decrypts the CMS message with the old and new private key \(the symmetric key is actually encrypted twice with the old and new private key\).

    -   The CMS verifier can verify CMS signatures signed by the old or new public key.

    -   The HTTPS server can cope with the old and new client certificate.


2.  The tenant administrator overwrites the old SAP key pair \(in the tenant's system keystore\) with the new SAP key pair by activating the new SAP key pair.

3.  The tenant administrator informs the administrators of the sender and receiver systems that the key has been renewed.

    The administrators then remove the old X.509 certificate from their system.


This process ensures that no downtime is necessary in message processing during key renewal.

> ### Tip:  
> You can see from this example that the tenant administrator has to have a good knowledge of the integration flow steps and channels where the key pair is used. Furthermore, the administrators of the sender and receiver systems have to know the capabilities of their systems.
> 
> If a sender/receiver administrator doesn't know whether the CMS decryptor component of his or her system is capable of creating a CMS Enveloped Data message where the symmetric key can be decrypted by two public keys, to be on the safe side we recommend that the sender and receiver system administrators and the tenant administrator agree on a downtime. During the downtime window, all involved parties adapt the configuration to the new key pair. Note that this downtime window can only be organized if the tenant administrator knows the administrators of the sender and receiver systems.

