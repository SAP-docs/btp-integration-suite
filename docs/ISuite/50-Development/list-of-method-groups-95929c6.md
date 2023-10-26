<!-- loio95929c6bf22349aaa74044c54ef4ce69 -->

# List of Method Groups

Get to know the list of method groups and their respective methods for the Slack receiver adapter.

There are 24 method groups with each containing many methods. Depending on the method group you choose, the respective methods and their parameters get displayed in the *Processing* step of your Slack receiver.

> ### Note:  
> Do not use *&* symbol in any of the input field as this will cause creation of route failure.

**API Method Groups**


<table>
<tr>
<th valign="top">

Method Group

</th>
<th valign="top">

Method

</th>
<th valign="top">

Parameters

</th>
</tr>
<tr>
<td valign="top">

Admin Method Group

</td>
<td valign="top">

*admin.analytics.getFile*

You can get analytics data for a given date, presented as a compressed JSON file.

</td>
<td valign="top">

*Type*: Specify the type for analytics to retrieve.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *admin.apps.approve* 

    You can approve an app for installation on a workspace.

-   *admin.apps.approved.list*

    You can list approved apps for an organization or workspace.

-   *admin.apps.requests.list*

    You can list restricted apps for an org or workspace.

-   *admin.apps.restrict*

    You can restrict an app for installation on a workspace.

-   *admin.apps.restricted.list*

    You can list app requests for a workspace.




</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.apps.clearResolution*

You can clear an app resolution by providing App ID.

</td>
<td valign="top">

*App ID*: Specify the ID of the application whose resolution you want to clear or undo.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.apps.requests.cancel*

You can cancel restricted Apps for an org or workspace.

</td>
<td valign="top">

*Request ID*: Specify the ID of the request to cancel.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.apps.uninstall*

You can uninstall an app from one or many workspaces, or an entire enterprise organization by providing App ID.

</td>
<td valign="top">

*App ID*: Specify the ID of the application that you want to uninstall.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.auth.policy.assignEntities*

You can assign entities to a particular authentication policy by providing the Entry IDs, Entity Type and Policy Name.

</td>
<td valign="top">

-   *Entry IDs*: Specify the array of IDs to assign to the policy.

-   *Entry Type*: Specify the type of entity of the authentication policy.
-   *Policy Name*: Specify your email ID for the name of the authentication policy.

    > ### Note:  
    > Only email password policy can be used with this method.




</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.auth.policy.getEntities*

You can fetch all the entities assigned to a particular authentication policy by providing policy name.

</td>
<td valign="top">

*Policy Name*: Specify your email ID for the name of the authentication policy.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.auth.policy.removeEntities*

You can remove specified entities from a specified authentication policy.

</td>
<td valign="top">

-   *Entry IDs*: Specify the array of IDs of the authentication policy.

-   *Entry Type*: Specify the type of entity of the authentication policy.
-   *Policy Name*: Specify your email ID for name of the authentication policy.

    > ### Note:  
    > Only email password policy can be used with this method.




</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.barriers.create*

You can create an Information Barrier.

</td>
<td valign="top">

-   *Barriered from Usergroup IDs*: Specify the list of IDP Groups IDs that the primary usergroup is to be barriered from.

-   *Primary Usergroup ID*: Specify the ID of the primary IDP Group.
-   *Restricted Subjects*: Specify the interactions that are blocked by this barrier. The supported interactions are:
    -   eg im

    -   mpim
    -   call




</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.barriers.delete* 

You can delete an Information Barrier by providing the already created Barrier ID.

</td>
<td valign="top">

*Barrier ID*: Specify the ID of the barrier you're trying to delete

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.barriers.list* 

You can get list of all Information Barriers for your organization.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.barriers.update*

You can update an existing Information Barrier.

</td>
<td valign="top">

-   *Barriered from Usergroup IDs*: Specify the list of IDP Groups IDs that the primary usergroup is to be barriered from.

