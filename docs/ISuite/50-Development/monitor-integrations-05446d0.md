<!-- loio05446d0616d44e1daf821c273b69fcc6 -->

# Monitor Integrations

Check the status of messages and integration content artifacts for a tenant cluster.

The start page is subdivided into the following sections, each covering a specific task area.

**Sections on Monitor Start Page**


<table>
<tr>
<th valign="top">

Container

</th>
<th valign="top">

Allows you to ...

</th>
</tr>
<tr>
<td valign="top">

*Monitor Status Overview* 

</td>
<td valign="top">

Monitor the status overview of your messages according to your custom filters.

</td>
</tr>
<tr>
<td valign="top">

*Monitor Message Processing* 

</td>
<td valign="top">

Monitor message processing on the tenant.

Tiles in this section show the number and status of processed messages within a specified time window.

</td>
</tr>
<tr>
<td valign="top">

*Manage Integration Content* 

</td>
<td valign="top">

Manage integration content for the tenant.

Tiles in this section show the number and status of integration content artifacts \(such as integration flows\).

</td>
</tr>
<tr>
<td valign="top">

*Manage Security* 

</td>
<td valign="top">

Manage security artifacts for the tenant.

Tiles in this section allow you to manage certain tasks related to the setup of secure connections between your tenant and remote systems.

The *Security Material* tile provides access to and allows you to deploy security-related artifacts such as user credentials artifacts.

The *Keystore* tile provides access to the content of the tenant keystore and allows you to manage its content and also the lifecycle of keys and certificates.

The *PGP Keys* tile allows you to check the information of the PGP keys.

The *Access Policies* tile provides an overview of the existing access policies and allows you to maintain them.

The *JDBC Material* tile provides an overview of the used JDBC data sources \(artifact connections interacting with a database\) as well as of the JDBC drivers.

The *User Roles* tile provides an overview of the existing user roles and allows you to maintain them.

The *Connectivity Tests* tile allows you to test the connectivity to a receiver system.

</td>
</tr>
<tr>
<td valign="top">

*Manage Stores* 

</td>
<td valign="top">

Manage temporary data storages on the tenant.

The *Data Stores* tile provides an overview of storages on the tenant, which are temporarily used to persist data of different kind during message processing \(when using the Data Store Operations step type\).

The *Variables* tile allows you to monitor variables used in integration flows.

The *Message Queues* tile provides an overview of the active queues of a tenant and allows you to manage them

> ### Note:  
> You can only monitor message queues, if Enterprise Messaging is activated and a JMS Message broker is provisioned. \(See: [Activating Enterprise Messaging](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/a74cddceacb34abb958e817c1f6782d2.html "Activate SAP Event Mesh.") :arrow_upper_right:\)

The *Number Ranges* tile provides an overview of number ranges that are used in business-to-business scenarios.

</td>
</tr>
<tr>
<td valign="top">

*Access Logs* 

</td>
<td valign="top">

Access the *System Log Files* and to analyze errors that occurred during inbound HTTP processing \(and documented in system log files\).

You access the system logs can access the system logs only if the `Cloud Logging Service` is available for your Cloud Integration application. This feature isn't yet enabled on all data centers.

</td>
</tr>
<tr>
<td valign="top">

*Manage Locks* 

</td>
<td valign="top">

Manage message lock as well as the design artifact lock entries.

The *Message Lock* tile provides an overview of the lock entries that are created \(in the in-progress repository\) to avoid the same message being processed several times in parallel, and allows you to manage them.

The *Designtime Artifact Locks* tile provides an overview of the locked design time artifacts and allows you to manage them.

</td>
</tr>
</table>

Each section contains tiles, which show filter settings and the number of messages/artifacts that correspond to the filter settings.

Selecting a tile opens a page with more information.

The start page is automatically refreshed every 5 seconds. The autorefresh ends after 5 minutes \(indicated by a message\).

