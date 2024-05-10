<!-- loiob927e0182df04208ace0f15c66073317 -->

# Archiving Payload Data

Archive your sender and receiver interchange payloads.

The feature *Archive Payload Data* allows you to archive your interchange payloads to backend CMIS system. This is how it works:

-   Each tenant will have one B2B archiving job assigned to it. The initial status of the job would be set to inactive.

-   To activate this, you need to enable the checkbox *Archive Payload Data* provided in your agreement for the sender/receiver interchange step under *B2B Scenarios* tab.
-   The archiving job will be executed once a day and the status of the archiving job can be monitored in the *Monitor* tab.
-   Each archived interchange will be compressed to one zip file with the naming convention `Business_Document_Data_Content<Interchange ID>.zip`.
-   The archiving job, once activated will archive the payload data upto 7 days before the date of activation. Other payload data created before this time period will not be archived.
-   Each archived interchange is sent to CMIS system in one transaction.
-   There is no retry mechanism for the failed archived interchanges. These interchanges have to wait for the next archiving schedule job execution.
-   Once the archiving job is completed, you need to check your CMIS system to check the archived data as the tenant does not display this information.
-   The archiving feature is supported by the generic integration flow from version 2.3.0 and above.
-   Once the interchange arhive is completed, the monitor backend database will store the data for 90 days post which the data will be deleted automatically. To monitor the archiving status, see [Monitoring B2B Messages](monitoring-b2b-messages-b5e1fc9.md)

.

