<!-- loio4edeee5e46904792a51788260689c529 -->

# What Is Data Space Integration?

Learn more about the Data Space Integration capability within SAP Integration Suite.

The Data Space Integration capability within SAP Integration Suite allows data space participants to exchange data with other participants of the same data space \(for example, Catena-X\) in a reliable, secure, and sovereign manner. It offers a simple integration of SAP and non-SAP applications as well as a harmonized and intuitive way to configure and monitor the data exchange within a data space leveraging SAP Integration Suite.



<a name="loio4edeee5e46904792a51788260689c529__section_gxh_lnr_gyb"/>

## Eclipse Dataspace Components

Data Space Integration is based on the open-source Eclipse Dataspace Connector \(EDC\) technology. EDC provides a connector framework for sovereign, interorganizational data exchange. The framework contains modules for performing data query, data exchange, policy enforcement, monitoring, and auditing. Specifically, it integrates with existing identity, data catalog, and transfer technologies to provide compliance, policy, and control capabilities across organizations. A data-sharing system requires a protocol implementation for policy enforcement among participants, so EDC will implement the International Data Spaces standard \(IDS\) while being extensible so that it can support alternative protocols.



<a name="loio4edeee5e46904792a51788260689c529__section_csc_qnr_gyb"/>

## Data Spaces

The International Data Spaces \(IDS\) initiative aims to establish a uniform standard for data sharing \(IDS\) that can be applied in any professional and private areas based on the European Privacy Policy \(DPP\) to enforce data sovereignty. An IDS data space is a virtual place that enables sovereign data governance, based on interoperable standardized components, among involved persons and companies. Data spaces are typically organized by industry or topic.



> ### Note:  
> Currently, Data Space Integration supports connections to the following data spaces:
> 
> -   [Catena-X](https://catena-x.net)
> 
>     See also the [Release Notes](https://catenax-ev.github.io/release-notes) of Catena-X.



<a name="loio4edeee5e46904792a51788260689c529__section_n1q_3nd_lxb"/>

## Environment

The Data Space Integration capability within SAP Integration Suite is available in the Cloud Foundry environment.



<a name="loio4edeee5e46904792a51788260689c529__section_qsl_jnd_lxb"/>

## Multitenancy Support

This service supports multitenancy. It can be used in tenant-aware applications.



<a name="loio4edeee5e46904792a51788260689c529__section_ffj_lnd_lxb"/>

## Overview

Data Space Integration allows data space participants to exchange data with other participants of the same data space. The following graphic illustrated the different steps and interactions involved in this exchange:

![The diagram shows how the participants of a data space interact with each other. First, the provider creates both assets and policies, which come together to form a contract definition. Based on the contract definition, the provider creates a contract offer. At this point, the provider and consumer together begin the contract negotiation based on the contract offer. This process of negotating and creating offers can take multiple interations. After successful negotiations between provider and consumer, a contract agreement is reached.](images/Dataspace_Interaction_Process_a605456.jpg)

For more information, see [Concepts in Data Space Integration](concepts-in-data-space-integration-fcf96b2.md).



<a name="loio4edeee5e46904792a51788260689c529__section_zr3_dxb_nxb"/>

## Tools


<table>
<tr>
<th valign="top">

Tool

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

SAP BTP cockpit 

</td>
<td valign="top">

The central point for managing all activities associated with your SAP BTP subaccount.

See: [Tools](https://help.sap.com/docs/btp/sap-business-technology-platform/tools?version=Cloud&q=tools) 

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration 

</td>
<td valign="top">

Integrate SAP and non-SAP, cloud, and on-premise applications and process messages in real-time scenarios spanning different companies, organizations, or departments within one organization.

See: [Cloud Integration](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/sap-cloud-integration?version=Cloud&locale=en-US) 

</td>
</tr>
</table>

