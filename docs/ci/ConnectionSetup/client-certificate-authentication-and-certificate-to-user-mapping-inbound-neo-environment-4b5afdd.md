<!-- loio4b5afdd6bcbd4bc8a3d50d9ad2ef6482 -->

# Client Certificate Authentication and Certificate-to-User Mapping \(Inbound\), Neo Environment

This option includes an authentication step based on a digital client certificate and the mapping of the certificate to a user.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

With a certificate-to-user mapping, a certificate is mapped to a user, and that way the user can be authenticated based on a certificate.

> ### Note:  
> Note that multiple certificates can be mapped to one user \(n:1 certificate-to-user mappings possible\).

Certificate-to-user mappings make sure that a user is always associated with the certificate as a whole, not only with one attribute of it \(for example the common name \(CN\)\). As different certificates can have the same CN, mapping only the CN to a user name bears the risk that different certificates can be mapped accidentally to the same user. Using certificate-to-user mappings circumvents this risk.

For the user defined that way, in a subsequent step, an authorization step is being executed.



## How it Works

The following figure shows the complete setup of components and security artifacts required for this option.

![](images/Certificate-to-User_Mapping_6d7a978.png)

When you have configured this authentication option, the authentication of the user is performed in the following way at runtime:

The TLS connection of the sender system and the integration platform is terminated and newly established by the load balancer. This means, that first the load balancer authenticates itself against \(as server\) the sender based on the load balancer server certificate. Vice versa, the sender authenticates itself against the load balancer as client using the sender client certificate.

To enable the sender to communicate that way with the load balancer, the sender administrator has to make sure that the sender client certificate is signed by one of the certification authorities that are supported by the load balancer.

The load balancer sets the following message header fields:

-   `SSL_CLIENT_CERT`

    Contains the Base64-encoded sender client certificate.

-   `SSL_CLIENT_USER`


When the authentication is been executed successfully, the load balancer writes the sender client certificate \(base 64-encoded\) into the message header \(field SSL\_CLIENT\_CERT\). The tenant then maps the sender client certificate to a user based on the certificate-to-user mapping which is deployed on the tenant.

> ### Note:  
> In a subsequent step, the authorization check is executed for the default role \(ESBMessaging.send\) provided by SAP or a custom role configured in an adapter. You can define a custom role. For more information, read the blog on [How to Setup Secure HTTP Inbound Connection with Client Certificates](https://blogs.sap.com/2017/06/05/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client-certificates/).