-   *Primary Usergroup ID*: Specify the ID of the primary IDP Group.
-   *Restricted Subjects*: Specify the interactions that are blocked by this barrier.
-   *Barrier ID*: Specify the ID of the barrier.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *admin.conversations.archive* You can archive a public or private channel by providing Channel ID.

-   *admin.conversations.convertToPrivate* You can convert a public channel into a private channel by providing the Channel ID.
-   *admin.conversations.delete* You can delete a public channel or a private channel.
-   *admin.conversations.disconnectShared* You can disconnect a connected channel from one or more workspaces
-   *admin.conversations.getConversationPrefs* You can get conversation preferences for a public or private channel.
-   *admin.conversations.getCustomRetention* This API endpoint can be used by any admin to get a channel's retention policy.
-   *admin.conversations.getTeams* You can get all the workspaces to which a given public or private channel is connected within this Enterprise org.
-   *admin.conversations.removeCustomRetention* This API endpoint can be used by any admin to remove a channel's retention policy.
-   *admin.conversations.restrictAccess.listGroups*
-   *admin.conversations.setTeams* You can set the workspaces in an Enterprise grid org that connect to a public or private channel.
-   *admin.conversations.unarchive* This API endpoint can be used to unarchive a public or private channel.



</td>
<td valign="top">

*Channel ID*: Specify the ID of the channel

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.conversations.create*

You can create a private channel or a public channel.

</td>
<td valign="top">

-   *Is Private*: When true, a private channel is created instead of a public channel.

-   *Name*: Specify the name of the public or the private channel.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.conversations.invite* You can invite new users to a channel by this API endpoint.

</td>
<td valign="top">

-   *User IDs*: Specify the IDs to invite the users.

-   *Channel ID*: Specify the ID of the channel



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.conversations.rename* This API endpoint can be used by any admin to rename a channel's retention policy.

</td>
<td valign="top">

-   *Name*: Specify the name of the public or the private channel.

-   *Channel ID*: Specify the ID of the channel



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *admin.conversations.ekm.listOriginalConnectedChannelInfo*

    You can get list of all disconnected channels which were once connected to other workspaces and then disconnected, and the corresponding original channel IDs for key revocation with EKM.

-   *admin.conversations.search* You can search for public or private channels in an Enterprise organization



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.conversations.restrictAccess.addGroup* You can add an allowlist of IDP groups for accessing a channel

</td>
<td valign="top">

-   *Channel ID*: Specify the ID of the channel
-   *Group ID*: Specify the IDP Group ID to be an allowlist for the private channel.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.conversations.restrictAccess.removeGroup* You can remove a linked IDP group linked from a private channel.

</td>
<td valign="top">

-   *Channel ID*: Specify the ID of the channel
-   *Group ID*: Specify the IDP Group ID to be an allowlist for the private channel.
-   *Team ID*: Specify the ID of the workspace where the channel exists.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.conversations.setConversationPrefs* You can set the posting permissions for a public or private channel.

</td>
<td valign="top">

-   *Prefs*: Specify the preferences for this channel in a stringified JSON format.

-   *Channel ID*: Specify the ID of the channel



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.conversations.setCustomRetention* This API endpoint can be used by any admin to set a channel's retention policy.

</td>
<td valign="top">

-   *Duration Days*: Specify the message retention duration in days to set for this channel.

-   *Channel ID*: Specify the ID of the channel



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.emoji.add* This API endpoint is to add an emoji.

</td>
<td valign="top">

-   *Name*: Specify the name of the public or the private channel.

-   *URL*: Specify the URL of a file to use as an image for the emoji. Square images under 128KB and with transparent backgrounds work best.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.emoji.addAlias* This API endpoint is to add an emoji Alias.

</td>
<td valign="top">

-   *Name*: Specify the name of the public or the private channel.

-   *Alias for*: Specify the alias for the emoji.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *admin.emoji.list* This API endpoint is to list emoji for an Enterprise Grid organization.

