<!-- loioe6b35d1175344f76ae41351dca76fd56 -->

# Working with Mapping Flow Step

Define an association between fields of messages with different structuring within an API artifact. For example, consider the record **Employee** where you need to update the employee identification number. In the sender system, the field name is **Employee ID**. However, in the receiver system, the same field is called **ID**.

Similarly, the table illustrates how the same fields might have different identifiers in the source and target systems:


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
> If you delete a mapping step from the policy model and the mapping definition resource associated with it is not used in any other mapping step, then the resource also gets deleted.



## Use

You use mapping in an API artifact to define an association between fields of messages with different structuring. This enables in recognizing and updating the relevant fields in the target systems when the API artifact processes requests and responses.

Each mapping flow step added to the policy model of an API artifact is associated with a mapping definition resource. You create this definition while adding the mapping step to the API. You can also reuse a definition resource that you have already created in the same API artifact project.



## Mapping Steps


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/Links

</th>
</tr>
<tr>
<td valign="top">

Operation Mapping

</td>
<td valign="top">

Relates an outbound service interface operation with an inbound service interface operation. You can also relate IDoc and RFC interfaces with entities of the same type or with service interface operations.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Operation Mapping](operation-mapping-05b9569.md).

</td>
</tr>
<tr>
<td valign="top">

XSLT Mapping

</td>
<td valign="top">

Assigns XSLT mapping that is available in your local workspace.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Create XSLT Mapping](create-xslt-mapping-5ce1f15.md).

</td>
</tr>
<tr>
<td valign="top">

ID Mapping

</td>
<td valign="top">

Maps a source message ID to a target message ID.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define ID Mapping](define-id-mapping-2367101.md).

</td>
</tr>
<tr>
<td valign="top">

Message Mapping

</td>
<td valign="top">

Defines an association between fields of messages with different structuring. This enables the Cloud Integration system to recognize and update the relevant fields in the target systems.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Creating Message Mapping as a Flow Step](creating-message-mapping-as-a-flow-step-3d5cb7f.md).

</td>
</tr>
</table>

