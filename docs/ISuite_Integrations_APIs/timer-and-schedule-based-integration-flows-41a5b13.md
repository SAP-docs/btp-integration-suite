<!-- loio41a5b13406c044e0853bc3d7592a8e90 -->

# Timer and Schedule based Integration Flows

This section describes how to design and operate schedule‑based integration flows in SAP Cloud Integration. This is applicable for certain sender components, particularly timers, and in built schedule feature in polling adapters \(SFTP and FTP\) have best effort quality of service.



## Context

SAP Cloud Integration runs on a multi‑node worker runtime.

When a timer‑initiated integration flow is deployed:

-   The timer event is evaluated on all active worker nodes.

-   Internal concurrency control ensures that only one node executes the timer activation at any given scheduled time.

-   All remaining nodes skip execution for that trigger.

    For Start Timer events:

    -   Skipped executions are recorded in the Message Processing Log with the status Discarded.
    -   This behavior is expected and indicates normal cluster coordination.


For details about the underlying architecture, see [Integration Flow Deployed on Multiple Worker Nodes](integration-flow-deployed-on-multiple-worker-nodes-95bb34a.md)



## Execution and Monitoring Behavior: Discarded Messages

The appearance of Discarded entries for timer‑initiated integration flows in the Message Processing Log is normal runtime behavior in a clustered environment. These entries represent worker nodes that detected the timer but did not execute it.



### **Best‑Effort Execution Model**

Timer and scheduled executions in polling adapters operate on a best effort basis:

-   Execution can be skipped if a previous run is still active.
-   Triggers may be lost if the worker process is restarted due to maintenance, upgrades, or system failures.
-   As a result, timer initiation does not guarantee execution for every scheduled trigger.



### **Monitoring Recommendation**

If successful execution of a timer‑initiated integration flow is business‑critical:

-   Monitor execution externally, not solely through internal runtime guarantees. Use the Message Processing Log API to confirm successful completions. See [3381987](https://me.sap.com/notes/3381987)
-   Set the integration flow log level to Info.
-   Add custom monitoring logs into an own hosted database to get information of missed runs.



## Design Guidelines for Clustered Environments

1.  **Design for Best‑Effort Execution**
    -   Do not design scenarios that require exactly‑once execution guarantees based solely on timer triggers.
    -   Assume that scheduled events can be skipped under specific runtime conditions. See [3663256](https://me.sap.com/notes/3663256)

2.  **Keep Processing Time within the Schedule Interval**

    When using periodic schedules:

    -   If a flow is still running when the next trigger occurs, that trigger is skipped.
    -   Design flows so that the maximum expected processing time comfortably fits within the configured interval.

3.  **Decouple Business Interval from Schedule Timing**

    For scenarios such as periodic data synchronization:

    -   Do not rely on the timer firing exactly once per business interval.

        Instead:

        -   Persist the last successful execution timestamp.
        -   Derive the data processing window dynamically based on stored state.
        -   Process all outstanding intervals during the next successful run.


    This ensures data consistency even if one or more triggers are skipped.




## Common Design Pitfalls to Avoid

Avoid the following patterns when designing timer‑initiated flows:

-   **Using the current timestamp as the data query start time**: Results in silent data loss if a trigger is skipped.
-   **Assuming the timer fires exactly on schedule**: Under load, outages, or node restarts, executions can be delayed or entirely skipped.
-   **Failing to handle outages or restarts**: Always calculate processing windows from persisted state, not from trigger time.



## Guidance on Run-Once Scheduling

Run‑Once scheduling relies on a **run‑on‑deploy** pattern and long‑term concurrency handling.

As a result:

-   It may behave unpredictably in high‑load or long‑running production systems.
-   It is intended for testing purposes only.

> ### Recommendation:  
> Recommendation: For production scenarios, always use Schedule at a specific time. This avoids unintentional reruns at later points in time.



### **Additional Notes on Expired Schedules**

For schedules configured with a trigger time in the past:

-   Do not rely on the integration flow status changing to **Error** in the Monitoring view as a control mechanism.
-   To ensure consistent monitoring behavior:
    -   Use Start Timer component version 1.4 or higher
    -   Disable Throw Exception on Expiry


This ensures the integration flow remains in Started state and avoids misleading error states.



## Summary

Timer and scheduler‑initiated integration flows in SAP Cloud Integration are cluster‑aware and best‑effort by design.

Reliable production scenarios require:

-   External monitoring
-   State‑driven data window calculation
-   Proper handling of skipped or delayed executions

Designing with these principles ensures resilient and predictable integration behavior in multi‑node runtimes.

