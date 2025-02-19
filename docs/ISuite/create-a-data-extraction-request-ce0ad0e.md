<!-- loioce0ad0e1ef4546acbb6604dd0245ad39 -->

# Create a Data Extraction Request

Retrieve data from your system of choice using a data extraction request.



<a name="loioce0ad0e1ef4546acbb6604dd0245ad39__prereq_tbh_qkg_k5b"/>

## Prerequisites

You've configured a source system as described in [Add an SAP Process Orchestration System](add-an-sap-process-orchestration-system-5f76723.md).

> ### Note:  
> Do you prefer hands-on instructions? Check out the tutorial [Use the Migration Assessment Application](https://developers.sap.com/tutorials/migration-assessment.html).

> ### Restriction:  
> The total physical disk storage is limited. As each extraction consumes physical disk storage, future extractions can fail with an error message once the limit is reached.
> 
> Before extracting new data, make sure that enough storage space is available. If you've reached the limit, free up space by deleting old extractions.



## Procedure

1.  In the Migration Assessment application, navigate to *Request* \> *Data Extraction*.

2.  Choose *Create*.

3.  Enter a *Request Name* and select the *System* you want to connect to.

4.  Choose one of the following options:

    -   *Complete Extraction*: You want to extract **all integration scenarios** from the selected system.

        Continue with step 5.

    -   *Custom Extraction*: You want to extract **a subset of integration scenarios** from the selected system. Use this option, for example, if you want to exclude specific integration scenarios or only need to extract a small selection.

        In the list of integration scenarios that were retrieved from the system, all are selected by default. Customize the list by deselecting and selecting integration scenarios to fit your needs. You can use the search function to find specific integration scenarios.

        ![When creating a new data extraction, you can choose between Complete Extraction and Custom Extraction. If you choose Custom Extraction, a list of all integration scenarios available in the selected system is retrieved. Select and deselect integration scenarios in this list to customize the selection of integration scenarios you want to extract.](images/IntegrationSuite_PIMAS_Request_DataExtraction_CustomExtraction_87f8c8d.png)


5.  Choose *Create*.

    The data extraction starts. Once the extraction finishes, the new request appears in the list of data extraction requests with the status *Completed*.

    If the extraction has the status *Completed with warnings* or *Completed with errors*, open the extraction log and review the warnings and errors. Fix errors in your local SAP Process Orchestration system, otherwise they're not included in any scenario evaluations of this data extraction. Once you've fixed the errors, you must create a new data extraction.

6.  Choose *Log* to view the data extraction log, which provides you with details about the data extraction.




<a name="loioce0ad0e1ef4546acbb6604dd0245ad39__postreq_rq2_t1g_k5b"/>

## Next Steps

After extracting the necessary data from your system, you can assess the integration scenarios associated with your data using scenario evaluation requests. See [Create a Scenario Evaluation Request](create-a-scenario-evaluation-request-435ec61.md).

> ### Note:  
> Data extraction requests may occasionally become outdated due to the implementation of new rules. To fully benefit from these updates, you may need to perform a new data extraction before conducting a scenario evaluation, as previous extractions may not encompass the latest rule sets.

