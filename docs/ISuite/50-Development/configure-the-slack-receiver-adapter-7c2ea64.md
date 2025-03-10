<!-- loio7c2ea64f931640afb01c6a9d82abdfa1 -->

# Configure the Slack Receiver Adapter

Enables SAP Integration Suite to get data from the Slack storage or to create, modify, or delete data on the Slack storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a receiver channel and selected the Slack receiver adapter, you can configure the following attributes.

Select the *General* tab to access the following parameters.

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name* 

</td>
<td valign="top">

Enter the name of the Slack channel.

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

Shows *Slack* as adapter type.

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol* 

</td>
<td valign="top">

Shows *HTTPS* as transport protocol.

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol* 

</td>
<td valign="top">

Shows *REST* as message protocol.

</td>
</tr>
</table>

You can provide more information in the *Description* field.

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Specifies the authorization option for the sender.

You can select one of the following options:

-   *Bot Token*

-   *Dynamic*

-   *User Token*




</td>
</tr>
<tr>
<td valign="top">

If *Bot Token* is selected for *Authentication* 

</td>
<td valign="top">

-   *Token Alias* :

    Name of the *Secure Parameter* artifact that contains the Slack token credentials.

    See: [Deploying a Secure Parameter Artifact](deploying-a-secure-parameter-artifact-4641d6c.md)

-   *Timeout \(in ms\)*:

    Specifies the maximum waiting time in milliseconds to contact the Slack server while establishing a connection; default value: `30000`.




</td>
</tr>
<tr>
<td valign="top">

If *Dynamic* is selected for *Authentication* 

</td>
<td valign="top">

-   *Bot Token Alias* :

    Name of the *Secure Parameter* artifact that contains the Slack bot token credentials.

    See: [Deploying a Secure Parameter Artifact](deploying-a-secure-parameter-artifact-4641d6c.md)

-   *User Token Alias* :

    Name of the *Secure Parameter* artifact that contains the Slack user token credentials.

-   *Timeout \(in ms\)*:

    Specifies the maximum waiting time in milliseconds to contact the Slack server while establishing a connection; default value: `30000`.


> ### Note:  
> The *Dynamic* authentication chooses the authentication type dynamically using the property `SAP_Slack_Outbound_AuthenticationType` with values `UserToken` or `BotToken` whose paramaters are `userAlias` and `botAlias` respectively.



</td>
</tr>
<tr>
<td valign="top">

If *User Token* is selected for *Authentication* 

</td>
<td valign="top">

-   *Token Alias* :

    Name of the credential artifact deployed on the tenant and used to connect to Dropbox account.

    See: [Deploying a Secure Parameter Artifact](deploying-a-secure-parameter-artifact-4641d6c.md)

-   *Timeout \(in ms\)*:

    Specifies the maximum waiting time in milliseconds to contact the Slack server while establishing a connection; default value: `30000`.




</td>
</tr>
</table>

There are 3 token types:

-   Granular Bots

-   User
-   Legacy Bots

To know more about the scope of these tokens and the API methods, see the table below

**API Methods**


<table>
<tr>
<th valign="top">

API Method

</th>
<th valign="top">

Description

</th>
<th valign="top">

Token

</th>
</tr>
<tr>
<td valign="top">

admin

</td>
<td valign="top">

Administer a workspace.

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.analytics:read

</td>
<td valign="top">

Access analytics data about the organization

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.apps:read

</td>
<td valign="top">

View apps and app requests in a workspace

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.apps:write

</td>
<td valign="top">

Manage apps in a workspace

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.barriers:read

</td>
<td valign="top">

Read information barriers in the organization

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.barriers:write

</td>
<td valign="top">

Manage information barriers in the organization

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.conversations:read

</td>
<td valign="top">

View the channel’s member list, topic, purpose and channel name

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.conversations:write

</td>
<td valign="top">

Start a new conversation, modify a conversation and modify channel details.

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.invites:read

</td>
<td valign="top">

Gain information about invite requests in a Grid organization.

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.invites:write

</td>
<td valign="top">

Approve or deny invite requests in a Grid organization.

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.teams:read

</td>
<td valign="top">

Access information about a workspace.

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.teams:write

</td>
<td valign="top">

Make changes to a workspace

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.usergroups:read

</td>
<td valign="top">

Access information about user groups

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.usergroups:write

</td>
<td valign="top">

Make changes to your usergroups

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.users:read

