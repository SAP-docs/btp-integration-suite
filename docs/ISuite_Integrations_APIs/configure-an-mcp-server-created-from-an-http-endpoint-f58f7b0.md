<!-- loiof58f7b04b86246419563fba744f073bd -->

# Configure an MCP Server Created from an HTTP Endpoint

After creating an MCP server from an HTTP endpoint, you can customize its behavior, secure access, and define how AI agents interact with the exposed HTTP endpoint.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

An MCP server created using an HTTP endpoint is a versioned entity that you can manage independently within Integration Suite. While its initial structure \(such as resources and tools\) is derived from the source API, you can further enrich and manage it by:

-   Selecting and refining API resources and tools exposed to AI agents
-   Defining prompts to guide how agents interact with these tools
-   Applying policies to enforce security, traffic control, and governance

In addition, if the underlying API artifact is updated \(for example, new endpoints or modified operations\), you can use the synchronize option to align the MCP server with the latest API definition without recreating it.



## MCP Configuration

In the MCP Configuration tab, you can configure the core capabilities exposed by the MCP server. You can view the source and add or manage tools, resources, and prompts available to AI agents.



### Source

-   The *Source* tab lets you view the HTTP endpoint configured as the source for the MCP server.
-   Depending on how the MCP server was created, the source is either a **URL** or a **SAP BTP destination**.
-   You can update the source configuration and use *Edit API Specification* to modify the API specification that defines the tools and resources exposed by the MCP server.

    > ### Note:  
    > The OpenAPI specification must be a version between 3.0.0 and 3.0.3. Swagger 2.0 and earlier versions are not supported.




### Tools

You can expose specific API resources as MCP tools. These tools allow AI agents to interact with your API in a structured and controlled way.

To add and define MCP tools:

1.  Go to the *MCP Configuration* \> *Tools* tab and choose *Add*.
2.  Select the API operations that you want to expose as tools based on the HTTP method and resource path, and choose *Add*.

> ### Note:  
> Each MCP server supports up to 15 tools.

The selected operations are added as tools. For each tool, you can:

-   Review or modify the **Name**, **Title**, and **Description**.

-   View the corresponding HTTP **method** and resource **path**.

-   Review the **input schema** and **output schema** derived from the API operation. The input schema defines the parameters that an AI agent can provide when invoking the tool, while the output schema defines the structure of the response returned by the tool.

-   Compare the tool schema with the source API schema using **API Reference**.




### Resources

You can expose API resources as MCP resources, allowing AI agents to access data and context from your API.

1.  Go to *MCP Configuration* and choose the *Resources* tab. Choose *Add* to open the resource selection dialog.

2.  Select the API resources that you want to expose and choose *Add* to include them in your MCP server.

    > ### Note:  
    > -   Only the API resources with GET method will be listed for MCP resources.
    > -   Each MCP server supports up to 15 resources.


The selected API resources are added as MCP resources. For each resource, you can:

-   Review or modify the **Name**, **Title**, and **Description**.

-   View the corresponding HTTP **method**, resource **path**, and **response content type**.

-   Review the **resource schema** derived from the API operation. The resource schema defines the URI template used to access the resource and the MIME type of the content returned.

-   Use **API Reference** to review the corresponding source API operation and its parameters.




### Prompts

Prompts define reusable interaction patterns that AI agents can use to interact with an MCP server in a consistent and structured way.

To add and define an MCP prompt:

1.  Go to *MCP Configuration* and choose the *Prompts* tab, and choose *Add*.

2.  In *Define Prompt*, provide a **Name**, **Title**, and **Description**, and choose *Next*.

3.  In *Define Arguments*, define the following input arguments for the prompt and choose *Next*:

    -   Specify a **Name** for the argument.

    -   Optionally, provide a **Title** and **Description**.

    -   Select **Required** if the argument is mandatory.

    -   Add additional arguments if needed.


4.  In **Define Messages** dialog, select a role and enter the corresponding message content:

    -   **User**: Represents input or a request from the user.

    -   **Assistant**: Represents a response, instruction, or context provided by the assistant.

    -   Add additional messages as needed to define the interaction flow.


5.  Choose **Add** to save the prompt.

    > ### Note:  
    > To define a prompt, you must define the prompt and messages. Defining arguments is optional.




## MCP Policy Configuration

Policies govern how tools are accessed and executed.

