<!-- loio435ec6196a9f4007910b69bcab90937a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Scenario Evaluation Request

Assess your integration scenarios using the information from data extraction requests.



<a name="loio435ec6196a9f4007910b69bcab90937a__prereq_u4c_zyg_k5b"/>

## Prerequisites

You've created at least one data extraction request as described in [Create a Data Extraction Request](create-a-data-extraction-request-ce0ad0e.md).

> ### Note:  
> Data extraction requests may occasionally become outdated due to the implementation of new rules. To fully benefit from these updates, you may need to perform a new data extraction before conducting a scenario evaluation, as previous extractions may not encompass the latest rule sets.

> ### Tip:  
> Do you prefer hands-on instructions? Check out the tutorial [Use the Migration Assessment Application](https://developers.sap.com/tutorials/migration-assessment.html).



## Procedure

1.  In the Migration Assessment application, navigate to *Request* \> *Scenario Evaluation*.

2.  Choose *Create*.

3.  Enter a *Request Name* and choose a *Data Extraction Request* you executed previously.

4.  For this specific run of your scenario evaluation, enter an *Evaluation Run Name* and a *Description*.

    You can start a new evaluation run anytime, for example, for the purpose of comparing new and old data.

5.  Choose *Create*.

    The new request appears in the list of scenario evaluation requests and the evaluation is run.

6.  The following additional *Actions* can be performed for a scenario evaluation request:

    -   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Open Dashboard*: Access and download an analysis of your scenario evaluation runs with details specific to your integration scenarios, for example, adapters,modernization recommendations, and an overview of the rules used in the evaluation. You can switch between the data of all runs performed for the scenario evaluation request so far.

        For more information, see [Modernization Recommendations](https://help.sap.com/docs/help/90c8ad90cb684ee5979856093efe7462/d337a6f0d324405f9ef0c410fd0d3739.html). Be aware that depending on your data and the current ruleset, you might not receive any recommendations.

    -   <span style="color:#346187;"><span class="SAP-icons-V5"></span></span> *Trigger Analysis*: Schedule a new evaluation run based on current data.

    -   Create a report to access the latest evaluation run details by using one of the following two options:

        -   <span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span> *Export*: Use this option to download an in-depth analysis report. This option lists all integration scenarios that were part of the request. It includes comprehensive details necessary for migration, such as:
            -   Migration assessment category and effort estimation
            -   Modernization recommendations
            -   Rules applied to the integration scenarios
            -   Sender and receiver adapters \(both standard and custom\)
            -   Request and response message types
            -   Message throughput and mappings usage
            -   Performance data: Message size and processing time

        -   <span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span> *Generate Report*: Select this option to download a summarized overview of the evaluation, which includes the following:
            -   A summary of the evaluation with charts and tables as visual aids
            -   Number of integration scenarios per category, size, modernization recommendation, etc.
            -   The top 10 most active scenarios in terms of processed messages
            -   Standard adapter usage
            -   Migration effort estimation
            -   Modernization recommendations for your scenarios

                > ### Note:  
                > Custom adapters details are only included in the *Export* file.




    ![Screenshot of the Scenario Evaluation interface. It shows the options to download the details on the latest evaluation run either as an Excel file withExportor as a PDF file with Generate Report. These options are displayed after navigating to Additional Options on the respective scenario evaluation listed item.](images/PIMAS_scenarioevaluation_additionaloptions_39d256b.png)


