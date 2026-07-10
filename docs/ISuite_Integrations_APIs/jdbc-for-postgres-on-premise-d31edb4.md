<!-- loiod31edb4da0654b4192765945aab2bbdd -->

# JDBC for Postgres \(On-Premise\)

JDBC receiver adapter supports Postgre On-Premise database.

> ### Note:  
> This adapter enables you to connect Cloud Integration to a remote database system. SAP can’t give advice on how to configure the external system nor does SAP provide support related to this system.

**Database Details**


<table>
<tr>
<td valign="top">

Database Provider

</td>
<td valign="top" colspan="2">

Postgres

</td>
</tr>
<tr>
<td valign="top">

Infrastructure

</td>
<td valign="top" colspan="2">

On-Premise

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
> Connectivity to Postgres service instance of Business Technology Platform \(Cloud Foundry environment\) is not supported.

