<!-- loio5f7d522f7c46412087c8988672805b3a -->

# Create Rate Plans

An event rate plan defines the messaging type, access type, queue type, and other configurations that control how events are delivered to consumers.



## Context

You must create at least one rate plan before you can publish an event product from Advanced Event Mesh business system.



## Procedure

1.  Log in to Developer Hub.

2.  Choose *Admin Center* from the top navigation bar.

3.  On the *Manage Content* page, choose the *Rate Plans* tab.

4.  On the *Rate Plans* tab, choose *Create*.

5.  In the *Create Event Rate Plan* dialog, enter the following details:

    -   *Name* \(required\) – Enter a unique name for the rate plan. For example, Gold, Silver, or Platinum.

    -   *Messaging* \(required\) – Select the messaging type from the dropdown:

        -   Guaranteed – Messages are guaranteed to be delivered. Additional queue and spool configurations are required.

        -   Direct – Messages are delivered directly without queuing. No additional configurations are needed.


    -   *Access Type* \(required\) – Select the access type from the dropdown:

        -   Exclusive – Only one consumer can access the queue at a time.

        -   Non Exclusive – Multiple consumers can access the queue simultaneously.


    -   *Queue Type* \(required\) – Select the queue type from the dropdown:

        -   Combined Queue – Events are delivered to a single combined queue.

        -   Single Queue – Events are delivered to individual queues.


    -   *Maximum TTL \(sec\)* \(required\) – Enter the maximum time-to-live in seconds. This defines how long a message is retained in the queue before it expires. For example, 500.

    -   *Spool Size \(MB\)* \(required\) – Enter the maximum spool size in megabytes. This defines the storage limit for queued messages. For example, 100.

        > ### Note:  
        > If you select Direct messaging, the Access Type, Queue Type, Maximum TTL, and Spool Size fields are not applicable and will not be displayed.


6.  Choose *Create* to save the rate plan.

    The new rate plan appears in the *Event Rate Plans* list on the *Rate Plans* tab.




## Results

The rate plan is now available and can be selected when creating or editing an event product from Advanced Event Mesh business system.