</td>
<td valign="top">

Access a workspace’s profile information

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

admin.users:write

</td>
<td valign="top">

Modify account information

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

app\_configurations:read

</td>
<td valign="top">

Read app configuration info via App Manifest APIs

</td>
<td valign="top">

app\_config

</td>
</tr>
<tr>
<td valign="top">

app\_configurations:write

</td>
<td valign="top">

Write app configuration info and create apps via App Manifest APIs

</td>
<td valign="top">

app\_config

</td>
</tr>
<tr>
<td valign="top">

app\_mentions:read

</td>
<td valign="top">

View messages that directly mention @your\_slack\_app in conversations that the app is in

</td>
<td valign="top">

Legacy bot Bot

</td>
</tr>
<tr>
<td valign="top">

auditlogs:read

</td>
<td valign="top">

View events from all workspaces, channels and users \(Enterprise Grid only\)

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

authorizations:read

</td>
<td valign="top">

Grants permission to list authorizations associated with the Events API

</td>
<td valign="top">

App level

</td>
</tr>
<tr>
<td valign="top">

bookmarks:read

</td>
<td valign="top">

List bookmarks

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

bookmarks:write

</td>
<td valign="top">

Create, edit, and remove bookmarks

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

bot

</td>
<td valign="top">

Add the ability for people to direct message or mention @your\_slack\_app

</td>
<td valign="top">

Legacy bot

</td>
</tr>
<tr>
<td valign="top">

calls:read

</td>
<td valign="top">

View information about ongoing and past calls

</td>
<td valign="top">

UserLegacy botBot

</td>
</tr>
<tr>
<td valign="top">

calls:write

</td>
<td valign="top">

Start and manage calls in a workspace

</td>
<td valign="top">

UserLegacy botBot

</td>
</tr>
<tr>
<td valign="top">

channels:history

</td>
<td valign="top">

View messages and other content in public channels to which your slack app has been added.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

channels:join

</td>
<td valign="top">

Join public channels in a workspace

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
<tr>
<td valign="top">

channels:manage

</td>
<td valign="top">

Manage public channels to which your slack app has been added and create new ones

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
<tr>
<td valign="top">

channels:read

</td>
<td valign="top">

View basic information about public channels in a workspace

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

channels:write

</td>
<td valign="top">

Manage a user’s public channels and create new ones on a user’s behalf

</td>
<td valign="top">

UserWorkspace

</td>
</tr>
<tr>
<td valign="top">

chat:write

</td>
<td valign="top">

Post messages in approved channels & conversations

</td>
<td valign="top">

UserBotWorkspace

</td>
</tr>
<tr>
<td valign="top">

chat:write.customize

</td>
<td valign="top">

Send messages as @your\_slack\_app with a customized username and avatar

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
<tr>
<td valign="top">

chat:write.public

</td>
<td valign="top">

Send messages to channels @your\_slack\_app

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
<tr>
<td valign="top">

chat:write:bot

</td>
<td valign="top">

Send messages as your slack app

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

chat:write:user

</td>
<td valign="top">

Send messages on a user’s behalf

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

commands

</td>
<td valign="top">

Add shortcuts and/or slash commands that people can use

</td>
<td valign="top">

UserBot

</td>
</tr>
<tr>
<td valign="top">

connections:write

</td>
<td valign="top">

Grants permission to generate websocket URIs and connect to Socket Mode

</td>
<td valign="top">

App level

</td>
</tr>
<tr>
<td valign="top">

conversations.connect:manage

</td>
<td valign="top">

Allows your slack app to manage Slack Connect channels

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
<tr>
<td valign="top">

conversations.connect:read

</td>
<td valign="top">

Receive Slack Connect invite events sent to the channels pertained to your slack app.

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
<tr>
<td valign="top">

conversations.connect:write

</td>
<td valign="top">

Create Slack Connect invitations for channels that your slack app has been added to, and accept invitations sent to your slack app

</td>
<td valign="top">

Legacy bot

</td>
</tr>
<tr>
<td valign="top">

dnd:read

</td>
<td valign="top">

View Do Not Disturb settings for people in a workspace

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

dnd:write

</td>
<td valign="top">

Edit a user’s Do Not Disturb settings

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

dnd:write:user

</td>
<td valign="top">

Change the user's Do Not Disturb settings

</td>
<td valign="top">

Workspace

</td>
</tr>
<tr>
<td valign="top">

email

