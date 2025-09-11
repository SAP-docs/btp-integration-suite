<!-- loiob16cf858de0340e4ba6186506bd686ea -->

# Best Practices

Optimize the Cloud Integration processes by applying best practices for data download and upload, with a specific focus on configurations, integration content, and data monitoring.



<a name="loiob16cf858de0340e4ba6186506bd686ea__section_tq1_1n3_fgc"/>

## Backup of Integration Content \(Design Time\)

Integration content refers to the various integration flows, mappings, and configurations that are designed in the SAP Cloud Integration system. It is important to regularly backup this content to prevent data loss. See [Backup and Restore Your Integration Artifacts](50-Development/backup-and-restore-your-integration-artifacts-bd280ef.md) and [Exporting Integration Packages](50-Development/exporting-integration-packages-95c0299.md)

> ### Note:  
> You can automate the export process using the SAP Cloud Integration API to export and backup integration content.



<a name="loiob16cf858de0340e4ba6186506bd686ea__section_rtw_mn3_fgc"/>

## Data Export of Message Data \(Runtime\)

SAP Cloud Integration stores runtime data for monitoring and logging purposes, such as message processing logs and error handling. This data is typically retained in the system for a limited period, and long-term storage might require backup.

You can manually download message logs and processing information from the Monitor view. To do so:

1.  Navigate to *Monitor* \> *Integrations and APIs* \> *Monitor Message Processing*.
2.  Search for the messages based on time or other filtering criteria. See [Using IDs to Filter Messages](50-Development/using-ids-to-filter-messages-a820752.md) and [Using Additional Filter Criteria](50-Development/using-additional-filter-criteria-6891f9e.md)

3.  Scroll down to the *Logs* section, and choose *Open Text View*.

4.  Choose *Download* to download the logs or atachments.

    > ### Note:  
    > For long-term storage of message data, SAP recommends using **SAP Solution Manager** or other monitoring tools to archive messages or integrate with external systems.




<a name="loiob16cf858de0340e4ba6186506bd686ea__section_mc5_153_fgc"/>

## Restore Data

In SAP Cloud Integration, you can download the integration content by re-importing the previously exported content. Similarly, if you need to restore specific configurations or integration flows:

-   Reinstate Integration Content: You can reinstate integration content by re-importing the previously exported content. See [Backup and Restore Your Integration Artifacts](50-Development/backup-and-restore-your-integration-artifacts-bd280ef.md)
-   Reinstate Message Data: Message data \(runtime\) cannot be directly reinstated to the system. However, in case of an error or business disruption, you can use the downloaded message logs to manually reprocess or trigger manual actions to restore system behaviour.




<a name="loiob16cf858de0340e4ba6186506bd686ea__section_yc2_r53_fgc"/>

## Backup for Security Configurations

Security settings like certificates, keystores, and credentials can be downloaded as a local copy separately to avoid disruptions in case of system migration or failures.

You can manually download and store keystores and certificates securely, as they are critical for secure communication between systems.

See:

-   [Downloading a Keystore](50-Development/downloading-a-keystore-c6b910b.md)
-   [Downloading Single Keystore Entries](50-Development/downloading-single-keystore-entries-ca8a663.md)
-   [Backing Up Keystore Entries](50-Development/backing-up-keystore-entries-b8e03b7.md)
-   [Restoring Backed-Up Keystore Entries](50-Development/restoring-backed-up-keystore-entries-bfbbf91.md)
-   [Downloading Backed-Up Keystore Entries](50-Development/downloading-backed-up-keystore-entries-3a67f8a.md)

