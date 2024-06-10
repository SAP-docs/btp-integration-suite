<!-- loioee7994609a974cd19614de1a21d84e5f -->

# Personas in Event Mesh

When you perform user management tasks using SAP BTP cockpit, you can find a set of predefined roles that you can assign to users of the account. These roles are associated to certain personas relevant for an event-driven integration project.

Personas cover the different tasks associated with an integration project. To assign the applicable role collections for a user, see [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).


<table>
<tr>
<th valign="top">

Persona

</th>
<th valign="top">

Authentication

</th>
<th valign="top">

Authorization

</th>
<th valign="top">

Associated Role Collection

</th>
</tr>
<tr>
<td valign="top">

Integration Developer in Event Mesh 

</td>
<td valign="top">

OAuth \(Authorization code flow\)

</td>
<td valign="top">

-   Manage queues, topic subscriptions

-   Monitor usage of message brokers and queues




</td>
<td valign="top">

EventMeshDeveloper

</td>
</tr>
<tr>
<td valign="top">

Administrator for Event Mesh 

</td>
<td valign="top">

OAuth \(Authorization code flow\)

</td>
<td valign="top">

-   Manage message brokers

-   Manage queues, topic subscriptions

-   Monitor usage of message broker and queues




</td>
<td valign="top">

EventMeshAdmin

</td>
</tr>
<tr>
<td valign="top">

OAuth Client

</td>
<td valign="top">

OAuth \(Client credentials flow\)

</td>
<td valign="top">

Handle technical communication with the publishing and subscribing applications during binding

</td>
<td valign="top">

Not applicable

</td>
</tr>
</table>

