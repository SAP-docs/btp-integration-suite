<!-- loioa8cd981bd54440c7bbc0b09c21654f51 -->

# Guidelines to Design Enterprise-Grade Integration Flows

As an integration developer, you need to make sure that you design integration flows in a robust fashion in order to safeguard your company's mission-critical business processes.

An integration flow is enterprise grade when it's designed in such a way that it's qualified to implement parts of the mission-critical processes of an enterprise. A poorly designed integration flow can lead to errors. In the worst case, the integration flow breaks, resulting in a service disruption for the business process. It is your responsibility to design an integration flow in such a way that the overall availability of the business process isn't impaired. To fulfill this requirement, you need to embrace certain characteristics constituting an enterprise-grade integration flow.

> ### Note:  
> For example, you can design your integration flows in many different ways to implement a certain integration scenario. However, there are certain guidelines that help you to optimize the performance of your scenario \(see [Optimize Performance](optimize-performance-491c80d.md)\).

In this section, we introduce guidelines for designing enterprise-grade integration flows in SAP Integration Suite.

Enterprise-grade integration flows have the following qualities:



<a name="loioa8cd981bd54440c7bbc0b09c21654f51__section_a2g_4nf_n3b"/>

## High Availability

One of the key qualities of a cloud service is high availability. As such, it's essential that you build robust integration flows that never break the business process. A prerequisite is that you consider certain patterns when modeling the integration flow. These patterns can be assigned to different qualities constituting an enterprise-grade integration flow.



<a name="loioa8cd981bd54440c7bbc0b09c21654f51__section_igs_snf_n3b"/>

## Resilience

One of the most crucial qualities of an enterprise-grade integration flow is its resilience. The traditional \(deterministic\) approach assumes a software system free of malfunctions. But resilient software design doesn't try to avoid failures. Instead, it assumes that failures are going to occur and can't be prevented or predicted. The resilience approach tries to minimize the time that elapses between the occurrence of a failure and its correction. An integration flow can involve complex integration logic including enriching the message content with data from external components, storing data in a database persistence, and much more. Consequently, make sure that you apply principles for resilient software development when developing an integration flow.



<a name="loioa8cd981bd54440c7bbc0b09c21654f51__section_pnj_14f_n3b"/>

## Resource Management

Processing messages in SAP Integration Suite requires resources. Since resources are often limited, they must be managed to prevent leaks. SAP Cloud Integration relies, depending on the capabilities used in the integration flow, on the computing system, database persistence, and messaging service broker to process messages. Developing enterprise-grade integration flows mandates the diligent management of the resources available on the tenant.



<a name="loioa8cd981bd54440c7bbc0b09c21654f51__section_tfk_f4f_n3b"/>

## Loose Coupling

Loose coupling is a basic principle for preventing cascading failures. Executing an integration flow usually requires invoking external components. For example, an endpoint in an application system is called during outbound processing of a message. If the external component can't be reached, the integration flow execution fails with an error. Relaxing dependencies to external components increases the robustness of an integration flow. Temporary failures must be anticipated when the integration flow tries to connect to an external component.



<a name="loioa8cd981bd54440c7bbc0b09c21654f51__section_jt4_34f_n3b"/>

## Handling Failures Gracefully

Failures in the logic of an integration flow must not lead to a service disruption of the business process. Instead, failures must be handled gracefully. Supervision is required to observe the execution status of an integration flow. If there is a failure in the execution of the integration flow, sufficient data needs to be collected for later troubleshooting. Errors thrown during integration flow execution must be caught and appropriately handled in the further processing of the message.



<a name="loioa8cd981bd54440c7bbc0b09c21654f51__section_fj5_l4f_n3b"/>

## Readability

Readability of an integration flow is crucial for its maintainability. If a simple integration flow is poorly designed, it creates a perception of complexity. As an integration developer, make sure that you leverage the capabilities of the integration flow modeler of SAP Integration Suite to visualize the message processing flow, keeping its maintainability in mind.



<a name="loioa8cd981bd54440c7bbc0b09c21654f51__section_fgm_t4f_n3b"/>

## Usage of Prepackaged Integration Content

We deliver prepackaged integration content for various business processes. The prepacked integration content contains integration flows, value mappings, documentation, and more. By using this content, integration developers can get a quick-start into an integration project.



<a name="loioa8cd981bd54440c7bbc0b09c21654f51__section_x3y_bmf_plb"/>

## Application-Specific Guidelines Related to SAP Integration Suite 

There are application-specific guidelines related to SAP Integration Suite. For more information, see:


<table>
<tr>
<th valign="top">

Information Source

</th>
<th valign="top">

Related Application/Topic

</th>
</tr>
<tr>
<td valign="top">

[Managing time intensive Integration Flows using SAP Integration Suite](https://blogs.sap.com/2020/02/10/managing-time-intensive-integration-flows-using-sap-cloud-platform-integration-and-sap-api-management/) 

</td>
<td valign="top">

SAP API Management

</td>
</tr>
<tr>
<td valign="top">

[Implementation Design Principles for SAP SuccessFactors solutions](https://blogs.sap.com/2019/04/15/implementation-design-principles-idp-for-successfactors/) 

</td>
<td valign="top">

SAP SuccessFactors

</td>
</tr>
<tr>
<td valign="top">

[Making SAP SuccessFactors and SAP Cloud Integration more reliable and performant](https://blogs.sap.com/2020/09/23/making-sap-successfactors-and-sap-cloud-platform-integration-more-reliable-and-performant/) 

</td>
<td valign="top">

SAP SuccessFactors

</td>
</tr>
</table>

**Related Information**  


[Run an Integration Flow Under Well-Defined Boundary Conditions](run-an-integration-flow-under-well-defined-boundary-conditions-f8cf974.md "Developing enterprise-grade integration flows mandates the diligent management of the resources available on the customer tenant. Depending on the capabilities used in the integration flow, SAP Integration Suite relies on the computing system, database persistence, and messaging service broker to process messages.")

[Relax Dependencies to External Components](relax-dependencies-to-external-components-3ea1e33.md "Calls to external components must be closely controlled. When you specify outbound processing of a message, anticipate a temporary unavailability of the called external component.")

[Keep Readability in Mind](keep-readability-in-mind-578fa77.md "Readability of the integration flow is crucial for its maintainability.")

[Handle Errors Gracefully](handle-errors-gracefully-42c95f7.md "Even well-designed integration flows sporadically break based on load, resource usage, and other factors. To prepare for such situations, extend the integration flow with the appropriate error handling.")

[Use Prepackaged Integration Content Provided by SAP](use-prepackaged-integration-content-provided-by-sap-95c68ce.md "SAP delivers prepackaged integration content out of the box that enables integration developers to get started quickly. These integration packages are created for some of the commonly used business processes.")

[Apply the Highest Security Standards](apply-the-highest-security-standards-201fd43.md "")

[Use the Partner Directory Appropriately](use-the-partner-directory-appropriately-6e00412.md "When designing business-to-business scenarios, you can use the Partner Directory to store information on business partners that are connected to the tenant in the context of a larger business network.")

[Use Scripting Appropriately](use-scripting-appropriately-d4dc13c.md "You can use the Script step to apply script operations on the message content.")

