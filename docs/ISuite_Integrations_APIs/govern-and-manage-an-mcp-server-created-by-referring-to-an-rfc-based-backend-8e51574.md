<!-- loio8e51574c86354e938ef7cad09242ac1d -->

# Govern and Manage an MCP Server Created by Referring to an RFC-Based Backend

After creating an MCP server from an RFC-based backend, you can manage and govern it by configuring its source, tools, prompts, and policies.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

An MCP server created using an RFC-based backend is a versioned entity that you can manage independently within Integration Suite. While its structure is initially derived from selected RFC function modules, you can further refine and control it by:

-   Selecting and refining RFC functions and tools exposed to AI agents
-   Defining prompts to guide how agents interact with these tools
-   Applying policies to enforce security and traffic control

If the underlying RFC metadata changes, you can use the *Synchronize* option to update the MCP server without recreating it.



## Manage Source

In the *MCP Configuration* \> *Source* tab:

-   The *Source Type* is displayed as RFC.

-   The *Destination* shows the configured RFC destination \(backend system\).


This configuration defines the connection to the backend system from which RFC function modules are discovered.



## Define MCP Tools

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



## Configure Prompts

Prompts define how AI agents interact with MCP tools.

1.  Go to the *MCP Configuration* \> *Prompts* tab.
2.  Choose *Add*.
3.  In the *Create Prompt* wizard, provide a *Name*, *Title* and *Description* and choose *Next*.
4.  In *Add Arguments*, define the input parameters by specifying a name \(mandatory\), along with an optional title and description, and indicate whether the argument is required; you can add multiple arguments as needed.
5.  Then, in *Add Messages*, define the interaction flow by selecting a role—either *User* \(to represent input from the agent\) or *System* \(to provide instructions or context\)—and entering the corresponding content; additional messages can be added to structure the interaction.
6.  Choose *Create* to save the prompt, making it available for AI agents to use for consistent and structured interaction with MCP tools.



## Configure Policies

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

    > ### Note:  
    > Unlike MCP servers created from HTTP-based APIs, RFC-based MCP servers do not use API resources or HTTP operations. Instead, tools are directly derived from RFC function modules available in the connected backend system.


