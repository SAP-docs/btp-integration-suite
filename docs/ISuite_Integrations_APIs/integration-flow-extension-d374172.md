<!-- loiod3741720e29842e4bf547dcd66139f7f -->

# Integration Flow Extension

SAP Integration Suite allows you to extend the capabilities of standard integration content provided by SAP. This approach allows you to implement specific integration scenarios relevant to your business use case without changing the content provided by SAP.

SAP \(or SAP partners\) provide prepackaged integration content \(also referred to as *standard* content\) that covers a large variety of integration requirements. This content usually comprises a set of integration flows, value mappings, and other integration artifacts that cover a standard integration use case. If you want to adapt these capabilities to specific business requirements, you might consider directly editing and modifying the related integration flows contained in the standard integration package.

However, this does have some disadvantages. For example, you will not get any further updates to modified standard integration content. Furthermore, if you copy the updated standard package from the SAP Integration Content Catalog to the *Design* workspace of your tenant, you will overwrite all changes that you have made to that package.

To avoid such implications, we recommend decoupling the modifications \(required for your specific business scenario\) from the **standard content** provided by SAP. To support this pattern, SAP Integration Suite comes with dedicated concepts and features. Using these features, a customer can specify requirements in one or more dedicated **custom integration flows**, without touching any integration flows from the standard content. Both the standard and the custom integration flows are deployed on the same tenant and are processed in conjunction, communicating with each other using a specific adapter, the *ProcessDirect* adapter.

> ### Note:  
> Using the described concepts, the customer can keep the standard integration content unchanged and specify any required enhancements \(for example, specific mappings\) in one or more custom integration flows separate from the standard integration flow.
> 
> We can summarize the advantages as follows:
> 
> -   Ensures better lifecycle management of prebuilt integration flows. If you make custom changes to a standard integration flow \(prebuilt by SAP\), this has an impact on lifecycle management, as you will not receive future updates related to modified artifacts on your tenant. Additionally, if you copy the updated standard package from the content catalog to the *Design* workspace of your tenant that contains the modified packages, you will overwrite all changes that have been made to that package. Therefore, defining all required changes in a dedicated integration flow helps you to better manage the lifecycle of your integration packages.
> 
> -   Provides flexibility to integration developers to customize their integration flows without modifying them entirely.
> 
> -   Enables the reuse of integration flows for mapping across different integration projects.



<a name="loiod3741720e29842e4bf547dcd66139f7f__section_fb5_bcp_mgb"/>

## Involved Target Groups

As an integration flow extension is based on the interplay of standard integration content with one or more custom integration flows, two target groups are involved in the overall process:

-   *Content publisher* \(at SAP or an SAP partner\)

-   Customer doing the actual extension \(referred to as *customer* in the following\)


This documentation is structured as follows to serve both groups:

****


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Target Group

</th>
</tr>
<tr>
<td valign="top">

[Integration Flow Extension - Concepts](integration-flow-extension-concepts-41b238c.md)

Provides an overview of the concept and the involved components; shows how standard content and extended content work in conjunction.

</td>
<td valign="top">

**Content publisher**

**Customer**

</td>
</tr>
<tr>
<td valign="top">

[Mapping Extension Step by Step \(Demo Example\)](mapping-extension-step-by-step-demo-example-2c3a543.md)

Provides a step-by-step description of a simple demo example and covers *both sides* of the extension story:

-   [Creating the Standard Integration Flow](creating-the-standard-integration-flow-4da82ad.md)

    Shows how to design the standard integration content \(with a post-exit step\)

-   [Creating the Custom Integration Flow with the Post-Exit Mapping](creating-the-custom-integration-flow-with-the-post-exit-mapping-988e5e3.md)

    Shows how to design a post-exit integration flow \(with the customer mapping extension\)




</td>
<td valign="top">

**Content publisher**

**Customer**

This scenario is also feasible as a learning scenario: You should be able to set up and run this example in about an hour.

</td>
</tr>
<tr>
<td valign="top">

[Mapping Extension Step by Step \(Example from SAP Hybris C4C\)](mapping-extension-step-by-step-example-from-sap-hybris-c4c-7749fb7.md)

Shows how a mapping extension is done for a real-life use case \(covering pre-exit and post-exit mappings\).

</td>
<td valign="top">

**Customer** 

</td>
</tr>
</table>

