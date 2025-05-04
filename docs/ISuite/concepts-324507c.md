<!-- loio324507c7c50c45afb822ae5e95af6a9c -->

# Concepts

Get to know the most important concepts used in Migration Assessment.


<table>
<tr>
<th valign="top">

Concept

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Assessment categories

</td>
<td valign="top">

A classification that indicates if your integration scenarios are ready to be migrated to SAP Integration Suite and how you can proceed.

-   **Ready to migrate**: These integration scenarios match to the scenarios offered in SAP Integration Suite. They can be moved to SAP Integration Suite manually or semi-automatically. Additional configuration steps might be required.
-   **Adjustment required**: These integration scenarios partially match to the scenarios offered in SAP Integration Suite. They can be moved to SAP Integration Suite manually or semi-automatically. Further adjustments to the end-to-end integration process based on best practices are required.
-   **Evaluation required**: For these integration scenarios, some items require further evaluation before the scenario can be moved to SAP Integration Suite.



</td>
</tr>
<tr>
<td valign="top">

Data extraction

</td>
<td valign="top">

A process during which the application gathers data, for example, integration scenarios, from a connected on-premise system and prepares the data for assessment.

A data extraction can contain the following data:

-   from the Integration Directory: integration scenarios, communication channels, sender agreements, receiver agreements, alert rules, value mappings
-   from the Enterprise Services Repository: operation mappings, message mappings, service interfaces
-   from Monitoring: processed messages from the message monitor



</td>
</tr>
<tr>
<td valign="top">

Extraction status

</td>
<td valign="top">

A state that designates if issues occurred during a data extraction that could impact the scenario evaluation. The following extraction statuses exist:

-   *Extracted*: Your data was extracted without issues and is ready for evaluation.

-   *Extracted with warnings*: Parts of your data weren't extracted correctly, but can still be evaluated. For details, see the extraction log.

-   *Extracted with errors*: Parts of your data weren't extracted and can't be evaluated. If you trigger a scenario evaluation for this data extraction, it leaves out the erroneous data. You can fix the issues described in the extraction log in your SAP Process Orchestration system and create a new data extraction afterwards.




</td>
</tr>
<tr>
<td valign="top">

Modernization recommendation

</td>
<td valign="top">

A suggestion aimed at improving your integration practices, for example, regarding scalability, maintenance, flexibility, and responsiveness. The modernization recommendations often include transitioning from custom legacy content to predelivered packages or modern integration styles, as well as open and standardized protocols like SOAP, REST, and OData. For a list of all recommendations, see [Modernization Recommendations](https://help.sap.com/docs/help/90c8ad90cb684ee5979856093efe7462/d337a6f0d324405f9ef0c410fd0d3739.html).

Once you've completed a scenario evaluation, you can find the modernization recommendations for your scenarios in the downloadable reports or the dashboard. Be aware that based on your data and the current ruleset of the application, you might not receive any modernization recommendations. See [Create a Scenario Evaluation Request](create-a-scenario-evaluation-request-435ec61.md).

</td>
</tr>
<tr>
<td valign="top">

Rule

</td>
<td valign="top">

A set of characteristics according to which the application evaluates whether an integration scenario can be migrated and what effort you can expect.

A rule consists of multiple parameters, each of which has a certain weight assigned to them. Based on these weights, the application calculates the estimated effort, which means that some parameters, and therefore rules, have a bigger influence on the final estimation than others.

</td>
</tr>
<tr>
<td valign="top">

Scenario evaluation

</td>
<td valign="top">

A process during which the application uses predefined rules to evaluate the data gathered in a previous data extraction. It analyses whether the extracted integration scenarios can be migrated and the migration effort you can expect.

</td>
</tr>
</table>

