<!-- loio8e51574c86354e938ef7cad09242ac1d -->

# Configure an MCP Server Created from an RFC-Based Backend

After creating an MCP server by referring to an RFC-based backend, you can customize its behavior, secure access, and define how AI agents interact with the exposed RFC function modules.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

An MCP server created using an RFC-based backend is a versioned entity that you can manage independently within Integration Suite. While its structure is initially derived from selected RFC function modules, you can further refine and control it by:

-   Selecting and refining RFC functions and tools exposed to AI agents
-   Defining prompts to guide how agents interact with these tools
-   Applying policies to enforce security and traffic control

> ### Note:  
> Unlike MCP servers created from HTTP-based APIs, RFC-based MCP servers do not use API resources or HTTP operations. Instead, tools are directly derived from RFC function modules available in the connected backend system.



## MCP Configuration

In the MCP Configuration tab, you can configure the core capabilities exposed by the MCP server. You can view the source and add or manage tools and prompts available to AI agents.



### Source

In the *MCP Configuration* \> *Source* tab:

-   The *Source Type* is displayed as RFC.

-   The *Destination* shows the configured RFC destination \(backend system\).


This configuration defines the connection to the backend system from which RFC function modules are discovered.



### Tools

After adding resources, you can expose specific RFC functions as MCP tools. These tools allow AI agents to interact with your MCP server in a structured and controlled way.

In the *MCP Configuration* \> *Tools* tab, you manage RFC-based tools.

1.  Choose *Add* to open the *Add Tools* dialog.
2.  Use the search field to find RFC function modules.

    You can search using keywords or naming patterns. For example, to find purchase order–related BAPIs, search for `BAPI_PO` To find user-related BAPIs, search for `BAPI_USER`. Use relevant prefixes or terms to quickly locate the required RFC function modules.

3.  Select one or more RFCs and choose *Add*.

Each selected RFC function module is exposed as an MCP tool that AI agents can invoke.

> ### Note:  
> You can add multiple RFCs, up to the allowed limit.
> 
> Only selected RFCs are exposed as tools, helping you control access to backend functionality.



### Prompts

Prompts define how AI agents interact with MCP tools.

1.  Go to the *MCP Configuration* \> *Prompts* tab.
2.  Choose *Add*.
3.  In the *Create Prompt* wizard, provide a *Name*, *Title* and *Description* and choose *Next*.
4.  In *Add Arguments*, define the input parameters by specifying a name \(mandatory\), along with an optional title and description, and indicate whether the argument is required; you can add multiple arguments as needed.
5.  Then, in *Add Messages*, define the interaction flow by selecting a role—either *User* \(to represent input from the agent\) or *System* \(to provide instructions or context\)—and entering the corresponding content; additional messages can be added to structure the interaction.
6.  Choose *Create* to save the prompt, making it available for AI agents to use for consistent and structured interaction with MCP tools.

    > ### Note:  
    > To define a prompt, you must define the prompt and messages. Defining arguments is optional.




## MCP Policy Configuration

Policies govern how tools are accessed and executed.

1.  Navigate to the *Policies* tab.
2.  Add and configure policies as needed. See, [Add Policies to Artifacts](add-policies-to-artifacts-c2b3e56.md) 

    > ### Note:  
    > The following policies are supported for MCP servers and can be configured under the *Policies* section:
    > 
    > -   Traffic Management: Quota, Surge Protection, and IP Filter
    > 
    > -   Security Policies: Authentication and Authorization
    > 
    > 
    > By default, All MCP tools are protected using an Authentication policy, ensuring that only authenticated AI agents can invoke RFC operations.
    > 
    > To protect backend systems and control usage, configure Surge Protection to limit request rates \(for example, a fixed number of calls per agent within a time interval\).

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

When you create an MCP server from an **RFC-based backend**, the MCP server includes an **MCP sender adapter**, which receives requests from AI agents, and an **RFC receiver adapter**, which forwards the requests to the configured RFC destination.

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
    
-   **RFC Receiver Adapter** – The RFC receiver adapter forwards requests from the MCP server to an SAP system through an RFC destination.

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
    <td valign="top">
    
    Connection
    
    </td>
    <td valign="top">
    
    Destination
    
    </td>
    <td valign="top">
    
    Specifies the RFC destination used by the receiver adapter to connect to the SAP backend system. The destination contains the connection details required to invoke RFC-enabled function modules
    
    </td>
    <td valign="top">
    
    API
    
    </td>
    </tr>
    </table>
    

