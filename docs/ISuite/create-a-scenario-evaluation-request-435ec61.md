<!-- loio435ec6196a9f4007910b69bcab90937a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Scenario Evaluation Request

Assess your integration scenarios using the information from data extraction requests.



<a name="loio435ec6196a9f4007910b69bcab90937a__prereq_u4c_zyg_k5b"/>

## Prerequisites

You've created at least one data extraction request as described in [Create a Data Extraction Request](create-a-data-extraction-request-ce0ad0e.md).

> ### Note:  
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

    -   <span style="font-size:16px;"><span style="color:#346187;"><span class="SAP-icons-V5"></span></span></span> *Download*: Download details about the latest evaluation run in one of two formats:

        -   The option *as .xlsx file* lists all integration scenarios that were part of the request. It includes details such as migration effort, migration status, modernization recommendations, and the rules applied to the integration scenarios during the evaluation. For more information, see [Modernization Recommendations](https://help.sap.com/docs/help/90c8ad90cb684ee5979856093efe7462/d337a6f0d324405f9ef0c410fd0d3739.html). 
        -   The option *as .pdf file* features the previously mentioned details about the integration scenarios while also providing a written summary of adapters and the assessment in general, with charts and tables as visual aids. It also features a section on modernization recommendations for your scenarios. This file is suited as a summarizing report, for example, for management.


    ![Screenshot of the Scenario Evaluation interface. It shows the options to download the details on the latest evaluation run either As .xlsx fileor As .pdf file. These options are displayed after navigating through Additional Options \> Download on the respective scenario evaluation listed item.](images/IntegrationSuite_PIMAS_Request_ScenarioEvaluation_Download_d394c4f.png)


