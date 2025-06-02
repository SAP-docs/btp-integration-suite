<!-- loioab81b845230742b4aa863fb27644d439 -->

# Deploy the Edge Integration Cell Solution

Get to know the steps needed to create the Edge Node as a *Runtime Location* in SAP Integration Suite.



<a name="loioab81b845230742b4aa863fb27644d439__prereq_nbs_lth_vlb"/>

## Prerequisites

> ### Note:  
> Edge Integration Cell exposes API and Integration Flow endpoints for access by clients. The URL to be used is defined by a Virtual Host. A Virtual Host holds all information required to handle \(m\)TLS handshakes, the actual domain name, TLS key, server, and Trust CA certificates. For Edge Integration Cell, a Default Virtual Host name has to be chosen. Additionally, a key pair needs to be provided, referenced via a Default Virtual Host Key Alias. Currently, a predefined list of Trust CAs is supported.
> 
> The approach is comparable to the configuring custom domains approach for SAP Cloud Integration. Custom Domains are used if you don't wish to expose the default domain provided by SAP Cloud Integration. In such a scenario, you can construct custom domain names and TLS settings for a specific Cloud Integration instance. For more information, see [Configuring Custom Domains](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7230b9ff41914cc0969223e6a020104b.html "Allows you to customize the default tenant URL or domain as per your needs and access the tenant using your own the domain.") :arrow_upper_right:.
> 
> For Edge Integration Cell, you define exactly your custom domain using the Default Virtual Host.

-   The Edge Node is in status *Available*.

-   You've a domain name to be used for exposing the Edge Integration Cell endpoints.

-   You have a valid key pair for the domain name to enable TLS for the Istio gateway configuration. For more information, see [Managing Keystore Entries](50-Development/managing-keystore-entries-2dc8942.md).

-   You've a load balancer to be used for exposing the Edge Integration Cell endpoints. On cloud platforms, a load balancer is an infrastructure service, which is available out of the box. For other environments, it has to be be part of your Kubernetes infrastructure.

-   For production environments, you've set up external services for PostgreSQL and Redis.

-   You've set up storage classes for dynamic provisioning.




## Procedure

1.  Open the Edge Lifecycle Management user interface.

2.  Go to the *Edge Nodes* tab.

3.  Select the Node where you want to deploy the solution.

4.  Choose *Deploy Solution*. The system opens a dialog box in which you can select the solution that you want to deploy, select its version, and provide the solution properties.

5.  Select *Edge Integration Cell* as the solution name. The version of the solution is selected automatically. Dependent solutions EdgeIntegration Cell Services and Istio are deployed as part of Edge Integration Cell.

