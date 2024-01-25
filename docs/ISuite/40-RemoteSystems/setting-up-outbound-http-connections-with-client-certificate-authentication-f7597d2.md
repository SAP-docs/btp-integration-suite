<!-- loiof7597d23d8c34fffb997936f1b29e446 -->

# Setting Up Outbound HTTP Connections \(with Client Certificate Authentication\)

Using this option, authentication of Cloud Integration calling a receiver is performed based on a client certificate.



## Context

The following figure shows the involved components, digital keys, and storage locations. For more information on the tenant keystore that comes with Cloud Integration, see [Keystore](keystore-b163513.md).

![](images/SAP_HCI_Onboarding_Outbound_Authentication_Certificate_0ed06e8.png)

The table summarizes the required security artifacts required to set up this inbound authentication scenario and the configuration steps to be accomplished by the integration developer/tenant administrator and the administrator of the involved sender system.

-   For an overview of the procedure how to set up this authentication option, check out the numbered list below the following table.

-   For more information on how this authentication option works at runtime, check out: [Client Certificate Authentication \(Outbound\)](client-certificate-authentication-outbound-c4e4a15.md)

-   For an end-to-end description of the procedure, check out the following blog: [Cloud Integration – How to Setup Secure Outbound HTTP Connection using Keystore Monitor](https://blogs.sap.com/2017/06/19/cloud-integration-how-to-setup-secure-outbound-http-connection-using-keystore-monitor/) 



<table>
<tr>
<th valign="top">

Security Artifact

</th>
<th valign="top">

Used to ...

</th>
<th valign="top">

Configuration Steps

</th>
</tr>
<tr>
<td valign="top">

Tenant client certificate \(private/public key pair including certificate chain\)

</td>
<td valign="top">

Authorize Cloud Integration to call receiver.

At runtime, the identity of the Cloud Integration tenant is checked by the receiver by evaluating the client certificate chain of the tenant.

> ### Note:  
> In many cases, there is a multilevel setup of CAs so that a certificate is signed by an intermediate CA. The trustability of the intermediate CA is guaranteed by another intermediate CA one level higher, and so on, up to the root CA at the top of the **certificate chain**. In this case, it is necessary to assign the certificate chain to the certificate, to enable the connected component \(which has imported only the root CA into its keystore\) to evaluate the chain of trust.



</td>
<td valign="top">

Tenant administrator:

-   Generate key pair or use preinstalled one.

    You can use the preinstalled key pair with alias *sap\_cloudintegrationcertificate*.

    This key pair is already part of the tenant keystore \(provided by SAP together with the tenant\).

    > ### Note:  
    > This key pair is **not** preinstalled when you operate a Cloud Integration trial tenant.

-   Hand over the public key \(tenant client certificate\) to the receiver administrator.

    In the tenant keystore, check out the *Key Pair* entry used for this connection and can download the public part from there.


More information:

[Keystore](keystore-b163513.md)

[Managing Keystore Entries](../50-Development/managing-keystore-entries-2dc8942.md)

</td>
</tr>
<tr>
<td valign="top">

Tenant client root certificate \(identifies CA that has signed the tenant client certificate\)

</td>
<td valign="top">

Sign tenant client certificate.

This certificate is required to identify the root CA that is at the top of the certificate chain that ultimately guarantees the trustability of the tenant client certificate.

</td>
<td valign="top">

Receiver administrator:

-   Get tenant client root certificate from tenant administrator.

-   Add certificate to receiver keystore.




</td>
</tr>
<tr>
<td valign="top">

Tenant client certificate \(public key\)

</td>
<td valign="top">

Check trustworthiness of the Cloud Integration tenant at the receiver side based on this certificate.

</td>
<td valign="top">

Receiver administrator:

-   Get tenant client certificate from tenant administrator.

-   Add certificate to receiver keystore.




</td>
</tr>
<tr>
<td valign="top">

Receiver server certificate \(signed by CA with which the tenant has a trust relationship\)

</td>
<td valign="top">

Qualify receiver as trusted component \(for Cloud Integration tenants that like to connect to it\).

This certificate is required to identify the receiver \(to which the tenant connects as the client\) as a trusted server.

</td>
<td valign="top">

Receiver administrator:

-   Create server certificate \(key pair\) and import it into the receiver keystore. This certificate can be a certificate chain where the top-level certificate is a root certificate issued by a dedicated CA.

    When you configure an integration with an SAP system as receiver, check out the corresponding integration guide \(which you typically find as part of the related integration content package\). In such a guide, you find more information on the required certificates.

-   Download root certificate from the receiver keystore and make it available to the tenant administrator.




</td>
</tr>
<tr>
<td valign="top">

Receiver server root certificate

</td>
<td valign="top">

Make Cloud Integration trust the receiver.

This certificate is required to identify the root CA that is at the top of the certificate chain that ultimately guarantees the trustability of the receiver server certificate.

</td>
<td valign="top">

Tenant administrator:

Import this certificate into the tenant keystore.

</td>
</tr>
</table>

In the related receiver adapter, as *Authentication* choose *Client Certificate*. Optionally, you can enter a *Private Key Alias* to specify a dedicated key to be used for this step.



## Procedure

1.  Maintain the tenant keystore.

    To enable the tenant to authenticate itself as client against the receiver, a keystore with a valid client certificate has to be deployed on the tenant.

    Note that the tenant provided initially by SAP has already a keystore deployed that contains an initial set of security artifacts. The already available key pair might be suitable to set up the outbound connection.

    The keystore also has to contain a certificate of the certification authority \(CA\) that has signed the server certificate of the receiver system.

    Import the receiver server root certificate into the tenant keystore. To get this certificate, you've the following options:

    -   Get certificate handed over by receiver administrator.

    -   Apply the outbound *Connectivity Test* against the receiver system.

        More information: [Performing Connectivity Tests](../50-Development/performing-connectivity-tests-d5b2fae.md)

        For an example how to get such a certificate for an email server \(as receiver system\), check out: [Update the Tenant Keystore with the Certificates Required by the Mail Server](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/5d5495ed1d94477abaa009984285e483.html "Add the required server root certificates (required by the e-mail provider) to the tenant keystore.") :arrow_upper_right:


2.  Configure the receiver keystore.

    In the same way as for the tenant keystore, generate a public/private key pair, create a certificate signing request and get the certificate signed by a CA. Note that this must be the CA which root certificate is also obtained in the tenant keystore.

    More information:

    [Creating X.509 Keys](creating-x-509-keys-ec605c7.md)

3.  Configure the security-specific settings in the related integration flow.

    1.  Open the SAP Integration Suite design section for integration flows.

    2.  To create and design integration flows, go to the *Design* tab.

    3.  Open the related receiver adapter \(that is used to specify the connection of the tenant with the receiver system\) and as *Authentication* choose *Client Certificate*.

        Optionally, you can enter a *Private Key Alias* to specify a dedicated private key from the tenant keystore \(tenant client certificate\) to be used for this step.



**Related Information**  


[Client Certificate Authentication \(Outbound\)](client-certificate-authentication-outbound-c4e4a15.md "")

[Blog: Cloud Integration – How to Setup Secure Outbound HTTP Connection using Keystore Monitor](https://blogs.sap.com/2017/06/19/cloud-integration-how-to-setup-secure-outbound-http-connection-using-keystore-monitor/)

