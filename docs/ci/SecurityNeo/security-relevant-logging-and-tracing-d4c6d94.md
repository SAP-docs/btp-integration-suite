<!-- loiod4c6d9446ed7403482138035dd7dc2ed -->

# Security-Relevant Logging and Tracing

Audit logs allow administrators at SAP or the tenant administrator to monitor events such as data read accesses or system configuration changes. This enables administrators to take adequate measures to prevent malicious usage of the system.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.



A tenant administrator can display system access logs for his or her tenant using the *Monitoring* application of the Web UI \(under *Access Logs* in the *Audit Log* and *System Log Files* tile\).

The *Audit Log* section allows you to monitor changes to the configuration of the tenant cluster such as \(examples\):

-   Access to the system \(for example, read access to message content\)

-   Deletion of data from the message store

-   Change in the content of a keystore


An audit log records the following type of information for each logged event:

-   Type of the event

-   Date and time of the event

-   Initiator of the event \(user\)

-   Source of the event \(IP address of the source that issued the action\)


To view audit logs, the tenant administrator needs to have assigned the roles `IntegrationOperationServer.read` and `AuditLog.Read`.

The audit log data retention time in the database is 30 days.

The *System Log Files* section provides information related to errors that occurred during HTTP inbound processing and contains 2 different log types: the **HTTP Access Logs**and the **Worker Nodes Default Traces**.

-   For both log types, the access is granted through personas or composite roles such as \(`IntegrationDeveloper`, `Administrator`,`BusinessExpert`, `ReadOnly`, `SystemDeveloper`\). They all can open the log files as the composite roles always contain the single role `IntegrationOperationServer.read`. You need this role to download logs.

-   Retention time for both logs is 7 days. After that period, the log files are deleted.

**Stored information**

The information stored depends on the log type.

For the **HTTP Access Logs**, the system stores information about the incoming HTTP request on the worker node, such as:

-   The incoming time of the call

-   The IP address of the sender client
-   The User Id, if included in the request
-   The HTTP method \(`HEAD`, `POST`, `PUT`, `GET`, `DELETE`\)
-   The call path such as e.g. `/cxf/SOD/incoming` 
-   The HTTP status code \(e.g. 200, 401, 403, 500\)
-   The call size in bytes
-   The duration of the call.

This information is stored to be able to identify authentication or authorization problems arising in an early message processing phase, since no Message Processing Log Entries are logged yet. It is used by integration developers or administrators for trouble-shooting and/or configuration purposes.

The **Default Trace** contains general information about system activities according to the log level you have set.

In case of the default settings, errors and stack traces are logged. The default trace format is :

-   Log entry time stamp

-   Log level \(*ERROR, INFO, WARNING, DEBUG*,...\)
-   Class name of the logger
-   Tenant
-   Log text

This information is stored for trouble-shooting purposes, for example if an component monitor throws an error message during deployment of the corresponding integration flow and this error message does contain enough details. In this case the developer or the administrator might have a look into the *Worker Nodes Default Traces*.



> ### Note:  
> Audit logs managed by SAP
> 
> Audit logs are also generated SAP-internally and displayed for people with dedicated permissions. Such audit logs are generated for all virtual machines \(nodes\) of the customer's tenant clusters as well as for the load balancer. These logs can cover events such as:
> 
> -   Access to the system \(for example, read access to message content\)
> 
> -   Change to the setup of a tenant cluster \(for example, if VM has been started or stopped\)
> 
> -   Change to the configuration \(for example, an integration flow has been deployed or undeployed\)
> 
> -   Change of the tenant configuration
> 
> 
> Audit logs related to different customers are separated from each other \(according to the tenant isolation feature\).