</td>
<td valign="top">

View a user’s email address

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

emoji:read

</td>
<td valign="top">

View custom emoji in a workspace

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

files:read

</td>
<td valign="top">

View files shared in channels and conversations to which your slack app has been added.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

files:write

</td>
<td valign="top">

Upload, edit, and delete files as your slack app

</td>
<td valign="top">

UserWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

files:write:user

</td>
<td valign="top">

Upload, edit, and delete files as your slack app

</td>
<td valign="top">

UserLegacy bot

</td>
</tr>
<tr>
<td valign="top">

groups:history

</td>
<td valign="top">

View messages and other content in private channels that your slack app has been added to

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

groups:read

</td>
<td valign="top">

View basic information about private channels to which your slack app has been added.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

groups:write

</td>
<td valign="top">

Manage private channels that your slack app has been added to and create new ones

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

identify

</td>
<td valign="top">

View information about a user’s identity

</td>
<td valign="top">

legacy

</td>
</tr>
<tr>
<td valign="top">

identity.avatar

</td>
<td valign="top">

View a user’s Slack avatar

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

identity.avatar:read:user

</td>
<td valign="top">

View the user's profile picture

</td>
<td valign="top">

Workspace

</td>
</tr>
<tr>
<td valign="top">

identity.basic

</td>
<td valign="top">

View information about a user’s identity

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

identity.email

</td>
<td valign="top">

View a user’s email address

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

identity.email:read:user

</td>
<td valign="top">

 

</td>
<td valign="top">

Workspace

</td>
</tr>
<tr>
<td valign="top">

identity.team

</td>
<td valign="top">

View a user’s Slack workspace name

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

identity.team:read:user

</td>
<td valign="top">

View the workspace's name, domain, and icon

</td>
<td valign="top">

Workspace

</td>
</tr>
<tr>
<td valign="top">

identity:read:user

</td>
<td valign="top">

 

</td>
<td valign="top">

Workspace

</td>
</tr>
<tr>
<td valign="top">

im:history

</td>
<td valign="top">

View messages and other content in direct messages to which your slack app has been added.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

im:read

</td>
<td valign="top">

View basic information about direct messages to which your slack app has been added.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

im:write

</td>
<td valign="top">

Start direct messages with people

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

incoming-webhook

</td>
<td valign="top">

Create one-way webhooks to post messages to a specific channel

</td>
<td valign="top">

UserLegacy botBot

</td>
</tr>
<tr>
<td valign="top">

links:read

</td>
<td valign="top">

View URLs in messages

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

links:write

</td>
<td valign="top">

Show previews of URLs in messages

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

metadata.message:read

</td>
<td valign="top">

Allows your slack app to read message metadata in channels to which your slack app has been added.

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
<tr>
<td valign="top">

mpim:history

</td>
<td valign="top">

View messages and other content in group direct messages to which your slack app has been added.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

mpim:read

</td>
<td valign="top">

View basic information about group direct messages to which your slack app has been added.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

mpim:write

</td>
<td valign="top">

Start group direct messages with people

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

none

</td>
<td valign="top">

Execute methods without needing a scope

</td>
<td valign="top">

Legacy botWorkspace

</td>
</tr>
<tr>
<td valign="top">

openid

</td>
<td valign="top">

View information about a user’s identity

</td>
<td valign="top">

UserWorkspace

</td>
</tr>
<tr>
<td valign="top">

pins:read

</td>
<td valign="top">

View pinned content in channels and conversations to which your slack app has been added.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

pins:write

</td>
<td valign="top">

Add and remove pinned messages and files

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

profile

</td>
<td valign="top">

View a user’s Slack avatar and Slack workspace's basic information

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

reactions:read

</td>
<td valign="top">

View emoji reactions and their associated content in channels and conversations to which your slack app has been added.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

reactions:write

</td>
<td valign="top">

Add and edit emoji reactions

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

reminders:read

</td>
<td valign="top">

View reminders created by your slack app

</td>
<td valign="top">

UserLegacy botBot

</td>
</tr>
<tr>
<td valign="top">

reminders:read:user

</td>
<td valign="top">

Access reminders created by a user or for a user

</td>
<td valign="top">

Workspace

</td>
</tr>
<tr>
<td valign="top">

reminders:write

</td>
<td valign="top">

Add, remove, or mark reminders as complete

</td>
<td valign="top">

UserLegacy botBot

