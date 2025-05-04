<!-- loioca93653ec211457190ff8466e42ff9cd -->

# Managing Variables

The *Variables* view allows you to monitor variables used in integration flows.

> ### Tip:  
> To check which roles have permission to monitor variables, see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

Choose *Monitor* \> *Integrations and APIs*.

If you have activated Edge Integration Cell, select the target runtime \(*Runtime* parameter\). For more information on how to manage stores for Edge Integration Cell, see [Manage Stores for Edge Integration Cell](../manage-stores-for-edge-integration-cell-ced47da.md).

Choose the *Variables* tile in the *Manage Store*section. You get an overview of the existing variables, with the following attributes.

****


<table>
<tr>
<th valign="top">

Table Settings

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

The variable name is defined in the integration flow.

</td>
</tr>
<tr>
<td valign="top">

*Visibility* 

</td>
<td valign="top">

A variable can be globally visible across all deployed integration flows of the tenant or be used only by one integration flow.

</td>
</tr>
<tr>
<td valign="top">

*Integration Flow* 

</td>
<td valign="top">

Displays the ID of the integration flow the variable is used in.

</td>
</tr>
<tr>
<td valign="top">

*Updated At* 

</td>
<td valign="top">

Shows date and time when the variable content was last updated.

</td>
</tr>
<tr>
<td valign="top">

*Retain Until*

</td>
<td valign="top">

Displays date and time until the variable is still available. The retention time is updated along with any update of the variable.

</td>
</tr>
<tr>
<td valign="top">

*Actions*

</td>
<td valign="top">

You can download the variable content or delete the variable.

</td>
</tr>
</table>

You can filter in the table either by variable name or integration flow.

By clicking on the variable name in the table, you can see its content. If the variable content is not defined as a string value, its content cannot be displayed and a message is shown. You can also download the variable by choosing *Download*. If you choose to save the variable, the system creates a `.zip`file, containing the header properties file.

> ### Note:  
> If you want to delete a variable, check that this variable is no longer in use, as there is no “ where used list” available.

