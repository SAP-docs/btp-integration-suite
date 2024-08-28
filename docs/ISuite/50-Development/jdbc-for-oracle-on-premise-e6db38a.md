<!-- loioe6db38ab14ac480ab171b51932a481f5 -->

# JDBC for Oracle \(On-Premise\)

JDBC receiver adapter supports Oracle On-Premise database provided by Oracle.

> ### Note:  
> This adapter enables you to connect Cloud Integration to a remote database system. SAP can’t give advice on how to configure the external system nor does SAP provide support related to this system.

**Database Details**


<table>
<tr>
<td valign="top">

Database Provider

</td>
<td valign="top">

Oracle

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

`jdbc:oracle:thin:@<database>`

To connect to Oracle Database SID, use: `jdbc:oracle:thin:@<host>[:<port>]:<SID`\>

</td>
</tr>
<tr>
<td valign="top">

JDBC URL Example

</td>
<td valign="top">

jdbc:oracle:thin:@myoracle:1521:my\_sid

</td>
</tr>
</table>

Before connecting to this database, you must upload the drivers and then, add the Data Source. For more details, see [Configure JDBC Drivers](configure-jdbc-drivers-77c7d95.md) and [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

> ### Note:  
> Oracle RAC setup is not supported.

**Related Information**  


[JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md "The JDBC (Java Database Connectivity) adapter enables you to connect SAP Integration Suite to cloud or on-premise databases.")