> ### Note:  
> All times displayed on the Monitoring pages are local times \(with regard to the client of the Web application\).



## Managing Tiles

You can customize the start page to fit your personal needs by adding new tiles \(by selecting an empty tile containing a `+` symbol\) or deleting existing ones. You can also rearrange the start page by dragging and dropping tiles to another location. For example, you can customize the start page so that it shows only data related to integration flows that are edited by you.

> ### Note:  
> You can rearrange tiles only within the same section.
> 
> You can add, delete, or edit tiles in the following section types:
> 
> -   *Monitor Message Processing*
> 
> -   *Manage Integration Content*

> ### Note:  
> The personal settings are persisted in the client of the user. So, you can log out, close the browser, and log on again to the monitoring, and the previously specified user settings are kept.

To edit a tile, right-click the tile and choose *Edit*.

When you add or edit a tile, you can specify the following filter categories:

-   For *Monitor Message Processing* tiles you can specify *Status*, *Time*, and the related *Integration Artifact* or *Package* for the messages to be displayed.

    In the dropdown list for the *Artifact*, the display name and type are shown. The tooltip for an entry additionally shows the technical name and the package \(if available\) of the corresponding integration artifact.

-   For *Manage Integration Content* tiles, you can specify the *Status*, and the *Type* of the integration artifact to be displayed.


**Related Information**  


[Monitor Message Processing](monitor-message-processing-314df3f.md "The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.")

[Manage Integration Content](manage-integration-content-09a7223.md "The Manage Integration Content section provides an overview of integration content artifacts, such as integration flows, that have been deployed on the tenant.")

[Manage Security](manage-security-6e7c44c.md "The Manage Security section allows you to manage various kinds of security material (for example, user credentials, keystore entries), and to perform outbound connectivity tests.")

[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

[Managing Keystore Entries](managing-keystore-entries-2dc8942.md "The Keystore Monitor allows a tenant administrator to manage the tenant keystore and its entries (X.509 certificates and key pairs).")

[Managing PGP Keys](managing-pgp-keys-cd478a7.md "The PGP Keys monitor allows a tenant administrator to manage the public and private PGP keys.")

[Creating Custom Roles for Access Policies](creating-custom-roles-for-access-policies-7db3c87.md "Define a custom role to be associated with an access policy.")

[Managing User Roles](managing-user-roles-4e86f0d.md "The user role monitor allows a tenant administrator to manage user roles which then can be used during inbound authorization of an integration flow execution.")

[Managing JDBC Material](managing-jdbc-material-32ee7cd.md "Learn how JDBC Materials supports SAP Integration Suite for interacting with your database server.")

[Performing Connectivity Tests](performing-connectivity-tests-d5b2fae.md "You can test the connectivity to a receiver system.")

[Manage Stores](manage-stores-59f8e3a.md "The Manage Stores section allows you to manage various temporary data storages on your tenant.")

[Managing Data Stores](managing-data-stores-ac39f1d.md "")

[Managing Variables](managing-variables-ca93653.md "The Variables view allows you to monitor variables used in integration flows.")

[Managing Number Ranges](managing-number-ranges-b6e17fa.md "The topic provides an overview of number ranges related artifacts.")

[Access Logs](access-logs-c1649cd.md "The Access Logs section allows you to monitor and to analyze errors that occurred during inbound HTTP processing (and documented in system log files)")

[Manage Locks](manage-locks-e3fb788.md "The Manage Locks section lets you manage various locked entities on your tenant.")

[Message Locks](message-locks-bce9ae0.md "This section allows you to display and manage lock entries that are created (in the in-progress repository) to avoid the same message being processed several times in parallel (for example, by different runtime nodes).")

[Designtime Artifact Locks](designtime-artifact-locks-5b3ecb8.md "As tenant administrators, use this self-service capability to view and unlock the integration artifacts and packages in the tenant that are locked by the users of the tenant.")

