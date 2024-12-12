<!-- loio4d5b488b4f394c51974ea8cb520e6d92 -->

# JDBC for PostgreSQL \(Cloud\)

JDBC receiver adapter supports PostgreSQL cloud database provided by Amazon RDS and Microsoft Azure.

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

`jdbc:postgresql://host:port/database?param1=value1&param2=value2&…`

</td>
<td valign="top">

`jdbc:postgresql://host:port/database?param1=value1&param2=value2&…`

</td>
</tr>
<tr>
<td valign="top">

JDBC URL Example

</td>
<td valign="top">

`jdbc:postgresql://mypostgresql:5434/mypostgresdb?ssl=false&loglevel=2`

</td>
<td valign="top">

`jdbc:postgresql://mypostgresql:5434/mypostgresdb?ssl=false&loglevel=2`

</td>
</tr>
</table>

Before connecting to this database, you must add the Data Source. For more details, see [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

> ### Note:  
> JDBC receiver adapter enables you to connect Cloud Integration to a remote database system. SAP can’t give advice on how to configure the external system nor does SAP provide support related to this system.

**Related Information**  


[JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md "The JDBC (Java Database Connectivity) adapter enables you to connect SAP Integration Suite to cloud or on-premise databases.")

