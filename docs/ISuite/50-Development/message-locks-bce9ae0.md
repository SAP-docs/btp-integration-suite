<!-- loiobce9ae0cf9594b2d8a32fafc981b2076 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Message Locks

This section allows you to display and manage lock entries that are created \(in the in-progress repository\) to avoid the same message being processed several times in parallel \(for example, by different runtime nodes\).

> ### Tip:  
> Example:
> 
> Several runtime nodes try to read a file from an SFTP server \(through SFTP sender channels\).
> 
> To prevent double processing, a lock entry is written to the in-progress repository each time a file is processed by a runtime node. As long as this lock entry exists, no other component can access the file. After message processing, the lock is removed by the runtime.

In certain situations \(for example, a runtime node crashes because of an out-of-memory error\), the message is retried after the node is restarted until the expiration time is reached. In this case, lock entries could remain in the in-progress repository and block subsequent message processing. You can use the *Manage Locks* view to analyze the situation and manually delete lock entries, if necessary, to reprocess the message.

If you choose the *Message Locks* tile under *Manage Locks* tile in the *Monitor* application, a list of locks is displayed. Be aware that only the most recent 500 lock entries are displayed.

The following information is shown for each lock entry:

****


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

Component that wrote the lock entry

AS2, JMS, Mail, SFTP, and XI adapters can write locks.

</td>
</tr>
<tr>
<td valign="top">

*Source* 

</td>
<td valign="top">

Component that caused the lock

Example for SFTP: `user_sftp@ld1234.mycompany.corp`

</td>
</tr>
<tr>
<td valign="top">

*Entry* 

</td>
<td valign="top">

Content of the lock entry

Example for SFTP: `directory1/dir2/test.xml` 

If the lock relates to an SFTP connection, the *Entry* field shows a file name \(of the file that the SFTP adapter tries to read from the SFTP server\).

This parameter provides a link to the message in the Managing Message Queues monitor.

To access the associated JMS Message, click *ID*. The Queue Monitor opens and loads the JMS Message.

This is only possible for JMS locks.

</td>
</tr>
<tr>
<td valign="top">

*Created at* 

</td>
<td valign="top">

Time when the lock was created

This is the time when a runtime node tried to process the message for the first time.

</td>
</tr>
<tr>
<td valign="top">

*Expires at* 

</td>
<td valign="top">

Time when lock entry expires

If the message is retried but cannot be processed successfully before the expiration time, processing is stopped. In this case, the lock entry has to be removed manually to enable further processing.

</td>
</tr>
</table>

You can also search for table entries \(search field\).

To sort and filter the content of the table, choose *Table Settings* \(:gear:\). On the subsequent screen, you can define how the table entries are to be sorted \(by specifying an attribute and whether the entries are to be sorted for that attribute in ascending or descending order\). You can also filter the table entries for certain attributes.

To remove the lock entry and retrigger message processing, select the entry and choose *Release*.

> ### Caution:  
> Before releasing a lock entry, make sure you do a careful problem analysis. In particular, make sure that you've understood how the lock entry in question relates to the actual problem you are trying to solve. Careless usage of the release lock function can lead to data inconsistencies or other serious problems.
> 
> For example, in the case of an SFTP connection the lock entry is a file name \(including the file path\). In this case, check whether the problem is related to the file that is to be processed through SFTP.
> 
> Another indicator is the duration of the lock \(time that has passed since the time specified under *Created at*\).

**Related Information**  


[Cloud Integration – Configure Dead Letter Handling in JMS Adapter](https://blogs.sap.com/2017/07/17/cloud-integration-configure-dead-letter-handling-in-jms-adapter/)

[JMS Adapter](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/jms-adapter?state=DRAFT&q=Message%20Locks)

