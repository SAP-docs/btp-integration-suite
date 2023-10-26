<!-- loio5b3ecb8c0300446daa2f196e74943a42 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Designtime Artifact Locks

As tenant administrators, use this self-service capability to view and unlock the integration artifacts and packages in the tenant that are locked by the users of the tenant.

There could be scenarios where a user locked a design time artifact and didn't release it. For example, an integration developer could have locked an integration flow to update it as per the revised business logic. But if the user is unavailable for various reasons and there's an urgent business need to edit the artifact, the tenant administrators can release the artifacts. The tenant administrators can unlock the artifact anytime after it was locked by a user.

Choose *Monitor* \> *Integrations* \> *Designtime Artifact Locks*, to see the list of design time artifacts that are in locked status. All users of the tenant can view the locked artifacts. Only the tenant administrators can unlock the artifacts using the :unlock: icon. After confirming the unlock action, the artifact gets unlocked and removed from the list.

The following information is shown for each locked artifact:


<table>
<tr>
<th valign="top">

Attribute

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

Name of the artifact that is locked.

</td>
</tr>
<tr>
<td valign="top">

*Type* 

</td>
<td valign="top">

Type of the artifact that is locked, like integration flow, REST API, or integration package.

</td>
</tr>
<tr>
<td valign="top">

*Package* 

</td>
<td valign="top">

For integration artifacts, the name of the package to which the locked artifact belongs.

</td>
</tr>
<tr>
<td valign="top">

*Locked At* 

</td>
<td valign="top">

Time when the user locked the artifact.

</td>
</tr>
<tr>
<td valign="top">

*Locked By* 

</td>
<td valign="top">

Name of the user who locked the artifact.

</td>
</tr>
</table>

