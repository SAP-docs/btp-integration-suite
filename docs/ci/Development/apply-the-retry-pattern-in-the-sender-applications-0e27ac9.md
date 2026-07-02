<!-- loio0e27ac963308474f941436565d76de6b -->

# Apply the Retry Pattern in the Sender Applications

While SAP strives to ensure the highest possible availability of the provided services, true resilience of communication is a two-way collaboration between client and server. Thus, it is important to implement any sender applications in a resilient way. Retry patterns are adopted during integration flow design to manage [Quality of Service](https://help.sap.com/docs/integration-suite/sap-integration-suite/quality-of-service?version=CLOUD) expectations, and it helps integrations remain reliable when temporary connectivity issues occur between systems. This guideline explains key considerations to balance reliability, response time, and resource usage when designing retry behavior.

> ### Note:  
> This guideline applies to HTTP-based communications initiated by the sender application into the Cloud Integration tenant during integration flow design.



## Control the Number of Simultaneously Running Synchronous HTTP Inbound Integration Flows

Synchronous integration flows consume runtime resources for the entire duration of request processing, including any retry attempts performed by receiver adapters.

When a receiver adapter retries connectivity to the target system, the corresponding integration flow instance continues to occupy the available resources until either a successful response is received or all retry attempts are exhausted. As a result, the resources available to process other synchronous messages is temporarily reduced.

**Runtime Environment Implications**

-   **Cloud Integration Runtime:** Resource exhaustion blocks the health check execution, triggering automatic runtime restarts.

-   **Edge Integration Cell Runtime:** Applications receive HTTP error code 503 \(Service Unavailable\) when resource capacity is exhausted.


Integration administrators should monitor message processing logs for integration flows that transition to an abandoned status due to tenant restarts. In addition, they also monitor the inspect tool to detect signs of resource saturation. If required, request additional worker resources from SAP operations to ensure stable and uninterrupted execution.



## Design Synchronous Interfaces with Idempotency Where Required

Synchronous integration scenarios require careful idempotency design to prevent duplicate business transactions when retry mechanisms execute multiple calls for the same business operation. When implementing sender-side retry mechanisms, refer to [Sender Handles Retry](https://help.sap.com/docs/integration-suite/sap-integration-suite/sender-handles-retry?version=CLOUD) for detailed guidance on idempotency considerations. To learn more idempotent receiver design, see [Receiver is Idempotent](https://help.sap.com/docs/integration-suite/sap-integration-suite/sender-handles-retry-receiver-is-idempotent?version=CLOUD).



## Implement Proper Timeout Configurations in the Sender

When retry pattern is implemented, the sender must configure timeout values appropriately to allow retries to complete without premature connection termination. In addition to application-level timeouts, network components may terminate idle connections after a predefined period. These timeout limits can vary depending on the underlying platform and environment and should be considered when designing synchronous interfaces in applications that trigger synchronous integration scenarios. Please refer to the idle timeout values [here](https://pages.github.tools.sap/cloudfoundry/documentation/internal-documentation/routing-tier-timeouts#idle-timeout) for current platform-specific timeout configurations.

