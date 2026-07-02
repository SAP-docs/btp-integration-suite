<!-- loioe6db38ab14ac480ab171b51932a481f5 -->

# JDBC for Oracle \(On-Premise\)

JDBC receiver adapter supports Oracle On-Premise database provided by Oracle.

> ### Note:  
> This adapter enables you to connect to a remote database system. SAP can’t give advice on how to configure the external system nor does SAP provide support related to this system.

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

Neo and Cloud Foundry

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

> ### Note:  
> When using Oracle Database with:
> 
> -   For JDBC access, the Oracle database must be licensed directly from Oracle with a Full-Use license.
> -   If the Oracle database is licensed through SAP with an Application-Specific Full Use license, JDBC access is**not covered** by SAP’s Oracle reseller license. See SAP note [581312](https://me.sap.com/notes/581312)

Before connecting to this database, you must upload the drivers and then, add the Data Source. For more details, see [Configure JDBC Drivers](../Operations/configure-jdbc-drivers-77c7d95.md) and [Managing JDBC Data Sources](../Operations/managing-jdbc-data-sources-4c873fa.md)

> ### Note:  
> Oracle RAC setup is not supported for the *Cloud Integration* runtime profile, including both Neo and Cloud Foundry environments.

**Related Information**  


[JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md "The JDBC (Java Database Connectivity) adapter enables you to connect SAP Cloud Integration to cloud or on-premise databases.")

