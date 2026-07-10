<!-- loio2c3a5436ce414ac4a8b3fd4ba8b98bb2 -->

# Mapping Extension Step by Step \(Demo Example\)

A demo example, explained step by step, covers the key aspects of integration flow extension.

This section provides a more detailed view of the concept overview given in [Integration Flow Extension - Concepts](integration-flow-extension-concepts-41b238c.md). We walk you through the most important concepts and involved components using a simple demo scenario.

You should be able to set up and run the scenario within approximately one hour.

> ### Note:  
> The demo scenario covers both the design of the standard integration flow and of the custom integration flow. Consider the following:
> 
> -   This demo scenario covers *both sides of the extension concept*: the design of the standard integration content and the customer extension \(in a post-exit integration flow\). Note that these tasks are typically accomplished by different target groups. Therefore, the demo scenario is aimed at experts from both target groups who want a more detailed understanding of the concepts and also hands-on experience of the tasks.
> 
>     The tasks described in the two parts of the demo scenario are associated with the different target groups as follows:
> 
>     -   [Creating the Standard Integration Flow](creating-the-standard-integration-flow-4da82ad.md)
> 
>         Describes the tasks accomplished by the **content publisher** \(at SAP or an SAP partner organization\) who makes this integration flow available as part of a predefined integration package that customers can copy into their own workspace.
> 
>     -   [Creating the Custom Integration Flow with the Post-Exit Mapping](creating-the-custom-integration-flow-with-the-post-exit-mapping-988e5e3.md)
> 
>         Describes the tasks accomplished by the **customer** who is extending the content.
> 
> 
> -   The example scenario does **not** reflect a real-life integration use case. We keep the mapping as simple as possible and focus on the main principles and concepts so that you can see the differences between the standard mapping provided by SAP and the customer extension. To make it easy for you to reproduce the example, the integration flows are based on the scenario described in [SOAP Sender Adapter: Example Integration Flow](soap-sender-adapter-example-integration-flow-ad2409e.md).
> 
> -   To find instructions for a mapping extension based on a real-life example, check out [Mapping Extension Step by Step \(Example from SAP Hybris C4C\)](mapping-extension-step-by-step-example-from-sap-hybris-c4c-7749fb7.md).
> 
> -   The demo scenario does **not** use a pre-exit step.



<a name="loio2c3a5436ce414ac4a8b3fd4ba8b98bb2__section_gpl_prh_cgb"/>

## Overview of the Demo Scenario

This section covers the following extension scenario with a post-exit.

![](images/Mapping_Extension_with_Post_Exit_Overview_Fl_ow_1887ac7.png)

In this scenario, the standard integration flow passes a message to a post-exit integration flow \(which contains the custom mapping\).

In this demo scenario, the sender system is simulated by a SOAP client, which sends a SOAP message to SAP Integration Suite . The original message has a simple structure \(only four elements\). The standard mapping is also kept simple and concatenates \(me.res\) two of the original fields

More information: [Standard Mapping](standard-mapping-56c3bf5.md)

The mapping extension in the post-exit integration flow \(the customer extension\) adds an additional field to the target message and fills it with the value of a field from the original message \( changing uppercase letters to lowercase letters\).

More information: [Post-Exit Mapping](post-exit-mapping-0f17497.md)

To learn how to design the standard integration flow, see [Creating the Standard Integration Flow](creating-the-standard-integration-flow-4da82ad.md).

To learn how to design the post-exit integration flow, see [Creating the Standard Integration Flow](creating-the-standard-integration-flow-4da82ad.md).

To learn how to execute the scenario, see [Executing the Scenario](executing-the-scenario-909ec34.md).

