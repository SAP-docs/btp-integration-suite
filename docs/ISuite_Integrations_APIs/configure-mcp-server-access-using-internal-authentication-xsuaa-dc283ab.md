<!-- loiodc283ab437684345a5482b4f3d9651f2 -->

# Configure MCP Server Access Using Internal Authentication \(XSUAA\)

If the MCP server is secured using Internal Authentication, SAP BTP Authorization and Trust Management \(XSUAA\) manages user authentication. The AI application authenticates users against the identity provider configured for the subscriber subaccount.



## Prerequisites

Before configuring the AI application, ensure that the following prerequisites are met:

1.  Your user exists in the identity provider configured for the subscriber subaccount.

    The user account that you use to authenticate from the AI application must exist in the identity provider configured for the subscriber subaccount.

    -   **For Internal Authentication \(XSUAA\):** Verify that your user is available in the identity provider configured for the subscriber subaccount.

        > ### Note:  
        > If your user does not exist in the configured identity provider, authentication fails and the AI application cannot connect to the MCP server.


2.  If your tenant uses shadow users, enable **Create Shadow Users on User Login** so that users are automatically provisioned during their first sign-in.

    To enable shadow user creation:

    1.  In the SAP BTP cockpit, navigate to your **Global Account**.
    2.  Choose *Security* \> *Trust Configuration*.
    3.  Select the identity provider configured for the subscriber subaccount.
    4.  On the *Parameters* tab, select *Create Shadow Users on User Logon*.
    5.  Save your changes.

3.  If the MCP server's **Authorization** policy validates OAuth scopes, assign the required role \(for example, `API.invoke`\) to your user in the SAP BTP cockpit. See, [Assigning Role Collections to Users](assigning-role-collections-to-users-80bb02e.md).

    > ### Note:  
    > There is no default role collection available for the **API.invoke** role. Therefore, the tenant administrator must create a custom role collection that includes this role and make it available for assignment to IDP users in order to support the IDP user-based flow. For configuring custom role collection, see [Creating a Custom Role Collection for Fine-Grained Access Control](creating-a-custom-role-collection-for-fine-grained-access-control-4a26b60.md).

    > ### Note:  
    > When shadow users are used, individual role assignments are not available. In this case, scope-based authorization cannot be used for individual user access. Configure the Authorization policy to use **Developer Key** or **OAuth Scope OR Developer Key** instead. See, [Authorization](authorization-6658409.md) policy.




## Obtain OAuth Credentials Using a Developer Hub Agent Subscription

If the MCP server is published through Developer Hub, you can obtain OAuth client credentials by creating an Agent subscription. For more information, see [Subscribe to Products to Make MCP Servers Agent-Ready](subscribe-to-products-to-make-mcp-servers-agent-ready-2df6934.md).

1.  Subscribe to the MCP server as an agent.
2.  Add the redirect URI of your AI application to the subscription in the *Callback URL*.
3.  Create the subscription.

Developer Hub automatically generates the client ID and client secret required by the AI application.

For example, when using Claude Desktop, register the following redirect URI:

AI Application: `Claude Desktop`

Redirect URI: `https://claude.ai/api/mcp/auth_callback`



## Obtain OAuth Credentials Using a Process Integration Runtime Service Key

If you are connecting directly to the MCP server, generate OAuth credentials using a Process Integration Runtime service instance.

1.  Create a Process Integration Runtime service instance.
2.  Configure the OAuth grant type as **Authorization Code**.
3.  Register the redirect URI of your AI application.
4.  Generate a service key.

The generated service key contains the client ID, client secret, token endpoint, and other OAuth information required to configure the AI application. See, [Invoke an API or an MCP Server Artifact by Obtaining Credentials through Process Integration Runtime](invoke-an-api-or-an-mcp-server-artifact-by-obtaining-credentials-through-process-integrat-b63baa2.md).

