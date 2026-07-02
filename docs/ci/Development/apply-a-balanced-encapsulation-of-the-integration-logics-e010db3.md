<!-- loioe010db3d68b14acaac7a45262aafcf88 -->

# Apply a Balanced Encapsulation of the Integration Logics

Apply a balanced encapsulation of the integration flow to improve the overall readability of the integration.



<a name="loioe010db3d68b14acaac7a45262aafcf88__section_o5l_mzs_mjb"/>

## Implementation

Troubleshooting an integration flow requires that you understand its integration logic. Encapsulating related integration logic in separate integration flows or processes are powerful means to structure the integration flow into different fragments:

-   Using Local Integration Processes

    Using this option allows you to modularize your integration scenario and to specify the various parts of the overall scenario within smaller manageable units called Local Integration Processes \(or: subprocesses\). The Local Integration Process components are called from the main Integration Process through local Process Call steps.

    Using Local Integration Processes comes with some limitations regarding the supported integration patterns \(as described in [Define Local Integration Process](define-local-integration-process-520341a.md)\).

-   Moving certain parts of the scenario into a separate integration flow that can be called through the ProcessDirect adapter.

    The ProcessDirect adapter allows direct communication between integration flows by reducing network latency, provided that both flows are available on the same tenant. Such an intra-tenant message exchange results in at least 1 message processing log per integration flow. The logs are related via the `correlation ID` \(which is described in the OData API documentation about message processing logs entity types\).

    You can find an example integration scenario illustrating this rule at [Outsource Integration Logic into Separate Integration Flows](outsource-integration-logic-into-separate-integration-flows-0bcf78d.md).

-   Using more than 8 nested routes within an integration process can lead to deployment delays and failures due to exponential increases in complexity. To mitigate this issue, consider utilizing local integration processes or other integration flows with process direct adapters to reduce the complexity.

-   Increasing reuse by making sure that an integration flow can be called through different ways \(for example, using different protocols\)

    You can find an example integration scenario illustrating this rule at [Expose an Endpoint for a Scheduled Integration Flow](expose-an-endpoint-for-a-scheduled-integration-flow-d4bb40c.md).


**Related Information**  


[Define Local Integration Process](define-local-integration-process-520341a.md "You use the local integration process to simplify your integration process. You can break down the main integration process into smaller fragments by using local integration processes. You combine these fragments to achieve your main integration process.")

[ProcessDirect Adapter](processdirect-adapter-7445718.md "Use ProcessDirect adapter (sender and receiver) to establish fast and direct communication between integration flows by reducing latency and network overhead provided both of them are available within a same tenant.")