1.  Navigate to the *Policies* tab.
2.  Add and configure policies as needed. See, [Add Policies to Artifacts](add-policies-to-artifacts-c2b3e56.md) 

    > ### Note:  
    > -   By default, **Authentication** and **Authorization** policies are applied to an MCP server. These policies are mandatory and cannot be deleted.
    > 
    > -   The **Authentication** policy must always be the first policy in the request flow. Only **OAuth-based authentication** is supported for an MCP server.
    > 
    > -   If the MCP server is created from an API artifact, the **Authentication** policy configuration is inherited from the source API artifact.
    > 
    > 
    > The following policies are supported for MCP servers and can be configured under the *Policies* section:
    > 
    > -   Traffic Management: [Quota](quota-2aecf15.md), [Surge Protection](surge-protection-3d14745.md), and [IP Filter](ip-filter-3a8b424.md) 
    > 
    > -   Security Policies: [Authentication](authentication-fa6eec4.md) and [Authorization](authorization-6658409.md)
    > 
    > 
    > By default, all MCP tools are protected with an Authentication and Authorization policy. This ensures that only authenticated and authorized AI agents—typically with proper credentials and identity assertions—can invoke the tool. To maintain system performance and prevent overload during traffic spikes, you can configure a Surge Protection Policy—for example, limit each agent to 4 calls every 10 seconds. Any calls beyond this threshold will be temporarily blocked or throttled to protect backend systems.




## MCP Adapter Configuration

Adapters define how an MCP server receives requests from AI agents and communicates with the target backend service.

Every MCP server contains two adapters:

-   **MCP Sender Adapter** – Receives incoming requests from AI agents and exposes the MCP endpoint. This adapter is created automatically and cannot be modified.

    **Configuration Properties**


    <table>
    <tr>
    <th valign="top">

    Section
    
    </th>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Value/Options
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    General
    
    </td>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Specifies the name of the sender adapter. By default, the value is **MCP**.
    
    </td>
    <td valign="top">
    
    MCP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Specifies an optional description for the sender adapter. Use this field to provide additional information about the adapter configuration.
    
    </td>
    <td valign="top">
    
    User-defined
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Adapter Type
    
    </td>
    <td valign="top">
    
    Displays the type of the sender adapter. The value is **MCP** and is read-only. The MCP sender adapter receives incoming Model Context Protocol \(MCP\) requests from AI agents and exposes the MCP server endpoint.
    
    </td>
    <td valign="top">
    
    MCP
    
    </td>
    </tr>
    </table>
    