</td>
</tr>
<tr>
<td valign="top">

reminders:write:user

</td>
<td valign="top">

Add, remove, or complete reminders for the user

</td>
<td valign="top">

Workspace

</td>
</tr>
<tr>
<td valign="top">

remote\_files:read

</td>
<td valign="top">

View remote files added by the app in a workspace

</td>
<td valign="top">

UserLegacy botBot

</td>
</tr>
<tr>
<td valign="top">

remote\_files:share

</td>
<td valign="top">

Share remote files on a user’s behalf

</td>
<td valign="top">

UserLegacy botBot

</td>
</tr>
<tr>
<td valign="top">

remote\_files:write

</td>
<td valign="top">

Add, edit, and delete remote files on a user’s behalf

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
<tr>
<td valign="top">

search:read

</td>
<td valign="top">

Search a workspace’s content

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

stars:read

</td>
<td valign="top">

View messages and files that your slack app has starred

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

stars:write

</td>
<td valign="top">

Add or remove stars

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

team.billing:read

</td>
<td valign="top">

Allows your slack app to read the billing plan for workspaces in which your slack app has been installed.

</td>
<td valign="top">

User

Legacy bot

Bot

</td>
</tr>
<tr>
<td valign="top">

team.preferences:read

</td>
<td valign="top">

Allows your slack app to read the preferences for workspaces in which your slack app has been installed.

</td>
<td valign="top">

UserLegacy botBot

</td>
</tr>
<tr>
<td valign="top">

team:read

</td>
<td valign="top">

View the name, email domain, and icon for workspaces to which your slack app is connected.

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

tokens.basic

</td>
<td valign="top">

Execute methods without needing a scope

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

triggers:write

</td>
<td valign="top">

Create new Platform triggers

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
<tr>
<td valign="top">

usergroups:read

</td>
<td valign="top">

View user groups in a workspace

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

usergroups:write

</td>
<td valign="top">

Create and manage user groups

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

users.profile:read

</td>
<td valign="top">

View profile details about people in a workspace

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

users.profile:write

</td>
<td valign="top">

Edit a user’s profile information and status

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

users.profile:write:user

</td>
<td valign="top">

Change the user's profile fields

</td>
<td valign="top">

Workspace

</td>
</tr>
<tr>
<td valign="top">

users:read

</td>
<td valign="top">

View people in a workspace

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

users:read.email

</td>
<td valign="top">

View email addresses of people in a workspace

</td>
<td valign="top">

UserLegacy botWorkspaceBot

</td>
</tr>
<tr>
<td valign="top">

users:write

</td>
<td valign="top">

Set presence for your slack app

</td>
<td valign="top">

UserLegacy botBot

</td>
</tr>
<tr>
<td valign="top">

workflow.steps:execute

</td>
<td valign="top">

Add steps that people can use in Workflow Builder

</td>
<td valign="top">

Legacy botBot

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Processing Details**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Method Group* 

</td>
<td valign="top">

Specify the API method group.

The supported API method groups are:

-   Admin

-   Api
-   Apps
-   Auth
-   Bots
-   Calls
-   Chat
-   Conversations
-   Dialog
-   DND
-   Emoji
-   Files
-   Openid
-   Pins
-   Reactions
-   Reminders
-   RTM
-   Search
-   Stars
-   Teams
-   Usergroups
-   Users
-   Views
-   Workflows



</td>
</tr>
<tr>
<td valign="top">

*Method* 

</td>
<td valign="top">

Specify the API Method for Method Group.

> ### Note:  
> Different fields appear depending on the type of method you chose. Maintain those relevant fields.
> 
> To know more about the paramaters and the values, see [List of Method Groups](list-of-method-groups-95929c6.md)



</td>
</tr>
<tr>
<td valign="top">

*Arguments* 

</td>
<td valign="top">

Choose *Add* and maintain the values of the *Key* and *Value* fields.

</td>
</tr>
<tr>
<td valign="top">

*Key* 

</td>
<td valign="top">

Select the name of property. You can also enter `${header.headername}` or `${property.propertyname}` to dynamically ready the value from a header or property.

The supported Keys are mentioned in the table below.

</td>
</tr>
<tr>
<td valign="top">

*Value* 

</td>
<td valign="top">

Specify the value of the property.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Response Format*

</td>
<td valign="top">

You can set one of the following 3 response formats:

-   *JSON*: Response displayed in JSON format.

