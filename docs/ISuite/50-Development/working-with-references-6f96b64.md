<!-- loio6f96b64eade84096b6de0322867a97aa -->

# Working with References

A reference is a variable that holds the name of the keystore or truststore, instead of directly specifying the name in the virtual host configuration.

The benefit of using a reference is that you can easily change the value of the reference to switch the keystore or truststore used by the virtual host. This is particularly useful when the current keystore or truststore's certificate is about to expire.

> ### Note:  
> References can only be used for the keystore and truststore, not for the certificates.
> 
> When changing the reference to a keystore, make sure that the alias name of the certificate remains the same as in the old keystore.

> ### Note:  
> When configuring a virtual host, you have the option to specify a keystore or truststore using a reference. For more information on how to configure custom domain virtual host and client certificate based authentication using references, see [Configuring Additional Virtual Host in Cloud Foundry Environment](../configuring-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md).

You can create, update, fetch and delete any certificate store references via service calls. For more information, see the following:

