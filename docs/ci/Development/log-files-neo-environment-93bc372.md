<!-- loio93bc3722533741c7a48eec6a8352f060 -->

# Log Files, Neo Environment

Access technical system logs written during message processing on the worker/runtime node.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

You can access the OData API at:

There, you find the basic operations.

[https://api.sap.com/api/LogFiles/](https://api.sap.com/api/LogFiles/)

This documentation provides additional information.



<a name="loio93bc3722533741c7a48eec6a8352f060__section_fkz_c3k_t4b"/>

## Permissions

To authorize an API client to access the OData API, perform the steps as described at:

In the **Neo** environment, perform the steps described at: [Setting Up Inbound HTTP Connections \(for API Clients\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-for-api-clients-neo-environment-fbae09c.md) 

Assign the following roles:

`IntegrationOperationServer.read`, `AuditLog.Read` \(see [Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md)\)



<a name="loio93bc3722533741c7a48eec6a8352f060__section_uvw_dlf_t4b"/>

## Resources

****


<table>
<tr>
<th valign="top">

Resource



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Log File Archives



</td>
<td valign="top">

Represents a log file.

Two kinds of log files are created during message processing:

-   HTTP access logs

    Contain information about inbound HTTP requests. You can use this information to analyze authentication and authorization errors for inbound HTTP communication.

-   Default trace logs

    Contain technical processing information.




</td>
</tr>
<tr>
<td valign="top">

Log Files



</td>
<td valign="top">

Represent a set of log files in a compressed file \(zip format\).



</td>
</tr>
</table>

> ### Note:  
> The property `NodeScope` identifies the node type associated with the log file.
> 
> For example, the following request returns a list of all HTTP access and default trace log files available for all runtime nodes \(*worker nodes*\) of the tenant cluster:
> 
> `https://<host address>/api/v1/LogFiles$filter=NodeScope eq 'worker'`
> 
> The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).
> 
> > ### Note:  
> > In future, this list probably contains log files from other node types. Therefore, we recommend the use of the variant with the `NodeScope` filter parameter, as it guarantees that only runtime nodes \(and no other node types\) are considered.

There's a user interface that allows you to access log files. Go to the *Monitor* application under *Access Logs* \(only in the Neo environment\).

More information: [Access Logs, Neo Environment](../Operations/access-logs-neo-environment-d5a4113.md)

For general information about query options, see [Query Options](query-options-99f4b70.md).



<a name="loio93bc3722533741c7a48eec6a8352f060__section_wsk_33x_54b"/>

## Example Requests

You find various example requests on SAP Business Accelerator Hub at [https://api.sap.com/api/LogFiles/](https://api.sap.com/api/LogFiles/).

For more example requests, see [Log Files Example Requests](log-files-example-requests-4e17410.md).



On SAP Business Accelerator Hub, you can test API calls against a sandbox tenant or against a custom tenant \(to be configured under *API Environment*\). If you want to perform an API call against your custom tenant using an HTTP client such like Postman, make sure that the request URL is composed in the following way:

`https://<host address>/api/v1/<relative resource path>`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

You can find the relative resource path for each operation on SAP Business Accelerator Hub.

**Related Information**  


[Log Files Example Requests](log-files-example-requests-4e17410.md "")

