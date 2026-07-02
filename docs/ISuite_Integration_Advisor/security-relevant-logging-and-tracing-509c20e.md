<!-- loio509c20e2a974484d8537e37b65634838 -->

# Security-Relevant Logging and Tracing

Audit logs allow administrators at SAP or the tenant administrator to monitor events such as data read accesses or system configuration changes. This enables administrators to take adequate measures to prevent malicious usage of the system.

A tenant administrator can request audit logs for his or her tenant using the Monitoring application of the Web UI \(under Access Logs in the Audit Log and System Log Files tile\).

The Audit Log section allows you to monitor changes to the tenant data. For example, deletion of message implementation guidelines and mapping guidelines

An audit log records the following type of information for each logged event:

-   Type of the event

-   Date and time of the event

-   Initiator of the event \(user\)

-   Source of the event \(IP address of the source that issued the action\)


To view audit logs, the tenant administrator needs to have assigned the roles `IntegrationOperationServer.read` and `AuditLog.Read`.

