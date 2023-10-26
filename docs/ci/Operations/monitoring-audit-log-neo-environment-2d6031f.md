<!-- loio2d6031ffc1aa4af08a03f0444b979667 -->

# Monitoring Audit Log, Neo Environment

The audit log contains information on system changes. These events can be for example the deployment of an integration flow as well as a configuration change.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

You view the audit log by clicking the tile *Audit Log* in the *Manage Security* area.

> ### Note:  
> To view the content of the log, you need the authorization `AuditLog.Read` .

You can control the display of the messages by adjusting the filter setting *Time Range*.

You can choose from the following preset time ranges:

-   All

-   Past Hour
-   Past 24 Hours
-   Past Week
-   Custom

> ### Note:  
> The audit log data retention time in the database is 30 days.

You can retrieve the following information from the audit log list and filter the entries by *Object Name*, *User* or *Source* 

**Audit log List**


<table>
<tr>
<th valign="top">

Attributes

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Time* 

</td>
<td valign="top">

Displays the time of the event.

</td>
</tr>
<tr>
<td valign="top">

*Action* 

</td>
<td valign="top">

Displays the action performed on the system such *Create* or *Delete* 

</td>
</tr>
<tr>
<td valign="top">

*Object Type* 

</td>
<td valign="top">

Displays the object type such as *IntegrationFlow* on which the action was performed on.

</td>
</tr>
<tr>
<td valign="top">

*Object Name* 

</td>
<td valign="top">

Displays the object name such as the integration flow name.

</td>
</tr>
<tr>
<td valign="top">

*User* 

</td>
<td valign="top">

Displays the user who triggered the action.

</td>
</tr>
<tr>
<td valign="top">

*Source* 

</td>
<td valign="top">

Displays the IP address of the source that issued the action.

</td>
</tr>
</table>

> ### Note:  
> If an SAP user triggers the changes, *User* and *Source* are displayed as *SAP* in the audit log list.

You can also sort the audit log list by *Time*, *Action*, *Object Type* or *Object Name*.

> ### Note:  
> The audit log retrieves a maximum of 1000 entries from the data base. If you have more than 1000 entries in the selected time range, you will be prompted to adjust your filter settings accordingly .

**Related Information**  


 <?sap-ot O2O class="- topic/link " href="289ef3f8cfad442ea86fe0d5ddad8c42.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/cvv1690968981196/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/2d6031ffc1aa4af08a03f0444b979667.xml" ?> 

