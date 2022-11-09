<!-- loiof86818219a954c829bd847e323ecb23d -->

# JDBC for Oracle \(Cloud\)

JDBC receiver adapter supports Oracle cloud database provided by Amazon RDS.

**Database Details**


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

`jdbc:oracle:thin:<user>/<password>@<database`

To connect to Oracle Database SID, use: `jdbc:oracle:thin:[<user>/<password>]@<host>[:<port>]:<SID>`



</td>
</tr>
<tr>
<td valign="top">

JDBC URL Example



</td>
<td valign="top">

`jdbc:oracle:thin:@myoracle:1521:my_sid`



</td>
</tr>
</table>

Before connecting to this database, you must upload the drivers and then, add the Data Source. For more details, see [Configure JDBC Drivers](configure-jdbc-drivers-77c7d95.md) and [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

**Related Information**  


[JDBC Receiver Adapter](jdbc-receiver-adapter-88be644.md "The JDBC (Java Database Connectivity) adapter enables you to connect Cloud Integration to cloud or on-premise databases.")