-   *admin.inviteRequests.approved.list* This API endpoint is to list all approved workspace invite requests.
-   *admin.inviteRequests.denied.list* This API endpoint is to list all denied workspace invite requests.
-   *admin.inviteRequests.list* This API endpoint is to list all pending workspace invite requests.
-   *admin.teams.list* You can list all teams on an enterprise organization.
-   *admin.users.list* You can list user on a workspace.
-   *admin.users.session.list* You can list active user sessions for an organization.



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.emoji.remove* This API endpoint is to remove an emoji across an Enterprise Grid organization.

</td>
<td valign="top">

*Name*: Specify the name of the public or the private channel.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.emoji.rename* This API endpoint is to rename an emoji.

</td>
<td valign="top">

-   *Name*: Specify the name of the public or the private channel.

-   *New Name*: Specify the new name for the emoji.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *admin.inviteRequests.approve* This API endpoint is to approve a workspace invite request.

-   *admin.inviteRequests.deny* This API endpoint is to deny a workspace invite request.



</td>
<td valign="top">

*Invite Request ID*: Specify the ID of the request.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *admin.teams.admins.list* You can list all the admins on a given workspace by providing Team ID.

-   *admin.teams.owners.list* You can list all owners in a given workspace by providing Team ID.
-   *admin.teams.settings.info* You can access information about settings in a workspace.



</td>
<td valign="top">

*Team ID*: Specify the ID of the workspace.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.teams.create* You can create an enterprise team.

</td>
<td valign="top">

-   *Team Domain*: Specify the team domain. Domains are limited to 21 characters.

-   *Team Name*: Specify the team name.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.teams.settings.setDefaultChannels* You can set the default channels of a workspace in settings.

</td>
<td valign="top">

-   *Team ID*: Specify the ID of the workspace.

-   *Channel IDs*: Specify the ID of the channels.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.teams.settings.setDescription* You can set the description of a given workspace in settings.

</td>
<td valign="top">

-   *Team ID*: Specify the ID of the workspace.

-   *Description*: Specify the description.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.teams.settings.setDiscoverability* You can set the discoverability of a given workspace in settings.

</td>
<td valign="top">

-   *Team ID*: Specify the ID of the workspace.

-   *Discoverability*:Specify the discoverability for workspace's discovery setting.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.teams.settings.setIcon* You can set the icon of a given workspace in settings by providing Team ID and image URL.

</td>
<td valign="top">

-   *Team ID*: Specify the ID of the workspace.

-   *Image URL*: Specify the URL of the icon.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.teams.settings.setName* You can set the name of a given workspace in settings by providing Name and Team ID.

</td>
<td valign="top">

-   *Name*: Specify the name of the public or the private channel.
-   *Team ID*: Specify the ID of the workspace.




</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *admin.usergroups.addChannels* You can add up to one hundred default channels to an IDP group by providing Channel ID and User Group ID.

-   *admin.usergroups.removeChannels* You can remove one or more default channels from an org-level IDP group \(user group\).



</td>
<td valign="top">

-   *Channel IDs*: Specify the array of channel IDs
-   *User Group ID*: Specify the ID of the IDP group to add default channels for.




</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.usergroups.addTeams* You can associate one or more default workspaces with an organization-wide IDP group by providing below-mentioned parameters.

</td>
<td valign="top">

-   *User Group ID*: Specify the ID of the IDP group to add default workspaces for.

-   *Team IDs*: Specify the comma separated list of encoded team \(workspace\) IDs. Each workspace must belong to the organization associated with the token.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.usergroups.listChannels* You can list the channels linked to an org-level IDP group \(user group\).

</td>
<td valign="top">

*User Group ID*: Specify the ID of the IDP group to add default workspaces for.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *admin.users.assign* You can add an enterprise user to a workspace.

-   *admin.users.remove* If you want to remove a user from a workspace, you need to provide Team ID and User ID of that respective user.
-   *admin.users.setAdmin* For setting an admin user, you can add an existing guest, regular user, or owner.
-   *admin.users.setOwner* You can set a workspace owner by adding an existing guest, regular user, or admin user.
-   *admin.users.setRegular* You can set a regular user by adding an existing guest user, admin user, or owner.



</td>
<td valign="top">

-   *Team ID*: Specify the ID of the workspace where the channel exists.

