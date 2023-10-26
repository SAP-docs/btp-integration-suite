<!-- loio1d470b08132f428d97ed4b2128df0c13 -->

# Managing Users and Role Assignments, Neo Environment

You specify the members of the account and assign roles to them.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

If this function is not available for your account, ask your SAP contact to activate it.

This task includes initial activities by the tenant administrator to assign roles to the users associated with all people who are supposed to work on the tenant cluster.

The task is sub dividied into the following main activities:

-   Adding members to the account:

    With this step, you specify all users who should have assigned the same role like the tenant administrator

    In addition to that, you can also define all users who should have a *restricted* tenant administrator role \(on the account\). This specific role allows you to to assign application-specific roles to other users of the account \(like, for example, the integration developer role\).

-   Defining authorizations for individual integration team members:

    With this step, you assign the actual application-specific roles to the integration team members \(like, for example, the integration developer role\)


To perform these steps, open the SAP BTP cockpit using the S-user ID provided to you by SAP \(in the mail that contains also the information on the account\).

The URL of the SAP BTP cockpit depends on the data center.

**SAP BCP Cockpit URLs**


<table>
<tr>
<th valign="top">

Region

</th>
<th valign="top">

URL

</th>
</tr>
<tr>
<td valign="top">

Europe \(Rot\)

</td>
<td valign="top">

[https://account.hana.ondemand.com/cockpit](https://account.hana.ondemand.com/cockpit) 

</td>
</tr>
<tr>
<td valign="top">

US East \(Ashburn\)

</td>
<td valign="top">

[https://account.us1.hana.ondemand.com/cockpit](https://account.us1.hana.ondemand.com/cockpit) 

</td>
</tr>
<tr>
<td valign="top">

Australia \(Sydney\)

</td>
<td valign="top">

[https://account.ap1.hana.ondemand.com/cockpit](https://account.ap1.hana.ondemand.com/cockpit) 

</td>
</tr>
</table>

**Related Information**  


[Adding Members to an Account](adding-members-to-an-account-eb6d612.md "You specify the members of the account to define who is involved in an integration project.")

[Defining Authorizations for Integration Team Members](defining-authorizations-for-integration-team-members-3ec7679.md "To authorize selected people to work on the account as part of the integration team in the context of SAP Cloud Integration (for example, as integration developers), you assign roles to the associated users.")

[Persona](../SecurityNeo/persona-2937e5c.md "When you perform user management tasks using SAP BTP SAP BTP cockpit, you find a set of predefined roles that you can assign to users of the account. According to the main tasks associated with integration projects, these roles are associated to certain persona relevant for an integration project.")

