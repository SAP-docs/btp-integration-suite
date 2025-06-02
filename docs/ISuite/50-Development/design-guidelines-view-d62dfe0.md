<!-- loiod62dfe018a44412db0de79175f052ff3 -->

# Design Guidelines View

Use this view to validate your integration flow against the design guidelines enabled by the integration leads of your organization.





### What Are Design Guidelines

Design guidelines are checks that help you design robust integration flows. Your tenant administrators or integration leads have enabled all or a subset of available design guidelines that they think are appropriate for your organization's business needs. For more information, see [Design Guidelines](IntegrationSettings/design-guidelines-4d1c84f.md).



### What Are The Implications

All integration flows designed in this tenant must abide by the enabled design guidelines.



### Validate Your Integration Flow

Run the design guidelines after you've designed your integration flow. Your integration flow must comply with all applicable design guidelines. Remember that not all enabled design guidelines are applicable for every integration flow that you create. The integration flow editor intelligently identifies the design guidelines that are applicable and validates the integration flow only against the applicable ones.

Follow these simple steps to run the design guidelines and validate your integration flow:

1.  In the *Design Guidelines* view, choose *Execute Guidelines*.

    You see the result across these columns:

    In the *Applicability* column – you get to know the applicable design guidelines against which your integration flow is validated.

    In the *Compliance* column – you find if your integration flow is compliant with all the applicable design guidelines.

    In the *Skipped Status* column – you get to know the skipped status of the non-compliant design guidelines.

    In the *Action* column – for every non-compliant design guideline, you find the analysis of what are the expected and actual configurations.

2.  Based on the analysis, do one of the following:

    -   Update your integration flow and resolve the non-compliant design guidelines.

    -   Skip the non-compliant design guidelines – You can skip a non-compliant design guideline by providing a reason and consent to this operation. You can revert any skipped guidelines at any time and reapply them.

        For the non-compliant design guidelines that you want to skip, in the *Skipped Status* column, switch the toggle button. Enter a reason, provide the consent by enabling the checkbox, and choose *Skip*. Once the guideline is skipped, the status changes to *Yes*. Also, an information icon appears next to toggle button where you can view the reason and user who skipped it.

        You can reapply any skipped design guideline by reverting the skip action. To revert, switch the toggle button, provide your consent by enabling the checkbox, and choose *Revert*.


3.  Run the design guidelines again to verify if your integration flow is fully compliant.




### Assess Your Integration Flow

In the *Design Guidelines* view, choose *Download Report* to download the last execution report. In the compliance report, you can also see the non-compliance guidelines that were skipped, along with details such as skipped status, reason for skipping, and who skipped them.

You can download the report multiple times. You can download the report with compliance errors too.

As a best practice, you can share the report with your integration leads to assess your integration flow before deployment.

**Related Information**  


[Integration Flow Design Guidelines](integration-flow-design-guidelines-6803389.md "As an integration developer, you need to make sure that you design integration flows in a robust fashion in order to safeguard your company's mission-critical business processes.")

