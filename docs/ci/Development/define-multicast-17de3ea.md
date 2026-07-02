<!-- loio17de3ea5757146d5994a31a3c4d4fbfb -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Multicast



## Context

You can use the *Multicast* step to send copies of the same message to multiple routes. You can send copies to all routes at once using *Parallel Multicast* or in an order of your choice using *Sequential Multicast*. This allows you to perform multiple operations on the same message in a single integration process. Without *Multicast*, you needed multiple integration processes to perform this task.

There are certain best practices and limitations that you must know when using Multicast:

-   The number of outgoing branches using a *Multicast* step must be equal to the number of incoming branches in a *Join* step.

-   Use only one *Multicast* step per *Integration Process* pool.

    To handle errors, you must move all inner *Multicast* steps \(Multicast steps within a Multicast step\) along with its branches to a new *Local Integration Process* pool with its own *Exception Subprocess* pool. For more information, see [SAP Note 3028577](https://me.sap.com/notes/3028577).

-   Use *Router* and *Multicast* steps in different Integration Process pools.

    Always include the *Router* step in a separate *Local Integration Process* pool and call it from the multicast branch.

-   If you like to combine the resulting output from multicast branches, use a *Gather* step immediately after the *Join* step to avoid data loss.




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