-   *User ID*: Specify the ID of the user.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.users.invite* You can invite a user to a workspace by providing Team ID, Channel IDs and Email.

</td>
<td valign="top">

-   *Team ID*: Specify the ID of the workspace where the channel exists.

-   *Channel IDs*: Specify the array of channel IDs
-   *Email*: Specify the email address of the person to invite.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *admin.users.session.clearSettings* You can clear user-specific session settings. In this, you can clear session duration and actions for a list of users.

-   *admin.users.session.getSettings* You can get user-specific session settings. In this, you can get session duration and actions for a list of users.
-   *admin.users.session.setSettings* You can configure the user-level session settings. In this, you can configure session duration and actions for a list of users.



</td>
<td valign="top">

*User IDs*: Specify the ID of the users.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.users.session.invalidate* You can revoke a single session for a user. Then, the user will be forced to login to Slack.users.

</td>
<td valign="top">

-   *Team ID*: Specify the ID of the workspace where the channel exists.

-   *Session ID*: Specify the ID of the session to invalidate.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.users.session.reset* You can reset valid sessions on all devices for a given user by providing respective User ID.

</td>
<td valign="top">

*User ID*: Specify the ID of the user to wipe sessions for.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*admin.users.setExpiration* You can set an expiration for a guest user using User ID and Timestamp of expiration.

</td>
<td valign="top">

-   *User ID*: Specify the ID of the user.

-   *Expiration ts*: Specify the timestamp when guest account should be disabled.



</td>
</tr>
<tr>
<td valign="top">

API Method Group

</td>
<td valign="top">

*api.test* You can test API.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Apps Method Group

</td>
<td valign="top">

*apps.connections.open* With this API endpoint, you can generate a temporary Socket Mode WebSocket URL that your app can connect to in order to receive events and interactive payloads over.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*apps.event.authorizations.list* You can get a list of authorizations for the given event context. Each authorization represents an app installation that the event is visible to.

</td>
<td valign="top">

*Event Context*: Specify the event context.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *apps.manifest.create* You can create an app from an app manifest.

-   *apps.manifest.validate* By this API endpoint, you can update an app manifest from an existing app.



</td>
<td valign="top">

*Manifest*: Specify the JSON app manifest encoded as a string. This manifest must use a valid app manifest.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *apps.manifest.delete* By this API endpoint, you can permanently delete an app created through app manifest.

-   *apps.manifest.export* By this API endpoint, you can export an app manifest from an existing app.



</td>
<td valign="top">

*App ID* : Specify the ID of the app.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*apps.manifest.update* By this API endpoint, you can update an app manifest from an existing app.

</td>
<td valign="top">

-   *Manifest*: Specify the JSON app manifest encoded as a string. This manifest must use a valid app manifest.

-   *App ID* : Specify the ID of the app.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*apps.uninstall* By this API endpoint, you can uninstall your app from workspace.

</td>
<td valign="top">

-   *Client ID*: Specify client ID issued when you created your application.

-   *Client Secret*: Specify the client secret issued when you created your application.



</td>
</tr>
<tr>
<td valign="top">

Auth Method Group

</td>
<td valign="top">

-   *auth.revoke* By this API endpoint, you can revoke a Token.

-   *auth.teams.list* By this API endpoint, you can list the workspaces a token can access.
-   *auth.test* By this API endpoint, you can check Authentication & Identity.



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Bots Method Group

</td>
<td valign="top">

*bots.info* By this API endpoint, you can access information about a bot user.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Calls Method Group

</td>
<td valign="top">

*calls.add* By this API endpoint, you can add a new Call.

</td>
<td valign="top">

-   *External Unique ID*: Specify the ID supplied by the 3rd-party Call provider.

-   *Join URL*: Specify the URL required for a client to join the Call.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *calls.end* By this API endpoint, you can end a Call

-   *calls.info* This API endpoint helps return information about a Call
-   *calls.update* This API endpoint helps update information about a Call.



</td>
<td valign="top">

*ID*: Specify the ID which is returned when registering the call using the calls.add method.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *calls.participants.add* This API endpoint helps add new participants to a Call.

