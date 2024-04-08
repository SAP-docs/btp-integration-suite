<!-- loio17de3ea5757146d5994a31a3c4d4fbfb -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Multicast



## Context

You can use the *Multicast* step to send copies of the same message to multiple routes. You can send copies to all routes at once using *Parallel Multicast* or in an order of your choice using *Sequential Multicast*. This allows you to perform multiple operations on the same message in a single integration process. Without *Multicast*, you needed multiple integration processes to perform this task.



## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Routing\), then *Multicast*.

2.  Choose *Parallel Multicast* or *Sequential Multicast* based on your requirement and place the step inside the integration process. Define the message paths based on the scenario.

    Based on the order in which you define the message path, the system assigns names to each message route branch as **Branch 1**, **Branch 2**, and so on.

3.  If you want to specify a name for this step, enter the value in *Name* field.

4.  If you are using *Parallel Multicast*, no further configuration is required for the multicast step.

5.  If you are using *Sequential Multicast*, you can change the order in which the message should be sent to the *Sequential Multicast* branches:

    1.  Choose *Routing Sequence*.

    2.  Select the branch which you want to move up or down in the order.

    3.  Use *Move Up* and *Move Down* to change the order.


    The branch name is dependent on the order in which you have defined the message path. If you change the order, the branch name will not change.

6.  Save or deploy the configuration.


