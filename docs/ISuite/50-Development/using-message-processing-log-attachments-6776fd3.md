<!-- loio6776fd33d672479ca4cec35752d3bdeb -->

# Using Message Processing Log Attachments

You can store the payload as message processing log attachment.

> ### Caution:  
> Use this approach with ease due to the limited storage size of your SAP Integration Suite tenant. If you expect high message volumes and the integration flow contains many persistency steps, there's the risk of exceeding the upper limit of your disk space. This means, you run into situations where the circuit breaker is opened, see [Persist Messages](persist-messages-8c35f3f.md).

Depending on your use case, implement one of the following measures:

-   When designing integration content, use the integration flow simulation capability.

    More information: [Simulation of an Integration Flow](simulation-of-an-integration-flow-2e2210b.md)

-   When performing a root cause analysis, use the tracing capability instead of placing multiple MPL attachment steps into your integration flow model.

    More information: [Tracing the Execution of an Integration Flow](tracing-the-execution-of-an-integration-flow-4ec27d3.md)

-   When writing MPL attachments, avoid writing the complete payload. Instead of this, extract only those parts of your payload that are necessary for your use case. Optionally, write key information into custom header properties. Custom header properties aren't only displayed in the message log but you can also search your messages based on them.

    More information: [Use Custom Header Properties to Search for Message Processing Logs](use-custom-header-properties-to-search-for-message-processing-logs-d4b5839.md)

-   Ensure that message logging through MPL attachments is disabled if not needed. For example, switch it on within your test environment, however deactivate this option in your production environment. You can also enable or disable MPL attachments by using an externalized parameter that is either true or false. This way, you can configure the MPL attachment handling without the need of modifying the integration flow.