-   *calls.participants.remove* This API endpoint helps remove new participants to a Call.



</td>
<td valign="top">

-   *ID*: Specify the ID which is returned when registering the call using the calls.add method.

-   *Users*: Specify the list of users to add as participants in the Call.



</td>
</tr>
<tr>
<td valign="top">

Chat Method Group

</td>
<td valign="top">

-   *chat.delete* This API endpoint deletes a message in a channel.

-   *chat.update* You can update a posted message in channel.

    > ### Note:  
    > This method updates a message in a channel. Though related to chat.postMessage, some parameters of chat.update are handled differently. Ephemeral messages created by chat.postEphemeral or otherwise cannot be updated with this method.




</td>
<td valign="top">

-   *Channel*: Specify the channel ID.

-   *ts*: Specify the timestamp of the message to be deleted



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*chat.deleteScheduledMessage* This API endpoint deletes a pending scheduled message from the queue.

</td>
<td valign="top">

-   *Channel*: Specify the channel ID.

-   *Scheduled Message ID*: Specify the ID returned from call to chat.scheduleMessage.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*chat.getPermalink* This API endpoint retrieves a permalink URL for a specific extant message.

</td>
<td valign="top">

-   *Channel*: Specify the channel ID.

-   *Message ts*: Specify the message's timestamp value, uniquely identifying it within a channel.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *chat.meMessage* This API endpoint shares a me message into a channel.

-   *chat.postMessage* This API endpoint sends a message to a channel.



</td>
<td valign="top">

-   *Channel*: Specify the channel ID.

-   *Text*: Enter the message to be sent.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*chat.postEphemeral* This API endpoint sends an ephemeral message to a user in a channel.

</td>
<td valign="top">

-   *Channel*: Specify the channel ID.

-   *Text*: Enter the message to be sent.
-   *User*: Specify the ID of the user who will receive the ephemeral message. The user should be in the channel specified by the channel argument.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*chat.scheduledMessages.list* You can get a list of scheduled messages in chat.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*chat.scheduleMessage* You can schedule a message to be sent to a channel.

</td>
<td valign="top">

-   *Channel*: Specify the channel ID.

-   *Text*: Enter the message to be sent.
-   *Post At*: Specify the unix EPOCH timestamp of time in future to send the message.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*chat.unfurl*You can provide custom unfurl behavior for user-posted URL.

</td>
<td valign="top">

-   *Channel*: Specify the channel ID.

-   *ts*: Specify the timestamp of the message
-   *Unfurls*: Specify the URL-encoded JSON map with keys set to URLs featured in the message, pointing to their unfurl blocks or message attachments.

> ### Note:  
> Both channel and ts must be provided together or unfurl\_id and source must be provided together.
> 
> This method unfurls a link—either in the message composer or in a posted message. This method supports both granular bot and user tokens. The bot token is recommended



</td>
</tr>
<tr>
<td valign="top">

Conversations Method Group

</td>
<td valign="top">

*conversations.acceptSharedInvite* This API endpoint accept an invitation to a Slack Connect channel.

</td>
<td valign="top">

*Channel Name*: Specify the name of the channel.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *conversations.approveSharedInvite* This API endpoint accept an invitation to a Slack Connect channel. While any user may accept an invitation to a Slack Connect channel, many workspaces then require Slack Connect channels to be approved by an Admin or user with elevated permissions.

-   *conversations.declineSharedInvite* This API endpoint declines a Slack Connect channel invite.



</td>
<td valign="top">

*Invite ID*: Specify the ID of the Slack Connect invite.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *conversations.archive* This method archives a conversation.

-   *conversations.close* You can close a direct message or multi-person direct message.
-   *conversations.history* This API endpoint returns history of messages in the thread.
-   *conversations.info* This conversations API method retrieves information about a conversation.

    This method returns a conversation object, which could be a public channel, private channel, direct message, multi-person direct message, depending completely on the channel ID and the permissions granted to your token.

