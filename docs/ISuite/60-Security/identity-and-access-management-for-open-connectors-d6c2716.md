<!-- loiod6c271683a264d949bb1a9ffa8815a2f -->

# Identity and Access Management for Open Connectors

Learn about the personas and roles in Open Connectors, as well as their typical tasks and permissions.



<a name="loiod6c271683a264d949bb1a9ffa8815a2f__section_cxz_vsk_pcc"/>

## Personas and Roles

The following role collections exist for Open Connectors :


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

*OpenConnectors\_User*

To permit additional users access to Open Connectors, assign the `OpenConnectors_User` role collection to the new user.

> ### Note:  
> No action needed if the logged user already has the `Integration Provisioner` role collection.



</td>
<td valign="top">

Add non-SAP cloud applications to your integration scenarios.

> ### Note:  
> Just adding the `OpenConnectors_User` role collection in the SAP BTP Trust Configuration cockpit isn't sufficient to access Open Connectors. The newly added user will have to be explicitly added as a **member** by the Open Connectors admin users.
> 
> See [Grant Users Access to Open Connectors, Capability Within SAP Integration Suite](https://blogs.sap.com/2024/01/08/grant-the-user-to-access-to-open-connectors-capability-of-integration-suite/) .



</td>
</tr>
</table>

