<!-- loio32e4f6e216cb4e11b1c151c5bf538224 -->

# Consider Basic Layout Principles

Consider basic layout principles when modeling an integration flow.



<a name="loio32e4f6e216cb4e11b1c151c5bf538224__section_ghh_r4q_tjb"/>

## Implementation

SAP Integration Suite offers a graphical modeling environment in the *Design* section that allows you to design integration flows. This tool provides various capabilities supporting you in increasing the readability of an integration flow.

-   Align participants to either the left or the right of the integration process. The flow direction must be from left to right and top to bottom. Message flow must be in straight horizontal or vertical lines.

-   Remove all flow steps that are unused and not connected via message flows.

    Unused and dangling flow steps always lead to deployment errors. If there are valid flow steps, then each one of them must be connected using message flows to be part of the your integration scenario.

-   Create additional integration flow to handle more number of process pools and flow steps.

    An integration flow can handle:

    -   1 Main Integration Process pool

    -   5 Local Integration Process pool

    -   25 flow steps per pool