-   *conversations.inviteShared* This conversations API method sends an invitation to a Slack Connect channel.
-   *conversations.join* This conversations API method joins an existing conversation.
-   *conversations.leave* This conversations API method leaves a conversation.
-   *conversations.members* This conversations API method helps retrieve members of a conversation.
-   *conversations.unarchive* This method unarchives a conversation. The calling user is added to the conversation



</td>
<td valign="top">

*Channel*: Specify the ID of the channel.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*conversations.create* You can initiate a public or private channel-based conversation.

</td>
<td valign="top">

*Name*: Specify the name of the public or the private channel.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*conversations.invite* This Conversations API method invites 1-1000 users to a public or private channel.

This Conversations API method's required scopes depend on the type of channel-like object you are working with. To use the method, you will need at least one of the channels:, groups:, im: or mpim: scopes corresponding to the conversation type you're working with.

</td>
<td valign="top">

-   *Users*: Specify the list of users to invite in conversation.
-   *Channel*: Specify the ID of the channel.




</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*conversations.kick* This conversations API method removes a user from a conversation.

</td>
<td valign="top">

-   *Channel*: Specify the ID of the channel.

-   *User*: Specify the ID of the user.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *conversations.list* This conversations API method helps to get list of all channels in Slack Team. The "channels" get returned depending on what the calling token has access to, and the directives placed in the types of parameter.

-   *conversations.listConnectInvites* This conversations API method helps get list of shared channel invites that have been generated or received but have not been approved by all parties.
-   *conversations.open* This conversations API method helps open or resume a direct message or multi-person direct message.



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *conversations.mark* This conversations API method helps set the read cursor in a channel.

-   *conversations.replies* This conversations API method helps retrieve a thread of messages posted to a conversation. Unique identifier of message you want is marked as most recently seen in this conversation.



</td>
<td valign="top">

-   *Channel*: Specify the ID of the channel.

-   *ts*: Specify the timestamp of the message.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*conversations.rename* This conversations API method helps rename a conversation.

</td>
<td valign="top">

-   *Name*: Specify the name of the public or the private channel.

-   *Channel*: Specify the channel to rename in the conversation.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*conversations.setPurpose* This conversations API method helps set the purpose for a conversation.

</td>
<td valign="top">

-   *Channel*: Specify the ID of the channel.

-   *Purpose*: Specify the new, special purpose



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*conversations.setTopic* This conversations API method helps set the topic for a conversation.

</td>
<td valign="top">

-   *Channel*: Specify the ID of the channel.

-   *Topic*: Specify the new topic string. Does not support formatting or linking.



</td>
</tr>
<tr>
<td valign="top">

Dialog Method Group

</td>
<td valign="top">

*dialog.open* You can open a dialog with a user

</td>
<td valign="top">

-   *Dialog*: Specify the dialog definition. This must be a JSON-encoded string.

-   *Trigger ID*: Specify the ID to Exchange a trigger to post to the user..



</td>
</tr>
<tr>
<td valign="top">

DND Method Group

</td>
<td valign="top">

-   *dnd.endDnd* This DND API method ends the current user's Do Not Disturb session immediately.

-   *dnd.endSnooze* This DND API ends the current user's snooze mode immediately.
-   *dnd.info* This DND API retrieves a user's current Do Not Disturb status.
-   *dnd.setSnooze* This DND API turns on Do Not Disturb mode for the current user, or changes its duration.



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*dnd.teamInfo* This DND API retrieves the Do Not Disturb status for up to 50 users on a team.

</td>
<td valign="top">

*Users*: Specify the list of users to whom DND message will be retrieved.

</td>
</tr>
<tr>
<td valign="top">

Emoji Method Group

</td>
<td valign="top">

*emoji.list* This Emoji API lists custom emoji for a team.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Files Method Group

</td>
<td valign="top">

*files.comment.delete* This File API deletes an existing comment on a file. Only the original author of the comment or a Team Administrator may delete a file comment.

</td>
<td valign="top">

-   *ID*: Specify the ID of the file

-   *File*: Specify the file to delete a comment from.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *files.delete* This File API deletes a file from a conversation.

