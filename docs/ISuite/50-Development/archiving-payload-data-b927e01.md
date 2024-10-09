<!-- loiob927e0182df04208ace0f15c66073317 -->

# Archiving Payload Data

Archive your sender and receiver interchange payloads.

The feature *Archive Sender/Receiver Payload Data* allows you to archive your interchange payloads to backend CMIS system. This is how it works:

-   Each tenant will have one B2B archiving job assigned to it. The initial status of the job would be set to inactive.

-   To activate this, follow the steps mentioned below:
    -   Send a **POST** call to the URL: `https://path-to-odata-api/api/v1/activateB2BArchivingConfiguration` where `path-to-odata-api` is specific to the user's environment.

    -   This call is sent to enable the archiving function. If successful, the call returns a 200 response code with a message stating the activation was successful. You can then enable the checkbox *Archive Sender Payload*/*Archive Receiver Payload* field provided in your agreement for the sender/receiver interchange respectively under *B2B Scenarios* tab.
    -   To check whether archiving is currently configured on a tenant, use the OData API that allows you to query the message processing logs. You can do this by sending a **GET** call to te URL: `https://path-to-odata-api/api/v1/B2BArchivingConfigurations('tenant-name')` where `path-to-odata-api` is specific to the user's environment.

-   The archiving job will be executed once a day and the status of the archiving job can be monitored in the *Monitor* tab. You can also check the overall status of an archiving schedule job execution by calling the KPI OData API `https://path-to-odata-api/api/v1/B2BArchivingKeyPerformanceIndicators` where `path-to-odata-api` is specific to your environment.
-   Each archived interchange will be compressed to one zip file with the naming convention `Business_Document_Data_Content<Interchange ID>.zip`.
-   The archiving job, once activated will archive the payload data upto 7 days before the date of activation. Other payload data created before this time period will not be archived.
-   Each archived interchange is sent to CMIS system in one transaction.
-   There is no retry mechanism for the failed archived interchanges. These interchanges have to wait for the next archiving schedule job execution.
-   Once the archiving job is completed, you need to check your CMIS system to check the archived data as the tenant does not display this information.
-   The archiving feature is supported by the generic integration flow from version 2.3.0 and above.
-   Once the interchange arhive is completed, the monitor backend database will store the data for 90 days post which the data will be deleted automatically. To monitor the archiving status, see [Update Agreements](update-agreements-b5e1fc9.md)

.

