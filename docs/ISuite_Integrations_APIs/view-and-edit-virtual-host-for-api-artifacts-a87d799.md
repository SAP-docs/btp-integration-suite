<!-- loioa87d7990e2024251a439d8bed0d2f970 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# View and Edit Virtual Host for API Artifacts

Virtual host defines the public-facing hostname and base path through which your API and MCP server artifacts are exposed. During the setup of Integration Cell runtime, a default virtual host is created and configured. This virtual host is subsequently used for deploying API artifacts.



## Prerequisites

-   To edit or manage virtual hosts, you must have the required *PI\_Administrator* role collection should be assigned to you.

-   To view the list of available virtual hosts during API or MCP server deployment the *PI\_Integration\_Developer* role collection must be assigned.




<a name="loioa87d7990e2024251a439d8bed0d2f970__context_nqy_ljm_jdc"/>

## Context

You can view and edit this virtual host through the *Manage Virtual Host* tile on the *Monitor APIs* page.

> ### Note:  
> The *Manage Virtual Host* tile will be visible on the *Overview* page only when the *Integration Cell* runtime profile is activated. See [Activate Integration Cell](activate-integration-cell-1a627da.md).

> ### Note:  
> The virtual host configured in the API artifact at design time and the virtual host selected during deployment can be different. If you select a different virtual host during deployment, the runtime endpoint is generated using the deployed virtual host. Therefore, in *Monitor* \> *Manage Integration Content*, the URL for the API artifact displayed under *Endpoints* reflects the virtual host currently used by the deployed runtime artifact.
> 
> If the API artifact is configured with the virtual host `api-dev.company.com` at design time, but you select `api-prod.company.com` during deployment, the design-time configuration continues to show `api-dev.company.com`. However, after deployment, the endpoint URL displayed in *Monitor* \> *Manage Integration Content* uses `api-prod.company.com`, because it reflects the virtual host associated with the deployed runtime artifact.

To view and edit the virtual host, execute the following steps:



<a name="loioa87d7990e2024251a439d8bed0d2f970__steps_rtg_fcn_jdc"/>

## Procedure

1.  Log on to the Integration Suite.

2.  From the left navigation pane, choose *Monitor* \> *Integrations and APIs*.

3.  From the *Runtime* dropdown in the top left corner, choose the*Integration Cell* to reveal the *Virtual Host* tile.

4.  Scroll down to the *Manage Virtual Host* section and select the *Virtual Host* tile.

5.  On the following screen, search for a virtual host or select one from the list and choose the :pencil2: icon.

6.  On the *Edit Virtual Host* dialog, you can modify the *Vitual Host* alias and set the *Client Certificate Authentication* to the following:

    -   *Optional* \(default\): Users can make the API call with or without a certificate.

    -   *Enforced*: Only users with a Process Integration Runtime certificate instance can make the API call using the required certificates.

    -   *Disabled*: Users without a certificate are allowed to make the API call.


    > ### Note:  
    > For the Virtual Host named `default`, only the *Client Certificate Authentication* field can be edited. All other fields remain non-editable.

    > ### Note:  
    > The host alias can be up to 22 characters long and may include alphanumeric characters and hyphens \(-\). Note that it cannot begin with a hyphen.

7.  Choose *Save*.

    > ### Note:  
    > If client certificate authentication is optional or enforced, and the authentication policy allows client certificate authentication, then the same certificate will be used to make the call and pass the authentication policy. For more information, see [Client Certificate Authentication for Integration Flow Processing](40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md).