-   *XML*: Response displayed in XML format \(converted to XML by the adapter\).

-   *Dynamic*: Response displayed in both JSON and XML.


> ### Note:  
> Creation of route in JSON will fail if it encounters `" : "` in the sample.
> 
> > ### Sample Code:  
> > ```
> > {"frequency": "weekly", "weekdays": ["monday", "wednesday", "friday"] }
> > ```



</td>
</tr>
<tr>
<td valign="top">

*Request Header*

</td>
<td valign="top">

Pipe separated value list of HTTP request headers. The specified headers to be sent from the Slack backend.

</td>
</tr>
</table>

**Supported Keys**


<table>
<tr>
<th valign="top">

Sl.No

</th>
<th valign="top">

Key

</th>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

app\_id

</td>
</tr>
<tr>
<td valign="top">

2

</td>
<td valign="top">

as\_user

</td>
</tr>
<tr>
<td valign="top">

3

</td>
<td valign="top">

attachments

</td>
</tr>
<tr>
<td valign="top">

4

</td>
<td valign="top">

auto\_provision

</td>
</tr>
<tr>
<td valign="top">

5

</td>
<td valign="top">

bot

</td>
</tr>
<tr>
<td valign="top">

6

</td>
<td valign="top">

channel

</td>
</tr>
<tr>
<td valign="top">

7

</td>
<td valign="top">

channel\_ids

</td>
</tr>
<tr>
<td valign="top">

8

</td>
<td valign="top">

code

</td>
</tr>
<tr>
<td valign="top">

9

</td>
<td valign="top">

created\_by

</td>
</tr>
<tr>
<td valign="top">

10

</td>
<td valign="top">

cursor

</td>
</tr>
<tr>
<td valign="top">

11

</td>
<td valign="top">

custom\_message

</td>
</tr>
<tr>
<td valign="top">

12

</td>
<td valign="top">

date

</td>
</tr>
<tr>
<td valign="top">

13

</td>
<td valign="top">

description

</td>
</tr>
<tr>
<td valign="top">

14

</td>
<td valign="top">

emoji

</td>
</tr>
<tr>
<td valign="top">

15

</td>
<td valign="top">

enterprise\_id

</td>
</tr>
<tr>
<td valign="top">

16

</td>
<td valign="top">

entity\_type

</td>
</tr>
<tr>
<td valign="top">

17

</td>
<td valign="top">

error

</td>
</tr>
<tr>
<td valign="top">

18

</td>
<td valign="top">

grant\_type

</td>
</tr>
<tr>
<td valign="top">

19

</td>
<td valign="top">

hash

</td>
</tr>
<tr>
<td valign="top">

20

</td>
<td valign="top">

icon\_emoji

</td>
</tr>
<tr>
<td valign="top">

21

</td>
<td valign="top">

icon\_url

</td>
</tr>
<tr>
<td valign="top">

22

</td>
<td valign="top">

include\_count

</td>
</tr>
<tr>
<td valign="top">

23

</td>
<td valign="top">

latest

</td>
</tr>
<tr>
<td valign="top">

24

</td>
<td valign="top">

leaving\_team\_ids

</td>
</tr>
<tr>
<td valign="top">

25

</td>
<td valign="top">

limit

</td>
</tr>
<tr>
<td valign="top">

26

</td>
<td valign="top">

name

</td>
</tr>
<tr>
<td valign="top">

27

</td>
<td valign="top">

num\_minutes

</td>
</tr>
<tr>
<td valign="top">

28

</td>
<td valign="top">

oldest

</td>
</tr>
<tr>
<td valign="top">

29

</td>
<td valign="top">

org\_channel

</td>
</tr>
<tr>
<td valign="top">

30

</td>
<td valign="top">

parent\_id

</td>
</tr>
<tr>
<td valign="top">

31

</td>
<td valign="top">

query

</td>
</tr>
<tr>
<td valign="top">

32

</td>
<td valign="top">

request\_id

</td>
</tr>
<tr>
<td valign="top">

33

</td>
<td valign="top">

resend

</td>
</tr>
<tr>
<td valign="top">

34

</td>
<td valign="top">

search\_channel\_types

</td>
</tr>
<tr>
<td valign="top">

35

</td>
<td valign="top">

sort

</td>
</tr>
<tr>
<td valign="top">

36

</td>
<td valign="top">

team\_description

</td>
</tr>
<tr>
<td valign="top">

37

</td>
<td valign="top">

