<!-- loio09d7783b16e04b0ab0e14713ab506ec4 -->

# Enable Client Applications

Before a client application can consume a business data graph, it must know certain secrets, known as *Graph service credentials* \(Graph root URL, security service URL, client ID, and client secret\).

This is satisfied by creating a *Graph service instance* and a service binding.

After creation of the Graph service instance and service binding, Graph API consumers must use service bindings to acquire an access token. The access token can be obtained from a security service during authentication. For more information, see [Authentication](authentication-79aabda.md).

> ### Note:  
> Sharing service bindings enables any client application to consume Graph APIs. From a security perspective, create a dedicated service instance per client application. This helps tracking, auditing, and if necessary, revoking the credentials of a client application, without affecting others.



<a name="loio09d7783b16e04b0ab0e14713ab506ec4__section_mnk_dlv_hzb"/>

## Prerequisites

You have already configured an entitlement for Graph. For more information, see [Configure Entitlement for Graph](initial-setup-12ad448.md#loio12ad448225ac47049982d9faab7978a3__section_configEntitlement).



<a name="loio09d7783b16e04b0ab0e14713ab506ec4__section_af4_wll_jyb"/>

## Create a Graph Service Instance

1.  In the SAP BTP cockpit, go to *Services* \> *Instances and Subscriptions*.

2.  In the top-right corner, choose *Create*. The *New Instance or Subscription* wizard opens.

3.  Select the *Graph* service from the dropdown menu and enter the basic information for your instance.
4.  Select *api* for your service plan.
5.  Select *Other* for your runtime environment.
6.  Enter a name for your instance, and choose *Next*.
7.  Configure instance parameters by uploading a JSON file, or configure the parameters in the text box, and choose *Next* or *Create*. The default OAuth security configuration only supports applications that are run from a localhost. To support other apps that can access this instance of Graph, you must add them to an allowlist by adding redirect URIs as follows:

    ```json
    {
      "xs-security": {
        "xsappname": "<unique-string>",
        "oauth2-configuration": {
          "redirect-uris": [
            "http://localhost:*/**",
            "https://<client-application-domain-name>/<callback-path>"
          ]
        }
      }
    }
    ```

    In development subaccounts, it is common for developers to use `localhost` hosted applications for testing purposes. Redirect URIs can contain wildcards, for example, `https://*.bestrun.com`. The `xsappname` should be unique, for example, a universally unique identifier \(UUID\). For more information, see *oauth2-configuration* in [Application Security Descriptor Configuration Syntax](https://help.sap.com/viewer/4505d0bdaf4948449b7f7379d24d0f0d/2.0.06/en-US/6d3ed64092f748cbac691abc5fe52985.html).

8.  Review and verify the instance details, and choose *Create*.



<a name="loio09d7783b16e04b0ab0e14713ab506ec4__section_xkp_zll_jyb"/>

## Create and Download a Service Binding

Developers or applications that want to access the Graph API require a service binding to obtain the access credentials to the service instance of a service that they want to consume.

1.  In the SAP BTP cockpit, go to *Services* \> *Instances and Subscriptions* and choose *...* to the right of your service instance.

2.  Select *Create Service Binding*, enter any name, and choose *Create*.

3.  Choose the *...* to the right of the service binding to download it as a text file and send it to the relevant stakeholder.


For more information, see [Creating Service Bindings in Other Environments](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/55b31ea23c474f6ba2f64ee4848ab1b3.html).

