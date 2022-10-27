<!-- loio4173d0aba45d4978bd3f583740aa09e1 -->

# JDBC for Microsoft SQL Server \(Cloud\)

JDBC receiver adapter supports Microsoft SQL Server cloud database provided by Amazon RDS.

<a name="loio4173d0aba45d4978bd3f583740aa09e1__table_uqd_tph_wtb"/>Database Details


<table>
<tr>
<td valign="top">

Database Provider



</td>
<td valign="top">

Amazon RDS



</td>
</tr>
<tr>
<td valign="top">

Infrastructure



</td>
<td valign="top">

Cloud



</td>
</tr>
<tr>
<td valign="top">

SAP BTP Environment



</td>
<td valign="top">

Neo and Cloud Foundry



</td>
</tr>
<tr>
<td valign="top">

JDBC URL Pattern



</td>
<td valign="top">

`jdbc:sqlserver://[serverName[\instanceName][:portNumber]][;property=value[;property=value]]`

You can delimit properties by using semicolon \(;\). You can't duplicate them.



</td>
</tr>
<tr>
<td valign="top">

JDBC URL Example



</td>
<td valign="top">

`jdbc:sqlserver://mysqlserver:1433;databaseName=mysqlserverdb;loginTimeout=0`



</td>
</tr>
</table>

> ### Note:  
> If your databse connection fails, try appending `@servername` with *Username*.

Before connecting to this database, you must upload the drivers and then, add the Data Source. For more details, see [Configure JDBC Drivers](configure-jdbc-drivers-77c7d95.md) and [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

**Related Information**  


[JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md "The JDBC (Java Database Connectivity) adapter enables you to connect Cloud Integration to cloud or on-premise databases.")

