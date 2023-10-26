<!-- loio8871b61f9e1f473591988e1ad38c8b01 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Manage Locks

This section allows you to display and manage lock entries that are created, to avoid the same message being processed several times in parallel.

On the Message Monitor overview page, select a runtime from the list of available runtimes.

Choose the *Message Locks* tile under the *Manage Locks* section in the Monitor application, to display the list of locks.

You get the following information:


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

*Component* 

</td>
<td valign="top">

The component writing the lock entry. \(AS2, JMS, Mail, SFTP, and XI adapters can write locks.\)

</td>
</tr>
<tr>
<td valign="top">

*Source* 

</td>
<td valign="top">

The component causing the lock.

</td>
</tr>
<tr>
<td valign="top">

*Entry* 

</td>
<td valign="top">

Content of the lock entry. This parameter provides a link to the message in the message queues monitor. To access the associated JMS Message, click ID. The queue monitor opens and loads the JMS Message. This operation is only possible for JMS locks.

</td>
</tr>
<tr>
<td valign="top">

*Created At* 

</td>
<td valign="top">

Time when the lock was created.

</td>
</tr>
</table>

> ### Note:  
> You can always switch the runtime to display the message locks of a particular runtime.

You also search for table entries, using the search field.

To sort and filter the content of the table, choose *Table Settings* \(:gear:\). On the subsequent screen, you can define how the table entries are to be sorted \(by specifying an attribute and whether the entries are to be sorted for that attribute in ascending or descending order\). You can also filter the table entries for certain attributes.

To remove the lock entry and retrigger message processing, select the entry and choose *Release*.

For more information about the JMS Adapter, see: [JMS Adapter](50-Development/jms-adapter-0993f2a.md)

