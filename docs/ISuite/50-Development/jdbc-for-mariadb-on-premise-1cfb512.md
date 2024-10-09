<!-- loio1cfb5124d5364617af4c6523af9c8c70 -->

# JDBC for MariaDB \(On-Premise\)

JDBC receiver adapter supports connectivity to MariaDB On-Premise database only if the integration scenarios are processed in an [Edge Integration Cell](../setting-up-and-managing-edge-integration-cell-8f7abc2.md) runtime location.

> ### Note:  
> This adapter enables you to connect Cloud Integration to a remote database system. SAP can’t give advice on how to configure the external system nor does SAP provide support related to this system.

**Database Details**


<table>
<tr>
<td valign="top">

Database Provider

</td>
<td valign="top">

MariaDB plc

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

jdbc:mariadb://<host\>:<port\>/<database\_name\>:property1=value1;property2=value2;...

</td>
</tr>
<tr>
<td valign="top">

JDBC URL Example

</td>
<td valign="top">

jdbc:mariadb://mymariadb:1234/TEST\_1

</td>
</tr>
</table>

> ### Note:  
> Stored procedure exceution is not supported for this database.

Before connecting to this database, you must upload the drivers and then, add the Data Source. For more details, see [Configure JDBC Drivers](configure-jdbc-drivers-77c7d95.md) and [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

> ### Note:  
> This documentation doesn’t provide further advice on how to configure the connected database system. Check out the corresponding documentation for more details.

