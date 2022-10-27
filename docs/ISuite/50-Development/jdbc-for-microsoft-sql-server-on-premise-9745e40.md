<!-- loio9745e4096fd9438fb681fac8270f11f1 -->

# JDBC for Microsoft SQL Server \(On-Premise\)

JDBC receiver adapter supports Microsoft SQL Server On-Premise database provided by Microsoft.

<a name="loio9745e4096fd9438fb681fac8270f11f1__table_uqd_tph_wtb"/>Database Details


<table>
<tr>
<td valign="top">

Database Provider



</td>
<td valign="top">

Microsoft



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

Neo and Cloud Foundry



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

JDBC URL Pattern



</td>
<td valign="top">

`jdbc:sqlserver://[serverName[\instanceName][:portNumber]][;property=value[;property=value]]`

You can delimit properties by using semicolon \(;\). You can't duplicate them.



</td>
</tr>
<tr>
<td valign="top">

Multi-instance support:

To connect to database, provide the instance name in the URL using property instanceName.



</td>
</tr>
<tr>
<td valign="top">

JDBC URL Example



</td>
<td valign="top">

`jdbc:sqlserver://testmysql:3333;database=testdb;instanceName=SQLEXPRESS`



</td>
</tr>
</table>

Before connecting to this database, you must upload the drivers and then, add the Data Source. For more details, see [Configure JDBC Drivers](configure-jdbc-drivers-77c7d95.md) and [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

**Related Information**  


[JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md "The JDBC (Java Database Connectivity) adapter enables you to connect Cloud Integration to cloud or on-premise databases.")

