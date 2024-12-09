<!-- loioa81309fbdc4446b98e138a328bf1776c -->

# Understanding the Basic Concepts

Learn more about the concept behind Cloud Integration.

Cloud Integration facilitates end-to-end process integration by enabling the exchange of messages between different software systems. In this way, Cloud Integration functions as a central hub for communication between software systems by exchanging messages.

A fundamental integration pattern is illustrated in the following diagram, showing a sender sending a message to Cloud Integration, which then forwards the message to various receivers. You have the ability to design the integration aspects, including how Cloud Integration processes messages received from a sender system. For example, the diagram demonstrates the routing integration pattern, where the message is forwarded to a specific receiver based on its content.

![](images/Cloud_Integration_Basic_Pattern_52e59c0.png)



<a name="loioa81309fbdc4446b98e138a328bf1776c__section_ath_df1_cdc"/>

## Integration Content

You utilize Cloud Integration to create, manage, operate and monitor integration scenarios, which define the integration-related aspects of a business process. In other words, an integration scenario specifies how messages are exchanged among different components \(senders and receivers\) through Cloud Integration.

Cloud Integration provides the ability to design such integrations, with the integration flow being a key component. An integration flow defines how a message is processed by Cloud Integration.

An integration flow is one type of integration content object.

See: [Elements of an Integration Flow](50-Development/elements-of-an-integration-flow-e49dbee.md) 



<a name="loioa81309fbdc4446b98e138a328bf1776c__section_ndg_v21_cdc"/>

## Phases of an Integration Project

An integration developer is responsible for designing integration scenarios to implement specific business processes. Usually, integration developers go through various phases based on the scope of the integration project.


<table>
<tr>
<th valign="top">

Phase

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Discover

</td>
<td valign="top">

The integration developer checks to see if there's already predefined integration content available to meet their integration requirements. You can find the catalog of integration content predefined by SAP under *Discover* \> *Integrations.* 

See: [Working with Prepackaged Integration Content](50-Development/working-with-prepackaged-integration-content-bd2ed3e.md)

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

The integration developer also has the option to design integration content \(such as integration flows\) from scratch or enhance predefined content identified in the discovery phase.

To design integration content, go to *Design* \> *Integrations and APIs*.

See:

-   [Basic Concepts of Integration Design](50-Development/basic-concepts-of-integration-design-ca0f6f7.md)

-   [Integration Development](50-Development/integration-development-b18936e.md)




</td>
</tr>
<tr>
<td valign="top">

Operate and monitor

</td>
<td valign="top">

After a successful design phase, the integration developer deploys the integration content to its runtime location.

SAP Integration Suite offers the capability to deploy integration content on various runtime locations, which are specific environments where the integration content, such as integration flows, is deployed and executed. These environments can include your SAP Business Technology Platform instance, an on-premise SAP Process Orchestration runtime, or a private cloud environment. Therefore, you have the option to select different types of runtime profiles based on your requirements \(see [Runtime Profiles](50-Development/IntegrationSettings/runtime-profiles-8007daa.md)\).

From that point on, the integration content is operational, and the processing of messages can be monitored.

To monitor integration content, go to *Monitor* \> *Integrations and APIs*.

See: [Monitor Integrations](50-Development/monitor-integrations-05446d0.md)

</td>
</tr>
</table>

