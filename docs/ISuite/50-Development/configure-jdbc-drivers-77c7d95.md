<!-- loio77c7d9550e12494eb600ec82496ef215 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure JDBC Drivers

Learn how to upload and deploy JDBC type-4 compliant third-party drivers on SAP Integration Suite.

JDBC connectivity provides a mechanism for integration flows deployed on SAP Integration Suite tenants to connect with Amazon RDS \(SQL Server and Oracle\) and HANA-aaS databases hosted on AWS using JDBC drivers. The tenant administrator configures JDBC drivers to enable you to establish connection to a database managed by a third-party vendor. Your database vendor should provide the driver or download it from their official website. We highly recommend that you work with the latest version of the third-party JDBC driver. All uploaded drivers undergo a security validation before being deployed on a tenant.

> ### Note:  
> Cloud Services may include features that permit third-party code or tools to be downloaded/uploaded into Customer’s Cloud Service account by \(i\) Customer or \(ii\) by SAP on behalf of and at the request of Customer from a non-SAP service for which Customer has a license, to facilitate the exchange of data or enable or improve other data processing activities. Such third-party code or tools are Customer Data. The code or tools may not be used to connect the Cloud Service or other software/cloud services to a third-party database licensed from SAP under a run-time license for use with specified SAP Applications. Customer must license a full-use license from the applicable database vendor to use such code or tools to replicate data from such database into the Cloud Service.
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Driver Name
> 
> </th>
> <th valign="top">
> 
> Supported Versions
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> [Microsoft JDBC Driver for SQL Server](https://learn.microsoft.com/en-us/sql/connect/jdbc/release-notes-for-the-jdbc-driver?view=sql-server-ver15#82) 
> 
> </td>
> <td valign="top">
> 
> -   [msSQLDriver12.4.0](https://repo1.maven.org/maven2/com/microsoft/sqlserver/mssql-jdbc/12.4.0.jre8)
> -   [msSQLDriver11.2.3](https://repo1.maven.org/maven2/com/microsoft/sqlserver/mssql-jdbc/11.2.3.jre8)
> -   [msSQLDriver8.2.2](https://repo1.maven.org/maven2/com/microsoft/sqlserver/mssql-jdbc/8.2.2.jre8/)
> 
> -   [msSQLDriver8.4.1](https://repo1.maven.org/maven2/com/microsoft/sqlserver/mssql-jdbc/8.4.1.jre8/)
> 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> [Oracle JDBC Driver](https://www.oracle.com/database/technologies/appdev/jdbc-downloads.html)
> 
> </td>
> <td valign="top">
> 
> -   [oracleDB11.2.0.4](https://repo1.maven.org/maven2/com/oracle/database/jdbc/ojdbc6/)
> 
> -   [oracleDB12.2.0.1](https://repo1.maven.org/maven2/com/oracle/database/jdbc/ojdbc8/12.2.0.1/)
> 
> -   [oracleDB19.11.0.0](https://repo1.maven.org/maven2/com/oracle/database/jdbc/ojdbc8/19.11.0.0/)
> 
> -   [oracleDB19.16.0.0](https://repo1.maven.org/maven2/com/oracle/database/jdbc/ojdbc8/19.16.0.0/)
> 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> IBM DB2 JDBC Driver
> 
> </td>
> <td valign="top">
> 
> -   [db2Driver11.5.4](https://www.ibm.com/support/pages/node/6241980)
> 
> -   [db2Driver11.5.5](https://www.ibm.com/support/pages/node/6438025)
> 
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> [MariaDB Connector](https://www.mariadb.com/docs/server/release-notes/mariadb-connector-j-3-3/3-3-3/) 
> 
> </td>
> <td valign="top">
> 
> [mariadb-connector-j-3.3.3](https://dlm.mariadb.com/browse/java8_connector/293/1970/) 
> 
> </td>
> </tr>
> </table>

You can create Amazon Relational Database Service \(Amazon RDS\) based data source that supports the following database engines:

-   Microsoft SQL Server

-   Oracle


Before consuming the drivers in runtime, you must deploy the uploaded driver as a data source to establish a connection with above mentioned databases. For more information on deploying a data source, see [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).



<a name="loio77c7d9550e12494eb600ec82496ef215__section_h2l_l4l_cfb"/>

## Deploying JDBC Drivers

1.  If you have activated Edge Integration Cell, select the target runtime where you want to deploy the JDBC driver.

2.  Choose the *JDBC Driver* tab, and then choose *Add* for uploading a driver from your file system.

3.  Specify the following attributes:

    **Driver-Specific Parameters**


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Database Type*
    
    </td>
    <td valign="top">
    
    Select one of the database types that are supported:

    -   Microsoft SQL Server

    -   Oracle

    -   DB2

    -   MariaDB


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *JDBC Driver File*
    
    </td>
    <td valign="top">
    
    Browse to choose the driver file from your file system.

    > ### Note:  
    > Only JAR \(\*.jar\) file formats are supported.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Runtime*
    
    </td>
    <td valign="top">
    
    Selected runtime is displayed.
    
    </td>
    </tr>
    </table>
    
4.  Deploy the driver.




<a name="loio77c7d9550e12494eb600ec82496ef215__section_igy_brm_cfb"/>

## Quick Actions


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

:gear:

</td>
<td valign="top">

Helps to sort and filter the content of the table. You can define how the table entries are to be sorted \(in ascending or descending order\). You can also filter the table entries for certain attributes.

</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons-V5"></span> \(Reload\)

</td>
<td valign="top">

Reloads the table content.

</td>
</tr>
</table>

