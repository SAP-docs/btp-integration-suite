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

A state that designates if issues occurred during a data extraction that could impact the scenario evaluation. The followings extraction statuses exist:

-   *Completed*: Your data was extracted without issues and is ready for evaluation.

-   *Completed with warnings*: Parts of your data weren't extracted correctly, but can still be evaluated. For details, see the extraction log.

-   *Completed with errors*: Parts of your data weren't extracted and can't be evaluated. If you trigger a scenario evaluation for this data extraction, it leaves out the erroneous data. You can fix the issues described in the extraction log in your SAP Process Orchestration system and create a new data extraction afterwards.




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

A process during which the application uses predefined rules to evaluate the data gathered in a previous data extraction regarding the following factors: if the extracted integration scenarios can be migrated, the expected effort of this migration, and what migration templates can be used.

</td>
</tr>
</table>

