<!-- loio4509f605e83c4c939a91b81eb3a6cdea -->

# Load Balancer Root Certificates Supported by SAP

The load balancer supports a certain list of root certificates.

A system sending a message to the Cloud-based integration platform using HTTPS as secure transport channel is not directly connected to the tenant. Instead of this, a load balancer component is interconnected that terminates all inbound HTTPS requests, and re-establishes a new secure connection.

To set up a secure connection between a sender system and the integration platform, you therefore need to make sure that the sender system's keystore contains a client certificate that is signed by one of those certification authorities \(CAs\) that are trusted by the load balancer component of SAP.

![](images/SAP_HCI_Onboarding_Inbound_Authentication_Certificates_38225ed.png)

For more information on the **root certificates** that are supported by the load balancer, check out SAP Note [2801396](https://me.sap.com/notes/2801396).

> ### Note:  
> A specific certificate that identifies a certification authority \(CA\) is referred to as *root certificate*. Such a certificate is typically not signed by any other authority, as it is *at the root* of a certificate chain.
> 
> The load balancer component is owned by SAP, and you, the customer, don't need to care how it is configured. However, you need to make sure that the client certificate in your sender keystore is signed by one CA that is listed at SAP Note [2801396](https://me.sap.com/notes/2801396).
> 
> Be aware that only **root certificates** are beeing imported into the *Keystore* of the *SAP Load Balancer*. Therefore you as a customer must always assign the whole certificate chain to the certificate to enable the connected component to evaluate the chain of trust.