6.  Enter the following properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Shared File System
    
    </td>
    <td valign="top">
    
    A shared file system can be enabled to preserve traces or dumps. This option is recommended especially for production environments.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Shared File System Storage Class \(only visible if shared file system is enabled\)
    
    </td>
    <td valign="top">
    
    Enter storage class for access mode `ReadWriteMany` and binding mode `Immediate`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Default Virtual Host
    
    </td>
    <td valign="top">
    
    Custom domain name used for exposing Edge Integration Cell endpoints.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Default Virtual Host Key Alias
    
    </td>
    <td valign="top">
    
    Key pair alias used for TLS enablement.

    You've to create the virtual host key alias and choose a name for it. The chosen name is needed to upload the virtual host key alias to the keystore.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Enable Default Virtual Host HTTP**
    
    </td>
    <td valign="top">
    
    By default, Edge Integration Cell endpoints are exposed via Ingress Gateway on port 443 \(HTTPS\). If needed, you can also enable port 80 \(HTTP\) for unencrypted communication.

    > ### Caution:  
    > -   HTTP-based communication doesn't have built-in transport layer security and doesn't protect secrets in transit. For more information, see [Security Considerations](https://www.rfc-editor.org/rfc/rfc9110.html#name-security-considerations) 
    > 
    > -   The authentication method is limited to HTTP Basic Authentication.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Enable SNC for RFC Adapter**
    
    </td>
    <td valign="top">
    
    Choose this option to set up SNC for secure communication over the RFC protocol. It is strongly recommended to enable this option if using the RFC adapter productively. For more information, see [Set Up SNC on Edge Integration Cell](60-Security/set-up-snc-on-edge-integration-cell-c2315d3.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **SNC File System Storage Class \(only visible if SNC for RFC Adapter is enabled\)**
    
    </td>
    <td valign="top">
    
    Enter the storage class for the access mode `ReadWriteMany` and the binding mode `Immediate`.
    
    </td>
    </tr>
    </table>
    
7.  Choose *Next Step*.

8.  Enter the following properties:

    ****


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Multi-AZ Support
    
    </td>
    <td valign="top">
    
    If your Kubernetes cluster nodes are distributed across availability zones, you can enable this property for your deployment. It has no effect otherwise.

    On cloud platforms, multiple availability zones are available.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message Service Storage Class
    
    </td>
    <td valign="top">
    
    Option to use a dedicated storage class \(access mode `ReadWriteOnce`\).

    If this field is left empty, the default storage class is used.

    For more information, see [3247839](https://me.sap.com/notes/3247839).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Message Service Pod Initializer
    
    </td>
    <td valign="top">
    
    Option to use a Mutating Webhook that optimizes resource usage for the Message Service in a HA environment.

    The monitoring pod \(Pod 2 in the Stateful Set\) requires less CPU and memory.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message Service Scaling Tier
    
    </td>
    <td valign="top">
    
    Select Message Service Scaling Tier.

    For more information, see [3247839](https://me.sap.com/notes/3247839).

    > ### Note:  
    > Choose the Message Service Scaling Tier carefully, as it can't be changed after the initial deployment using the Edge LM UI.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable External DB
    
    </td>
    <td valign="top">
    
    Select this option for production environments.

    > ### Note:  
    > You need to provide a new, empty database schema for each new deployment.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Database Type
    
    </td>
    <td valign="top">
    
    Database Type will be implicitly defined by selecting External DB.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    PostgreSQL Storage Class \(only visible if External DB isn't enabled\)
    
    </td>
    <td valign="top">
    
    Option to use a dedicated storage class \(access mode `ReadWriteOnce`\).

    If this field is left empty, the default storage class is used.

    For more information, see [3247839](https://me.sap.com/notes/3247839).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External DB Hostname \(visible if External DB is enabled\)
    
    </td>
    <td valign="top">
    
    Enter hostname of PostgreSQL database.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External DB Port \(visible if External DB is enabled\)
    
    </td>
    <td valign="top">
    
    Enter port of PostgreSQL database.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External DB Name \(visible if External DB is enabled\)
    
    </td>
    <td valign="top">
    
    Enter name of PostgreSQL database.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External DB Username \(visible if External DB is enabled\)
    
    </td>
    <td valign="top">
    
    Enter username to connect to PostgreSQL database.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External DB Password \(visible if External DB isnullnullnull
    
    </td>
    <td valign="top">
    
    Enter password to connect to PostgreSQL database.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External DB TLS Root Certificate Password \(visible if External DB is enabled\)
    
    </td>
    <td valign="top">
    
    Upload Trust CA certificate to connect to PostgreSQL database using TLS. CA certificate in PEM format \(Base64 ASCII\), should include only Root CAs required to connect \(size limit 5kB\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable External Redis
    
    </td>
    <td valign="top">
    
    Select this option for production environments.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Datastore Type
    
    </td>
    <td valign="top">
    
    Datastore Type will be implicitly defined by selecting External Redis.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Redis Storage Class \(only visible if External Redis is enabled\)
    
    </td>
    <td valign="top">
    
    Option to use a dedicated storage class \(access mode `ReadWriteOnce`\).

    If this field is left empty, the default storage class isn't used.

    For more information, see [3247839](https://me.sap.com/notes/3247839).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External Redis Addresses \(only visible if External Redis is enabled\)
    
    </td>
    <td valign="top">
    
    Enter comma-separated list of addresses in format HOST:PORT \(with write access\). For sentinel mode, this option represents the list of sentinel addresses.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External Redis Mode \(only visible if External Redis is enabled\)
    
    </td>
    <td valign="top">
    
    Select Redis mode \(Cluster, Sentinel, Standalone\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External Redis Username \(only visible if External Redis is enabled\)
    
    </td>
    <td valign="top">
    
    Enter username to connect to Redis \(if username enabled\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External Redis Password \(only visible if External Redis is enabled\)
    
    </td>
    <td valign="top">
    
    Enter password to connect to Redis \(password protected required\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External Redis Sentinel Username \(only visible if External Redis is enabled\)
    
    </td>
    <td valign="top">
    
    Enter username to connect to Redis Sentinel \(for Sentinel mode only\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External Redis Sentinel Password \(only visible if External Redis is enabled\)
    
    </td>
    <td valign="top">
    
    Enter password to connect to Redis Sentinel \(for Sentinel mode only\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External Redis TLS Certificate \(only visible if External Redis is enabled\)
    
    </td>
    <td valign="top">
    
    Upload Trust CA certificate to connect to external Redis using TLS.CA certificate in PEM format \(Base64 ASCII\), should include only Root CAs required to connect \(size limit 5kB\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External Redis Server Name \(only visible if External Redis is enabled\)
    
    </td>
    <td valign="top">
    
    Enter server name, required only if the server’s certificate doesn't have IP Subject Alternative Names \(SAN\).
    
    </td>
    </tr>
    </table>
    
9.  Choose *Next Step*.

10. Enter the following properties:

    ****


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    HTTP version 1.0
    
    </td>
    <td valign="top">
    
    Select this option to enable HTTP 1.0 for inbound Edge Integration Cell endpoints.

    Otherwise, only HTTP 1.1 is supported.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client IP Preservation
    
    </td>
    <td valign="top">
    
    Select this option if a client’s source IP is to be preserved. This option requires to have a network load balancer capable of forwarding the source IP. On cloud platforms, a network load balancer is used for this option.

    This option is a prerequisite for using client IP filtering policies. For more information, see [https://istio.io/latest/docs/tasks/security/authorization/authz-ingress/\#network](https://istio.io/latest/docs/tasks/security/authorization/authz-ingress/#network).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Load Balancer Provider
    
    </td>
    <td valign="top">
    
    Select the Load Balancer Provider. Based on the provider, you can enable an internal Load Balancer.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Port 80
    
    </td>
    <td valign="top">
    
    Choose this option to enable port 80 on the Istio Ingress Gateway, necessary when the *Enable Default Virtual Host HTTP* setting is enabled.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Internal Load Balancer \(only visible if Load Balancer Provider AWS or Azure is selected\)
    
    </td>
    <td valign="top">
    
    Select this option if you want to enable an internal Load Balancer.
    
    </td>
    </tr>
    </table>
    
11. Choose *Deploy*.

    The deployment of the solution starts with the deployment of the dependent solutions Istio and Edge Integration Cell Services. Once the deployment of independent solutions is complete, the deployment of Edge Integration Cell starts automatically. Edge Lifecycle Management deploys solutions based on helm charts.

12. After the successful deployment of the solution, assign the new runtime to a new or existing keystore. For more information see, [Interact with Keystores from Edge Integration Cell](interact-with-keystores-from-edge-integration-cell-d4972b8.md).

    > ### Note:  
    > You can either create a new keystore and assign the runtime to it or you can assign the runtime to an existing keystore. Consider the following limitations:
    > 
    > You can assign up to 20 runtimes to a single keystore.
    > 
    > The maximum permissible size for a keystore, which an edge runtime is assigned to, is 1 MB.
    > 
    > While a runtime can only be assigned to one keystore, a single keystore can accommodate multiple runtimes.
    > 
    > If an existing keystore is utilized again, shared access will be granted to all runtimes assigned to it.
    > 
    > The keystore becomes exclusive to a particular runtime if only one runtime is assigned to it.
    > 
    > You can assign a runtime to the SAP pre-delivered or *system* keystore, given that its size doesn't exceed the 1 MB restriction.

    > ### Caution:  
    > Be aware that changing the assigned keystore of a specific runtime after its initial setup could lead to errors in message processing. This is because the keystore becomes temporarily unavailable during the changeover process. For this reason, an initial careful selection of the runtime to a keystore is crucial.

13. To upload the key pair for the default virtual host into the keystore which you have assigned to the new runtime, choose the *Keystore* tile in the *Manage Security* section. Use the alias that you specified as the *Default Virtual Host Key Alias* during the deployment of the ELM solution as your alias. For instance "edge.integration.int.cloud.sap". For more information, see [Uploading a Key Pair](50-Development/uploading-a-key-pair-083911e.md).




<a name="loioab81b845230742b4aa863fb27644d439__result_oys_hz4_fvb"/>

## Results

TheEdge Integration Cell product profile is created, and is automatically enabled for consumption in design time.

**Related Information**  


[Modify Edge Integration Cell Solution Deployment Properties](modify-edge-integration-cell-solution-deployment-properties-6a060ff.md)

