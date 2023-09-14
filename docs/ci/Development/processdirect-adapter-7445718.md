<!-- loio74457187451f431298355fbbf807d086 -->

# ProcessDirect Adapter

Use ProcessDirect adapter \(sender and receiver\) to establish fast and direct communication between integration flows by reducing latency and network overhead provided both of them are available within a same tenant.



<a name="loio74457187451f431298355fbbf807d086__prereq_x5l_h55_4cb"/>

## Prerequisites

-   Deployment of the ProcessDirect adapter must support N:1 cardinality, where N \(producer\) → 1 \(consumer\).

    > ### Caution:  
    > Multiple producers can connect to a single consumer, but the reverse is not possible. The cardinality restriction is also valid across integration projects. If two consumers with the same endpoint are deployed, then the start of the second consumer fails.

-   The `Address` mentioned in ProcessDirect configuration settings must match for producer and consumer integration flows at any given point.




<a name="loio74457187451f431298355fbbf807d086__context_mqx_k55_4cb"/>

## Context

**ProcessDirect Receiver Adapter**: If the ProcessDirect adapter is used to send data to other integration flows, the integration flow is considered as a producer integration flow. In this case, the integration flow has a receiver ProcessDirect adapter.

**ProcessDirect Sender adapter**: If the ProcessDirect adapter is used to consume data from other integration flows, the integration flow is considered as a consumer integration flow. In this case, the integration flow has a sender ProcessDirect adapter.

The ProcessDirect adapter supports the following features:

-   **Decompose large integration flows**: You can split a large integration flow into smaller integration flows and maintain the in-process exchange without network latency.

-   **Customize the standard content**: SAP Cloud Integration enables integration developers to customize their integration flows without modifying them entirely. The platform provides plugin touchpoints where integration developers can add custom content. This custom content is currently connected using HTTP or SOAP adapters. You can also use the ProcessDirect adapter to connect the plugin touchpoints at a lower network latency.

-   **Allow multiple integration developers to work on the same integration flow**: In some scenarios, integration flows can be large \(100 steps or more\), and if they are owned or developed by just one integration developer this can lead to an overreliance on one person. The ProcessDirect adapter helps you to split a large integration flow into smaller parts that can be owned and managed by multiple integration developers independently. This allows several people to work on different parts of the same integration flow simultaneously.

-   **Reuse of integration flows by multiple integration processes spanning multiple integration projects**: Enables the reuse of integration flows such as error handling, logging, extension mapping, and retry handling across different integration projects and Camel context. Integration developers therefore only need to define repetitive logic flows once and can then call them from any integration flow using the ProcessDirect adapter.

-   **Dynamic endpoint**: Enables the producer integration flow to route the message dynamically to different consumer integration flow endpoints. The producer integration flow look ups the address in the headers, body, or property of the exchange and the corresponding value is then resolved to the endpoint to which the exchange is to be routed.

-   **Multiple MPLs**: MPL logs are interlinked using correlation IDs.

-   **Transaction processing**: Transactions are supported on integration flows using the ProcessDirect adapter. However, the scope of the transaction is isolated and restricted to a single integration flow.

-   **Header propagation**: Header propagation is not supported across producer and consumer integration flows unless configured in *<Allowed Header\(s\)\>* in the integration flow's runtime configuration.

-   **Property propagation**: Property propagation is not supported across producer and consumer integration flows, except for `SAP_SAPPASSPORT` property. This property is for internal use only and users are not allowed to modify it.


> ### Tip:  
> ProcessDirect adapter improves network latency, as message propagation across integration flows do not involve load balancer. For this reason, we recommend that you consider memory utilization as a parameter in scenarios involving heavy payloads and alternatively use HTTP adapter in such scenarios because, the behavior will be the same.

> ### Restriction:  
> Cyclic loop deployment of integration flows must be avoided.

**Related Information**  


[Configure the ProcessDirect Sender Adapter](configure-the-processdirect-sender-adapter-e340d4c.md "You use the ProcessDirect sender adapter to establish fast and direct communication between integration flows by reducing latency and network overhead provided both of them are available within a same tenant.")

[Configure the ProcessDirect Receiver Adapter](configure-the-processdirect-receiver-adapter-5b7327d.md "You use the ProcessDirect receiver adapter to establish fast and direct communication between integration flows by reducing latency and network overhead provided both of them are available within a same tenant.")