-   *files.info* This File API accesses file information.
-   *files.revokePublicURL* This File API revokes public/external sharing access for a file.
-   *files.sharedPublicURL* This File API method enables a file for public/external sharing.



</td>
<td valign="top">

*File*: Specify the file name.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *files.list* This File API gets list for a team, in a channel, or from a user with applied filters.

-   *files.remote.info* This File API retrieves information about a remote file added to Slack.
-   *files.remote.list* This File API gets list of remote files added to Slack.
-   *files.remote.remove* This File API removes a remote file.
-   *files.remote.update* This File API updates an existing remote file.
-   *files.upload* This File API helps upload a file.



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*files.remote.add* This File API adds a file from a remote service.

</td>
<td valign="top">

-   *External ID*: Specify the creator defined GUID for the file.

-   *External URL*: Specify the URL of the remote file.
-   *Title*: Specify the title of the file being shared



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*files.remote.share* This File API shares a remote file into a channel.

</td>
<td valign="top">

*Channels*: Comma-separated list of channel IDs where the file will be shared.

</td>
</tr>
<tr>
<td valign="top">

Openid Method Group

</td>
<td valign="top">

*openid.connect.userInfo* This OpenID API method gets the identity of a user who has authorized Sign in with Slack.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Pins Method Group

</td>
<td valign="top">

-   *pins.add* This Pin API method pins an item to a channel.

-   *pins.list* This Pin API method lists items pinned to a channel.
-   *pins.remove* This Pin API method remove pins from a channel.



</td>
<td valign="top">

*Channel*: Specify the Channel ID.

</td>
</tr>
<tr>
<td valign="top">

Reactions Method Group

</td>
<td valign="top">

*reactions.add* This Reactions API method adds reactions to an item.

</td>
<td valign="top">

-   *Name*: Specify the name of the public or the private channel.

-   *Channel*: Specify the channel ID.
-   *Timestamp*: Specify the timestamp of the message to add reaction to



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *reactions.get* This Reactions API method gets reactions for an item.

-   *reactions.list* This Reactions API method lists reactions made by a user.



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*reactions.remove* This Reactions API method removes a reaction from an item.

</td>
<td valign="top">

*Name*: Specify the name of the public or the private channel.

</td>
</tr>
<tr>
<td valign="top">

Reminders Method Group

</td>
<td valign="top">

*reminders.add* This Reminders API method creates a reminder.

</td>
<td valign="top">

-   *Text*: Specify the text of the message to send.

-   *Time*: Specify the time when this reminder should happen: the Unix timestamp \(up to five years from now\), the number of seconds until the reminder \(if within 24 hours\), or a natural language description \(Ex. "in 15 minutes," or "every Thursday"\).



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *reminders.complete* This Reminders API method marks a reminder as complete.

-   *reminders.delete* This Reminders API method deletes a reminder.
-   *reminders.info* This Reminders API method gets information about a reminder.



</td>
<td valign="top">

*Reminder*: Specify the ID of the reminder.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*reminders.list* This Reminders API method lists all reminders created by or for a given user.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

RTM Method Group

</td>
<td valign="top">

*rtm.connect* This RTM API method starts Real Time Messaging session.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Search Method Group

</td>
<td valign="top">

-   *search.all* This Search API method searches for messages and files matching a query.

-   *search.files* This Search API method searches for files matching a query.
-   *search.messages* This Search API method searches for messages in a file.



</td>
<td valign="top">

*Query*: Specify the search query. May contain Booleans, etc. This method allows users and applications to search both messages and files in a single call

</td>
</tr>
<tr>
<td valign="top">

Stars Method Group

</td>
<td valign="top">

-   *stars.add* This Stars API method saves an item for later. Formerly known as adding a star. This method adds a star to an item \(message, file, file comment, channel, private group, or DM\) on behalf of the authenticated user.

-   *stars.list* This Stars API method lists a user's saved items, formerly known as stars.
-   *stars.remove* This Stars API method removes a saved item \(star\) from an item.



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Teams Method Group

</td>
<td valign="top">

-   *team.accessLogs* This Teams API method gets the access logs for the current team.

