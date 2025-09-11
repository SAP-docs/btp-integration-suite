<!-- loiob48c40b3df8f441a879370d76dc0d8f3 -->

# Backup and Restore

Backup and restore procedures are crucial for ensuring data integrity and business continuity in Cloud Integration capability of SAP Integration Suite. While Cloud Integration offers robust features for handling integration flows and messages, backup and restore are typically managed by SAP as part of the service.

SAP automatically backs up all the tenant-specific data, and it's all stored securely in a secondary location with support to restore it in the event of any data loss. The backups are scheduled to be executed at regular intervals to reduce the chance and impact of data loss, thereby reducing overall downtime.



<a name="loiob48c40b3df8f441a879370d76dc0d8f3__section_ikg_yk3_fgc"/>

## Backup Services

All the data that’s being backed up is safeguarded by following set of qualities that guarantee a secure backup and facilitate data restoration with minimal loss:

-   Full backup: All necessary data is backed up daily.
-   Incremental backup: All delta updates within a day are backed up every 15 mins.
-   Data Storage: Each set of backup data is stored in secondary storage for up to 14 days.
-   Data Security: Every backup data stored is encrypted by default with the standard encryption mechanism.
-   Recovery Options: Point in time recovery is supported.



<a name="loiob48c40b3df8f441a879370d76dc0d8f3__section_cgt_fl3_fgc"/>

## Backup Exceptions

Certain configurations from Cloud Integration tenant are not backed up, including:

-   BTP sub-account configurations.
-   Cloud Connector settings for the BTP sub-account.
-   User access settings related to User Management and Authorizations at the sub-account level.
-   Integration destinations set up at the sub-account level.
-   Message queues and the messages stored within them.



<a name="loiob48c40b3df8f441a879370d76dc0d8f3__section_izg_ml3_fgc"/>

## Operational Details

-   Restore as an option is not available as a self-service for customers, and it’s provided as a service based on requests only.
-   Restore is only available in an emergency to mitigate risks from logical errors, such as data corruption and other irreparable situations.
-   SAP performs daily backup replication to a remote data centre within the same region. These data backups can be restored in the primary data centre.
-   Appropriate processes and automated tools are in place to validate backup integrity, and backup logs are reviewed daily to detect and correct backup failures.
-   Customers can restore the data of the productive and non-productive systems to any point in time within the backup cycle.

To request a data restoration in any of these cases, create a [ticket](http://support.sap.com) using the component LOD-HCI-PI-OPS.



<a name="loiob48c40b3df8f441a879370d76dc0d8f3__section_vcc_dwp_fgc"/>

## Known Limitations

The following scenarios do not support data restoration:

-   Restoration of tenant data older than 14 days.
-   Tenant replication for copying data between tenants.
-   Data migration between different tenant environments, such as test and production.

**Related Information**  


[Cloud Integration](cloud-integration-a33f27b.md "Cloud Integration allows you to build and run integration flows across cloud, on-premise, and hybrid landscapes for application-to-application (A2A), business-to-business (B2B), and business-to-government (B2G) scenarios.")

