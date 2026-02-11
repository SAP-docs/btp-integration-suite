<!-- loioffad2f97af6947168c5fe3cf86fe433a -->

# Update Activity Parameters

Update the activity parameters configuration by reading the latest parameter values from both the company \(including subsidiaries\) profile and the trading partner profile, and then applying these values to the agreement.



## Context

In the *Cross Actions* tab, you can modify properties of a group of agreements. For example, you can configure the activity parameters by performing the following procedure.

Note that the update action skips profile parameters that were previously assigned to an agreement activity and no longer exist in the profile \(for example, it has been deleted\). The parameter and its original value then remain unchanged in the agreement activity.

When updating an activity, the following applies to the **task status**:

-   If all profile parameters assigned to the activity still exist and are successfully updated, the task status is *Completed*.
-   If one or more parameters assigned to the activity can't be found in the profile, the task status is *Warning*.

Once the mass update job finishes, the following applies to the **overall job status**:

-   If all its tasks have the status *Completed*, the overall job status is *Completed*.
-   If at least one task has the status *Warning*, the overall job status is *Warning*.



## Procedure

1.  In your application, go to *Design* \> *B2B Scenarios*.

2.  In the *Cross Actions*, choose *Update Agreements*.

3.  Choose *Update Properties* and provide the following information:

    1.  Enter a meaningful *Action Name*.

    2.  For the *Update Property*, select *Activity Parameters*.

    3.  Enter a meaningful *Description*.

    4.  Finish by choosing *Create*. The new update property opens in a wizard.


4.  In the first wizard step *Select Agreements*, you can select the agreements for which you want to update the activity parameters. Use the filters to retrieve a list of agreements from the relevant type system and choose *Go*.

    To view all agreements existing in the system, choose *Go* without maintaining any filters.

    The search results are displayed in the *Agreements* table.

5.  From the list of agreements, select the relevant agreements and choose *Next*.

6.  In the step *Update Type System Version*, select the *Target Type System Version*. Choose *Next*.

7.  The final *Review* step displays a summary of the previous steps. Confirm or edit the modifications, then complete the update by choosing *Finish*.

8.  To review the progress of your newly created task, open it in the *Actions Logs* table.


**Related Information**  


[Update Properties](update-properties-ba066bb.md "Update the properties in your agreements.")

