<!-- loio9515cf8288d049479604b32836a58efe -->

# JDBC for DB2 \(On-Premise\)

JDBC receiver adapter supports DB2 On-Premise database provided by IBM.

> ### Note:  
> This adapter enables you to connect Cloud Integration to a remote database system. SAP can’t give advice on how to configure the external system nor does SAP provide support related to this system.

**Database Details**


<table>
<tr>
<td valign="top">

Database Provider

</td>
<td valign="top">

IBM

</td>
</tr>
<tr>
<td valign="top">

Infrastructure

</td>
<td valign="top">

On-Premise

</td>
</tr>
<tr>
<td valign="top">

SAP BTP Environment

</td>
<td valign="top">

Cloud Foundry

</td>
</tr>
<tr>
<td valign="top">

JDBC URL Pattern

</td>
<td valign="top">

`jdbc:db2://<host>:<port>/<database_name>:property1=value1;property2=value2;...`

Each property and value pair, including the last one, must end with a semicolon \(;\). Don't include space or other white-space characters anywhere within the list of property and value strings.

</td>
</tr>
<tr>
<td valign="top">

JDBC URL Example

</td>
<td valign="top">

`jdbc:db2://mydb2:5021/mydb2db`

</td>
</tr>
</table>

Before connecting to this database, you must upload the drivers and then, add the Data Source. For more details, see [Configure JDBC Drivers](configure-jdbc-drivers-77c7d95.md) and [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

**Related Information**  


[JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md "The JDBC (Java Database Connectivity) adapter enables you to connect SAP Integration Suite to cloud or on-premise databases.")

