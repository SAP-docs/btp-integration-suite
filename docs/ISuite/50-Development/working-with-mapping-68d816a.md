<!-- loio68d816a062484e13b5ae72ece1044e79 -->

# Working with Mapping

> ### Remember:  
> There are currently certain limitations when working in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

This feature enables you to define an association between fields of messages with different structuring. For example, consider the record **Employee** and we need to update the employee identification number. In the sender system, the field name is **Employee ID**. However, in the receiver system, the same field is called **ID**.

Similarly, the table illustrates how the same fields might have different identifiers in the source and target systems.

****


<table>
<tr>
<th valign="top">

Source Field

</th>
<th valign="top">

Target Field

</th>
</tr>
<tr>
<td valign="top">

Employee

</td>
<td valign="top">

User

</td>
</tr>
<tr>
<td valign="top">

Employee ID

</td>
<td valign="top">

ID

</td>
</tr>
<tr>
<td valign="top">

Employee Name

</td>
<td valign="top">

Name

</td>
</tr>
<tr>
<td valign="top">

Employee Surname

</td>
<td valign="top">

LastName

</td>
</tr>
<tr>
<td valign="top">

Date of Birth

</td>
<td valign="top">

DOB

</td>
</tr>
</table>

> ### Caution:  
> If you delete a message mapping step and the mapping definition resource associated with it is not used in any other message mapping step, then the resource also gets deleted.



<a name="loio68d816a062484e13b5ae72ece1044e79__section_pfdb_ms3_222_sfb"/>

## Use

You use message mapping, to define an association between fields of messages with different structuring. This enables the Cloud Integration system to recognize and update the relevant fields in the target systems.

Each message mapping flow step in an integration flow is associated with a mapping definition resource. You create this definition while adding the mapping step to the integration flow. You can also reuse a definition resource that you have already created in the same integration flow project.

