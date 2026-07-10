<!-- loio26c74164257f4b77a73def1b863a26e0 -->

# Configuring Additional Virtual Host

Configure and manage multiple virtual hosts under the default domain to expose APIs and MCP Servers through dedicated host names for improved routing and tenant segregation, for example across development, test, and production tenants.



## Prerequisites

Before configuring additional virtual hosts, ensure that:

-   You have the *PI\_Administrator* role assigned.
-   Integration Cell runtime is available and configured.
-   The virtual host limit for the runtime has not been reached.

    > ### Note:  
    > A maximum of 11 virtual hosts can be configured within a tenant.




## Context

**Why Use Multiple Virtual Hosts**:

By default, APIs are exposed through a single host under the default domain. As the API landscape grows, managing all APIs through one host can become difficult. Configuring multiple virtual hosts helps you:

-   Isolate APIs by environment, tenant, or use case
-   Simplify routing and hostname management
-   Expose APIs using dedicated hostnames
-   Improve scalability and operational flexibility

For example, if your backend service is hosted at `https://internal.services.local/orders`, you can expose it externally as `https://<api>.sapdomain.com/v1/orders`using a virtual host.





<a name="loio26c74164257f4b77a73def1b863a26e0__steps_rtg_fcn_jdc"/>

## Procedure

1.  Log on to the Integration Suite.

2.  From the left navigation pane, choose *Monitor* \> *Integrations and APIs*.

3.  From the *Runtime* dropdown in the top left corner, choose the*Integration Cell* to reveal the *Virtual Host* tile.

4.  Scroll down to the *Manage Virtual Host* section and select the *Virtual Host* tile.

5.  On the following screen, choose *Add*.

6.  In the *Add a Virtual Host* dialog, provide the required details:

    -   *Name*: Enter a unique name for the virtual host.

        > ### Note:  
        > The name **Default** is reserved and cannot be used for creating a virtual host.

    -   *Virtual Host*: Specify the host name prefix to be used with the default domain.

        > ### Note:  
        > The host alias can be up to 22 characters long and may include alphanumeric characters and hyphens \(-\). Note that it cannot begin with a hyphen.

    -   *Default*: This field cannot be edited. Newly created virtual hosts cannot be set as the default virtual host.
    -   *Client Certificate Authentication*: Choose the required client certificate authentication mode.
        -   *Optional* \(default\): Users can make the API call with or without a certificate.

        -   *Mandatory*: Only users with a Process Integration Runtime certificate instance can make the API call using the required certificates.

        -   *Disabled*: Users without a certificate are allowed to make the API call.



    If client cert authentication is optional or mandatory, and the authentication policy allows client certificate authentication, then the same certificate will be used to make the call and pass the authentication policy. For more information, see [Client Certificate Authentication for Integration Flow Processing](40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md).

7.  Choose *Add* to create the virtual host.