-   **HTTP Receiver Adapter** – The HTTP receiver adapter forwards requests from the MCP server to the configured HTTP endpoint. Depending on how the MCP server is created, the receiver adapter can connect to the backend using either a **URL** or an **SAP BTP destination**.

    -   **HTTP Receiver Adapter \(URL-based\)**: Use this option when the backend service is accessible through a direct HTTP endpoint.

        **Configuration Properties**


        <table>
        <tr>
        <th valign="top">

        Section
        
        </th>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Description
        
        </th>
        <th valign="top">

        Value/Options
        
        </th>
        </tr>
        <tr>
        <td valign="top" rowspan="3">
        
        General
        
        </td>
        <td valign="top">
        
        Name
        
        </td>
        <td valign="top">
        
        Name of the receiver adapter channel.
        
        </td>
        <td valign="top">
        
        HTTP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Description
        
        </td>
        <td valign="top">
        
        Optional description for the adapter.
        
        </td>
        <td valign="top">
        
        User-defined
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Adapter Type
        
        </td>
        <td valign="top">
        
        Type of adapter used for backend communication.
        
        </td>
        <td valign="top">
        
        HTTP
        
        </td>
        </tr>
        <tr>
        <td valign="top" rowspan="5">
        
        Connection
        
        </td>
        <td valign="top">
        
        Type
        
        </td>
        <td valign="top">
        
        Displays the type of backend connection. When the MCP server is created from an API artifact, the value is **API** and is read-only.
        
        </td>
        <td valign="top">
        
        API
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication
        
        </td>
        <td valign="top">
        
        Authentication mechanism used to invoke the backend service.
        
        </td>
        <td valign="top">
        
        Defines how the tenant \(as the HTTP client\) authenticates itself against the receiver.

        You can select one of the following authentication methods:

        -   Basic

            The tenant authenticates itself against the receiver using user credentials \(user name and password\).

        -   None

            When not to use any authentication can include, but not limited to, the following cases:

            -   If the target system that you want to communicate doesn't require any authentication.

            -   If you want to set an authorization header via a Content Modifier step before the adapter.

            -   If you want to set an authorization header via a Script step before the adapter.


        -   OAuth2 Client Credentials

            Use this grant type to access web resources by authorizing the client application to perform required actions on behalf of a user.

        -   Client Certificate

            The tenant authenticates itself against the receiver using a client certificate.

            It's a prerequisite that the required key pair is installed and added to a keystore. This keystore has to be deployed on the related tenant. The receiver side has to be configured appropriately.



        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Timeout \(in ms\)
        
        </td>
        <td valign="top">
        
        Specifies the time, in milliseconds, that the receiver adapter waits for a response from the backend service before the request times out.

        The default value is 60000 milliseconds \(1 minute\).
        
        </td>
        <td valign="top">
        
        60000
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Request Headers
        
        </td>
        <td valign="top">
        
        Specifies the request headers that are forwarded to the target MCP Server. You can specify individual headers or use wildcard patterns \(for example, \*\).
        
        </td>
        <td valign="top">
        
        User-defined
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Response Headers
        
        </td>
        <td valign="top">
        
        Specifies the response headers returned by the MCP server that are propagated back to the API artifact. You can specify individual headers or use wildcard patterns \(for example, \*\).
        
        </td>
        <td valign="top">
        
        User-defined
        
        </td>
        </tr>
        </table>
        
    -   -   **HTTP Receiver Adapter \(Destination-Based\)**: Use this option when the backend service is accessed through an SAP BTP destination. The receiver adapter uses the connection details defined in the destination, including the endpoint URL, authentication, and proxy configuration.


    <table>
    <tr>
    <th valign="top">

    Section
    
    </th>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Value/Options
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    General
    
    </td>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Name of the receiver adapter channel.
    
    </td>
    <td valign="top">
    
    User-defined
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Optional description for the adapter.
    
    </td>
    <td valign="top">
    
    User-defined
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Adapter Type
    
    </td>
    <td valign="top">
    
    Type of adapter used for backend communication.
    
    </td>
    <td valign="top">
    
    HTTP
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="6">
    
    Connection
    
    </td>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Specifies the backend endpoint configuration type.
    
    </td>
    <td valign="top">
    
    API provider
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Destination
    
    </td>
    <td valign="top">
    
    The pre-configured API Provider destination used to reach the backend system.
    
    </td>
    <td valign="top">
    
    Destination name
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Defines how the backend is reached.
    
    </td>
    <td valign="top">
    
    The type of proxy that you are using to connect to the target system:

    -   Select *Internet* if you are connecting to a cloud system.

    -   Select *On-Premise* if you are connecting to an on-premise system.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Authentication mechanism used to invoke the backend service.
    
    </td>
    <td valign="top">
    
    Defines how the tenant \(as the HTTP client\) authenticates itself against the receiver.

    You can select one of the following authentication methods:

    -   Basic

        The tenant authenticates itself against the receiver using user credentials \(user name and password\).

    -   None

        When not to use any authentication can include, but not limited to, the following cases:

        -   If the target system that you want to communicate doesn't require any authentication.

        -   If you want to set an authorization header via a Content Modifier step before the adapter.

        -   If you want to set an authorization header via a Script step before the adapter.


    -   OAuth2 Client Credentials

        Use this grant type to access web resources by authorizing the client application to perform required actions on behalf of a user.


    Enabled only if you choose *Proxy Type* as *Internet*:

    -   Client Certificate

        The tenant authenticates itself against the receiver using a client certificate.

        It's a prerequisite that the required key pair is installed and added to a keystore. This keystore has to be deployed on the related tenant. The receiver side has to be configured appropriately.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    The endpoint URL resolved from the selected API Provider destination.
    
    </td>
    <td valign="top">
    
    Auto-populated from destination
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Timeout \(in ms\)
    
    </td>
    <td valign="top">
    
    Specifies the time \(in milliseconds\) that the client waits for a response before the connection is interrupted.

    The default value is 60000 milliseconds \(1 minute\).
    
    </td>
    <td valign="top">
    
    60000
    
    </td>
    </tr>
    </table>
    



