<!-- loioce0ad0e1ef4546acbb6604dd0245ad39 -->

# Create a Data Extraction Request

Retrieve data from your system of choice using a data extraction request.



<a name="loioce0ad0e1ef4546acbb6604dd0245ad39__prereq_tbh_qkg_k5b"/>

## Prerequisites

You've configured a source system as described in [Add an SAP Process Orchestration System](add-an-sap-process-orchestration-system-5f76723.md).

> ### Note:  
> Do you prefer hands-on instructions? Check out the tutorial [Use the Migration Assessment Application](https://developers.sap.com/tutorials/migration-assessment.html).

> ### Note:  
> The following limitations apply when extracting data:
> 
> -   You can extract a maximum of 4000 integration scenarios.
> 
> -   The total physical disk storage of all extractions can't exceed 2 GB. As each extraction consumes physical disk storage, future extractions fail with an error message once the limit is reached.
> 
>     Make sure that enough storage space is available before you start an extraction request. If not, delete older extractions or contact support.



## Procedure

1.  In the Migration Assessment application, navigate to *Request* \> *Data Extraction*.

2.  Choose *Create*.

3.  Enter a *Request Name* and select the *System* you want to connect to.

4.  Choose *Create*.

    The data extraction starts. Once the extraction finishes, the new request appears in the list of data extraction requests with status *Completed*.

    If the extraction has status *Completed with warnings* or *Completed with errors*, open the extraction log and review the warnings and errors. Fix errors in your local SAP Process Orchestration system, otherwise they're not included in any scenario evaluations of this data extraction. Once you've fixed the errors, you must create a new data extraction.

5.  Choose *Log* to view the data extraction log, which provides you with details about the data extraction.




<a name="loioce0ad0e1ef4546acbb6604dd0245ad39__postreq_rq2_t1g_k5b"/>

## Next Steps

After extracting the necessary data from your system, you can assess the integration scenarios associated with your data using scenario evaluation requests. See [Create a Scenario Evaluation Request](create-a-scenario-evaluation-request-435ec61.md).