team\_id

</td>
</tr>
<tr>
<td valign="top">

38

</td>
<td valign="top">

timestamp

</td>
</tr>
<tr>
<td valign="top">

39

</td>
<td valign="top">

title

</td>
</tr>
<tr>
<td valign="top">

40

</td>
<td valign="top">

users

</td>
</tr>
<tr>
<td valign="top">

41

</td>
<td valign="top">

visibility

</td>
</tr>
</table>

Various operations, their APIs and pagination types have been tabulated below.

**Pagination Support**


<table>
<tr>
<th valign="top">

Operation

</th>
<th valign="top">

API

</th>
<th valign="top">

Pagination Type

</th>
</tr>
<tr>
<td valign="top">

conversations.history

</td>
<td valign="top">

https://slack.com/api/conversations.history

</td>
<td valign="top">

Cursor

</td>
</tr>
<tr>
<td valign="top">

conversations.list

</td>
<td valign="top">

https://slack.com/api/conversations.list

</td>
<td valign="top">

Cursor

</td>
</tr>
<tr>
<td valign="top">

conversations.members

</td>
<td valign="top">

https://slack.com/api/conversations.members

</td>
<td valign="top">

Cursor

</td>
</tr>
<tr>
<td valign="top">

conversations.replies

</td>
<td valign="top">

https://slack.com/api/conversations.replies

</td>
<td valign="top">

Cursor

</td>
</tr>
<tr>
<td valign="top">

files.info

</td>
<td valign="top">

https://slack.com/api/files.info

</td>
<td valign="top">

Cursor

</td>
</tr>
<tr>
<td valign="top">

reactions.list

</td>
<td valign="top">

https://slack.com/api/reactions.list

</td>
<td valign="top">

Cursor

</td>
</tr>
<tr>
<td valign="top">

stars.list

</td>
<td valign="top">

https://slack.com/api/stars.list

</td>
<td valign="top">

Cursor

</td>
</tr>
<tr>
<td valign="top">

users.list

</td>
<td valign="top">

https://slack.com/api/users.list

</td>
<td valign="top">

Cursor

</td>
</tr>
<tr>
<td valign="top">

files.list

</td>
<td valign="top">

https://api.slack.com/methods/files.list

</td>
<td valign="top">

Traditional

</td>
</tr>
<tr>
<td valign="top">

search.all

</td>
<td valign="top">

https://api.slack.com/methods/search.all

</td>
<td valign="top">

Traditional

</td>
</tr>
<tr>
<td valign="top">

search.files

</td>
<td valign="top">

https://slack.com/api/search.files

</td>
<td valign="top">

Traditional

</td>
</tr>
<tr>
<td valign="top">

search.messages

</td>
<td valign="top">

https://api.slack.com/methods/search.messages

</td>
<td valign="top">

Traditional

</td>
</tr>
</table>



<a name="loio7c2ea64f931640afb01c6a9d82abdfa1__section_xqq_rvp_z5b"/>

## Pagination

Slack Adapter supports Cursor based pagination as well as traditional pagination.

*Cursor based Pagination*

`cursor` \(`next_cursor` in response\) & `limit` are the parameters for Cursor based pagination. Pagination support will be done using the Looping Subprocess call. In this type, `limit` is a mandatory parameter referring to a pointer and `cursor` is an optional parameter referring to a page count, and the integration developer needs to maintain these parameters in the arguments.

*Traditional Pagination*

`Page_Count` in response is the parameter for traditional pagination. Pagination support will be done using the Looping Subprocess call. `Count` and `Page` are the optional parameters using which the adapter can bring records. By default, Slack paginates the response with 20 records if optional parameters are not provided.



### Behaviour of the adapter within the Looping Subprocess call

The Slack adapter check for the Exchange property `SAP_Slack_hasMoreRecords=false` and if it is null, defaults it to `hasMoreRecords=true` to initiate the looping process call. The Looping Process call in the integration flow should have set its condition as `SAP_Slack_hasMoreRecords!=false` to break out of the loop. As the exchange property `SAP_Slack_hasMoreRecords` is defaulted to true initially, the adapter will work to modify this property based on the `cursor` data for cursor based pagination and on `page count` for traditional pagination. When `cursor` \(`next_cursor` in response\) is blank or null for cursor based pagination and when `page count` reaches the last page for traditional pagination, the adapter will set the `SAP_Slack_hasMoreRecords=false`.