-   *team.billableInfo* This Teams API method gets billable users’ information for the current team.
-   *team.billing.info* This Teams API method reads a workspace's billing plan information.
-   *team.info* This Teams API method gets information about the current team.
-   *team.integrationLogs* This Teams API method gets the integration logs for the current team.
-   *team.preferences.list* This Teams API method retrieves a list of a workspace's team preferences.
-   *team.profile.get* This Teams API method retrieves a team's profile.



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Usergroups Method Group

</td>
<td valign="top">

*usergroups.create* This Usergroups API Method creates a new user group

</td>
<td valign="top">

*Name*: Specify the name of the public or the private channel.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

-   *usergroups.disable* This Usergroups API Method disables an existing User Group.

-   *usergroups. enable* This Usergroups API Method enables an existing User Group.
-   *usergroups.update* This method updates the properties of an existing User Group.
-   *usergroups.users.list* This API method lists all users in a User Group.



</td>
<td valign="top">

*Usergroup*: Specify the encoded ID of the User Group.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*usergroups.list* This method returns a list of all users within a User Group. This Conversations API method opens a multi-person direct message or just a 1:1 direct message.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*usergroups.users.update* This method updates the list of users that belong to a User Group. This method replaces all users in a User Group with the list of users provided in the users parameter.

</td>
<td valign="top">

-   *Users*: Specify the list of users to add as participants in the Call.

-   *Usergroup*: Specify the encoded ID of the User Group.



</td>
</tr>
<tr>
<td valign="top">

Users Method Group

</td>
<td valign="top">

-   *users.conversations* This Users API Method lists conversations the calling user may access.

-   *users.deletePhoto* This method deletes the user profile photo
-   *users.getPresence* This method gets user presence information.
-   *users.identity* This method gets a user's identity.
-   *users.list* This API method Lists all users in a Slack team.
-   *users.profile.get* This method retrieves a user's profile information, including their custom status.
-   *users.profile.set* This method sets a user's profile information, including custom status.
-   *users.setPhoto* This method sets the user profile photo.



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*users.info* This method gets information about a user.

</td>
<td valign="top">

*User*: Specify ID of the user

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*users.lookupByEmail* This method finds a user with an email address.

</td>
<td valign="top">

*Email*: Specify the email address of the user.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*users.setPresence* This method sets user presence manually.

</td>
<td valign="top">

*Presence*: Specify the presence to either auto or away.

</td>
</tr>
<tr>
<td valign="top">

Views Method Group

</td>
<td valign="top">

-   *views.open* This method opens a view for a user.

-   *views.push* This method pushes a view onto the stack of a root view.



</td>
<td valign="top">

-   *Trigger ID*: Specify the ID to exchange a trigger to post to the user.

-   *View*: Specify the view and this must be a JSON-encoded string.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*views.publish* This method publishes a static view for a User.

</td>
<td valign="top">

-   *User ID*: Specify the ID of the user.

-   *View*: Specify the view and this must be a JSON-encoded string.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*views.update* This method updates an existing view.

</td>
<td valign="top">

-   *External ID*: Specify the creator defined GUID for the file.

-   *View*: Specify the view and this must be a JSON-encoded string.



</td>
</tr>
<tr>
<td valign="top">

Workflows Method Group

</td>
<td valign="top">

*workflows.stepCompleted* This method indicates that an app's step in a workflow completed execution.

</td>
<td valign="top">

*Workflow Step Execute ID*: Specify the Context identifier that maps to the correct workflow step execution.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*workflows.stepFailed* This method indicates that an app's step in a workflow failed to execute.

</td>
<td valign="top">

-   *Workflow Step Execute ID*: Specify the Context identifier that maps to the correct workflow step execution.

-   *Error*: Specify the error for a JSON-based object with a message property that should contain a human readable error message.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*workflows.updateStep* This method updates the configuration for a workflow step.

</td>
<td valign="top">

*Workflow Step Edit ID*: A context identifier provided with view\_submission payloads used to call back to workflows.updateStep.

</td>
</tr>
</table>

