<!-- loio4173d0aba45d4978bd3f583740aa09e1 -->

# JDBC for Microsoft SQL Server \(Cloud\)

JDBC receiver adapter supports Microsoft SQL Server cloud database provided by Amazon RDS.

> ### Note:  
> This adapter enables you to connect Cloud Integration to a remote database system. SAP can’t give advice on how to configure the external system nor does SAP provide support related to this system.

**Database Details**


<table>
<tr>
<td valign="top">

Database Provider

</td>
<td valign="top">

Amazon RDS

</td>
<td valign="top">

Microsoft Azure

</td>
</tr>
<tr>
<td valign="top">

Infrastructure

</td>
<td valign="top" colspan="2">

Cloud

</td>
</tr>
<tr>
<td valign="top">

SAP BTP Environment

</td>
<td valign="top" colspan="2">

Cloud Foundry

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
<td valign="top">

`jdbc:sqlserver://mysqlserver:1433;databaseName=mysqlserverdb;loginTimeout=0`

</td>
</tr>
</table>

Before connecting to this database, you must upload the drivers and then, add the Data Source. For more details, see [Configure JDBC Drivers](configure-jdbc-drivers-77c7d95.md) and [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

> ### Note:  
> If your database connection fails, try appending `@servername` to your username in the [User](managing-jdbc-data-sources-4c873fa.md#loio4c873fac537248e58767f74e4a74d867__table_th1_2pq_gr) field while adding the [Data Source.](managing-jdbc-data-sources-4c873fa.md) For example, if your username is *test*, and servername is *mysqlserver*, enter*test@mysqlserver* as *User* and try establishing the connection.

**Related Information**  


[JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md "The JDBC (Java Database Connectivity) adapter enables you to connect SAP Integration Suite to cloud or on-premise databases.")

