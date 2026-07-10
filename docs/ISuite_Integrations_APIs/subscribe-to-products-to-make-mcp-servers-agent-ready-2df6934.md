<!-- loio2df6934701604c02b6304e7a199a03c1 -->

# Subscribe to Products to Make MCP Servers Agent-Ready

To make your MCP server agent-ready, you need to create product subscriptions that allow agents to easily consume the MCP servers within those products.



<a name="loio2df6934701604c02b6304e7a199a03c1__prereq_zvd_yxk_ffc"/>

## Prerequisites

You should be onboarded as an application developer on Developer Hub. For more information, see [Onboarding an Application Developer](onboarding-an-application-developer-786d107.md).



## Context

MCP servers that are self-describing and follow clear conventions require less documentation, generate fewer support requests, and can be used more intuitively by developers—as well as by AI agents with minimal prompt engineering or fine-tuning.

Agent-ready MCP servers typically follow consistent patterns, such as RESTful conventions, well-defined schemas, and OpenAPI specifications. This consistency makes them easier to compose, enabling them to be compose-ready, documentation-ready, and governance-ready.

As you know, MCP server consumption typically involves bundling MCP servers into products and then subscribing to those products. To support agent-based consumption, you can extend this model by creating product subscriptions specifically tailored for agents.



## Procedure

1.  Log on to Developer Hub.

2.  To create a product subscription for agents, you can subscribe to the product using either of the following methods:

    -   Create a new subscription for agents from Developer Hub catalog:
        1.  Choose the product you want to subscribe to from the Developer Hub catalog.

        2.  Choose *Subscribe*, and then select *Create New Subscription for Agent* to proceed.

        3.  In the *Create Subscription for Agent* dialog, enter a title for the agent and, optionally, provide a short description and a detailed description.

            While creating the subscription, if you select the checkbox *Take me to this new application now*, you'll be directly navigated to the newly created subscription for the agent.

        4.  Choose *Create*.

            The product subscription for an agent gets created.


    -   Add to existing subscription for agents from Developer Hub catalog:

        In the *Add to ExistingSubscription for Agent* dialog box, select the application and choose *Add*.

        The product gets added to the application you selected.

    -   *My Workspace*:

    Alternatively, you can subscribe to a product from *My Workspace*:

    1.  Navigate to *My Workspace*.

    2.  To create a subscription, choose *Create* and select *Subscription for an Agent*.

    3.  In the *Create Subscription for an Agent* dialog, select one or more *MCP products* from the list and choose *Next*.

        > ### Note:  
        > When you select a product, the list is filtered to show only products that can be grouped within this application.

    4.  In *Subscription Details* dialog, enter a title for the agent and, optionally, provide a short description and a detailed description.

        > ### Note:  
        > If you select a product that includes MCP server with an authentication provider of type *External OAuth*, the *Client ID* field appears. You must provide the Client ID details in this field.

    5.  Choose *Next*.

    6.  Review the changes and choose *Save*.

        The product subscription for an agent gets created.

        > ### Note:  
        > If governance is set to *Manage Approval Outside Developer Hub* for a subscription, the subscription request must be approved by an external administrator before any actions can be performed on it. Once approved, an email notification with a link to the approved subscription will be sent. Only then can the MCP servers in the subscription can be accessed and consumed by the agent.

        The agents you created earlier, are displayed under the *Agents* tab.



