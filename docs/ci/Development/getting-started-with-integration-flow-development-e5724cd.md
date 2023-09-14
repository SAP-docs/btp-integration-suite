<!-- loioe5724cd84b854719973afe0356ea128b -->

# Getting Started with Integration Flow Development

Learn how to develop and run your first integration flow.

> ### Note:  
> These exercises apply for both cases when you use SAP Cloud Integration in the Neo and in the Cloud Foundry environment.
> 
> Note that at certain steps there are specific things to consider depending on the environment. If this is the case, it’s indicated in this documentation.

> ### Note:  
> In addition to the exercises provided in this section, you can also check out the [Integration Flow Design Guidelines](integration-flow-design-guidelines-6803389.md).
> 
> The integration flow design guidelines provide both documentation and predefined integration content. You can deploy and run the integration content out-of-the-box to learn basic concepts of Cloud Integration. You can also access the integration flows from SAP Business Accelerator Hub as described in [How to Work with the Example Integration Flows](how-to-work-with-the-example-integration-flows-03e6959.md).

A key part of an SAP Cloud Integration project is to develop integration flows. An integration flow allows you to specify how SAP Cloud Integration is to process a message. SAP Cloud Integration provides a modeling environment that allows you to design the details of message processing \(its senders and receivers as well as the individual processing steps\) with a graphical user interface.

This section shows you step by step how to develop and run your first, simple integration flows. In other words, it gives you an introduction to the tasks of an integration developer. We show you the design of four integration flows, with increasing complexity.

> ### Note:  
> The first three integration flows start with a timer and don't have a sender. This means that you can omit all tasks related to setting up a sender system to SAP Cloud Integration.
> 
> The fourth integration flow is initiated by a request from a sender system that is simulated by an HTTP client.

To complete the tasks, you use the SAP Cloud Integration Web UI.

Before designing any integration flow of this section, you need to create an integration package first and, within this integration package, create an integration flow. When you've created the integration flow, you add the steps as described for the specific integration flow exercise.

-   The first exercise shows you how to perform a simple *smoke test* to check whether your tenant cluster is working correctly and that it processes messages in the expected way. A simple message is created with the text `Hello World!` in the message body. The integration flow has no receiver. To check if the message has been processed successfully, you can go to the monitoring application and check for the message content there.

    More information: [Smoke Test Scenario](smoke-test-scenario-8c83fcf.md)

-   The second exercise shows you how to extend the *smoke test* scenario by adding an outbound call to an external data source. The integration flow requests data exposed by the external component through an OData application programming interface \(API\). The message body is created based on that data and, like in the first exercise, can be displayed by the monitoring application.

    More information: [Smoke Test Scenario with External Data Source](smoke-test-scenario-with-external-data-source-e4bef74.md)

-   The third exercise is a simple enhancement and modification of second integration flow. It has an e-mail receiver so that you receive the message \(processed by SAP Cloud Integration\) in an e-mail account of your choice.

    More information: [Timer-Initiated Scenario with a Mail Receiver](timer-initiated-scenario-with-a-mail-receiver-bfee17e.md)

-   The last exercise is a simple integration flow that also has a sender component. The sender in this example is simulated by an HTTP client installed on your computer.

    More information: [Sender-Initiated Scenario \(with HTTPS Sender Adapter\)](sender-initiated-scenario-with-https-sender-adapter-ccdb189.md)


The exercises are designed so that you can do all four of them independently. All steps are described one-by-one. But you can also start with the first one and, successively, enhance it to derive the second and the third scenario out of the first one.

There are sample integration flows that show other simple modifications and additional features.

More information: [Further Sample Integration Flows](further-sample-integration-flows-b0db14e.md)

> ### Note:  
> Prerequisites:
> 
> -   You have set up an e-mail account that you can use as the receiver system for the integration flow \(only required for third exercise with the Mail adapter\).
> 
> -   You have opened the SAP Cloud Integration Web UI, which contains all the tools you need to set up, run, and monitor your integration scenario.
> 
>     You can access the Web UI using the hyperlink that ends with `/itspaces`.
> 
> -   You have been given access to an SAP Cloud Integration tenant and have the following permissions assigned to your user \(in the Cloud Foundry environment\):
> 
>     -   Authorization group `PI_Integration_Developer` \(to be authorized to perform integration developer tasks\)
> 
>     -   Authorization group `PI_Business_Expert` \(to allow you to access message processing log attachments\)
> 
> 
> -   You have been given access to an SAP Cloud Integration tenant and have the following permissions assigned to your user \(in the Neo environment\):
> 
>     -   Role collection `AuthGroup.IntegrationDeveloper` \(to be authorized to perform integration developer tasks\)
> 
>     -   Role collection `AuthGroup.BusinessExpert` \(to allow you to access message processing log attachments\)



<a name="loioe5724cd84b854719973afe0356ea128b__section_e5g_r33_t2b"/>

## Further Reading

For an introduction to the concept of integration flows, check out [Elements of an Integration Flow](elements-of-an-integration-flow-e49dbee.md).

For an overview of the available connectivity options \(adapter types\), check out [Connectivity \(Adapters\)](../WhatIsCloudIntegration/connectivity-adapters-55325f2.md).

For an overview of the available message processing options \(integration flow step types\), check out [Integration Capabilities](../WhatIsCloudIntegration/integration-capabilities-e32cede.md).

**Related Information**  


[Overview of the SAP Cloud Integration Web UI](overview-of-the-sap-cloud-integration-web-ui-9af2f05.md "")

[Creating an Integration Package](creating-an-integration-package-9126d79.md "Create an integration package that is specific to your integration scenario.")

[Creating an Integration Flow](creating-an-integration-flow-da53d93.md "Add an integration flow to an integration package.")

[Smoke Test Scenario](smoke-test-scenario-8c83fcf.md "")

[Smoke Test Scenario with External Data Source](smoke-test-scenario-with-external-data-source-e4bef74.md "")

[Timer-Initiated Scenario with a Mail Receiver](timer-initiated-scenario-with-a-mail-receiver-bfee17e.md "Create a simple integration scenario that is initiated by a timer, retrieves data from an external source, and sends the result to an e-mail account (as the receiver system).")

