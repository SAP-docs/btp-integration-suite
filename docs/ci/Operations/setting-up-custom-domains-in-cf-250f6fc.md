<!-- loio250f6fc282e24a0180f396997d96a5c7 -->

# Setting-Up Custom Domains in CF

Allows you to customize the default tenant URL.

There are use cases where you don’t wish to expose the default domain provided by SAP Cloud Integration. In such a scenario, you can construct custom domain names and TLS settings for a specific Cloud Integration instance. In the following you can configure a custom domain for accessing the runtime worker, for example `runtime.subdomain.mydomain.com`.

> ### Note:  
> When you've set up a custom domain, there are currently the following limitations:
> 
> -   To access Cloud Integration through your browser \(to perform tasks such like integration flow design, monitoring, for example\), you need to use the URL that contains the original SAP domain provided when subscribing to Cloud Integration service. Currently, it's not possible to access the Cloud Integration user interface through an address that contains your custom domain.
> 
> -   You can use runtime URLs containing the custom domain to call integration flows with HTTP-based sender adapters. However, when checking the endpoint URL of your integration flows in the *Monitor* application \(under *Manage Integration Content*\), the original SAP domain is shown in the base address of the endpoint URL, not the custom domain. If you develop a workaround to relate both endpoint URLs with each other, note that you know the mapping between both: You anyway need to execute this mapping when setting up the custom domain.

1.  **Initial Steps:**

    To use the Custom Domain Service you have to complete some initial steps, described here: [Initial Setup](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/108177aea2a04d1b9006d96173bfa99a.html).

2.  **Prerequisites** 

    Before configuring custom domains, you have to fulfill a number of prerequisites. See: [Prerequisites](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/48cdbe7a64f3475586dc2f4d11c5603c.html).

3.  **Configuring Custom Domains**
    1.  To get a better overview of the creation process of custom domains with TLS/SSL server authentication, see: [Creating Custom Domains with TLS/SSL Server Authentication](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/afeb1e77fc2f4365803049e9407449eb.html).

        1.  To create custom domains, see: [Create Custom Domains](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/2ab0040222ce4c018dfe798be13be379.html).

        2.  To create a certificate signing request, see: [Create a Certificate Signing Request](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/ce1c42b909b34eedafe1f9eecc15ddfa.html). We recommend to create a wildcard certificate for both custom domains.
        3.  To upload and activate the signed certificate, see: [Upload and Activate the Signed Certificate](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/908a691a2465493e8adaf36a9f21eff0.html).
        4.  To configure the DNS for a custom domain, see: [Configure the DNS for a Custom Domain](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/da9b54e5b9b54fbaa2b381af2bd15bc8.html).

    2.  To map the Cloud Integration instance to a custom domain, see: [Map a SaaS Application to a Custom Domain](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/9f029c0ba0ab496fa2767b607eae924f.html).

        Mapping example for the runtime:

        ```
        cf custom-domain-map-route <tenantname.landscape-runtimeid.cfapps.datacentername.hana.ondemand.com> <runtime.subdomain.mydomain.com>
        ```

    3.  To test your custom domain, and make sure it's reachable and secured by a certificate, send a *postman* request to the runtime URL.

        Remember that certain steps during the setup process of your custom domain can take up to 24 hours and the DNS configuration can take several hours depending on your provider.

    4.  To add trusted certificates for client authentication to a custom domain, see: [Adding Trusted Certificates for Client Authentication to a Custom Domain](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/a85e3c414a4d4a9fb406215acb6bfce1.html).

4.  **Managing Custom Domains**

    To manage custom domains, check the steps described in: [Managing Custom Domains](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/4651cdc79a1c49878e340e0448e5d0e6.html).

5.  **Removing the Custom Domain Service Instance** 

    To remove the Custom Domain Service Instance, see [Remove the Custom Domain Service Instance](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/8f845329f83f402eb59e8d3b7735754b.html).


If you encounter issues with your custom domains, we recommend that you follow the procedure described in [Monitoring and Troubleshooting](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/8987a2dfc5694b11876726f65daa0e06.html).

