<!-- loio3968091c619048729d789686dd7a74cd -->

# Involved Roles

The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.

**Roles in the Security Artifact Renewal Process**


<table>
<tr>
<th valign="top">

Role

</th>
<th valign="top">

Tasks

</th>
</tr>
<tr>
<td valign="top">

Sender/receiver administrator \(at customer side\)

</td>
<td valign="top">

Updates the security artifacts owned by the sender/receiver back-end system \(for example, the keystore\).

</td>
</tr>
<tr>
<td valign="top">

Integration developer

</td>
<td valign="top">

Updates the integration flow in certain use cases.

It depends on the **operating model** whether the tenant administrator and the integration developer are at the customer or at SAP. In the **customer-managed operating model**, the tenant administrator and integration developer tasks are performed by the customer. In the **SAP-managed operating model**, these tasks are performed by SAP.

</td>
</tr>
<tr>
<td valign="top">

Tenant administrator

</td>
<td valign="top">

Updates the security artifacts of the tenant \(relevant for outbound communication\).

It depends on the **operating model** whether the tenant administrator and the integration developer are at the customer or at SAP. In the **customer-managed operating model**, the tenant administrator and integration developer tasks are performed by the customer. In the **SAP-managed operating model**, these tasks are performed by SAP.

</td>
</tr>
<tr>
<td valign="top">

Load balancer administrator

</td>
<td valign="top">

Updates the security artifacts of the load balancer \(relevant for inbound communication\).

</td>
</tr>
</table>

**Related Information**  


[Operating Model](../WhatIsCloudIntegration/operating-model-72010e6.md "An operation model clearly defines the separation of tasks between SAP and the customer during all phases of an integration project.")

