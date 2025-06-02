<!-- loioe5bd17fbb36242e0bf621a9e0953f9a0 -->

# Data Collection for Knowledge Base

Information about the data that is collected by the knowledge base for generating proposals.

To generate and provide better proposals, SAP Integration Advisor collects some data respective to each artifact for its knowledge base. To know more about the contract information, refer to the section **SAP Integration Suite** here: [SAP Cloud Service Description Guide](https://cloudplatform.sap.com/support/service-description.html#section_11).

> ### Note:  
> To avoid the data collection for proposal service, you can opt out of proposal service completely. You can use this opt-out feature if you don’t want to use the proposal service and don’t want your content to be collected. To know more, see [MIGs and MAGs](../50-Development/migs-and-mags-4c442af.md).

The sections below pertaining to each artifact mention the details of the data which will and which will not be a part of the knowledge base.



<a name="loioe5bd17fbb36242e0bf621a9e0953f9a0__section_r4g_lqz_jbc"/>

## Message Implementation Guidelines

The following information of MIGs will not be part of the knowledge base:

-   Textual documentation \(names, definitions, notes, summaries\) of all components, such as messages, nodes, code values, etc.

-   MIG codelists
-   Example values
-   User-defined XSD Patterns
-   User-defined XSD Asserts
-   User review information
-   Administrative data such as Created By, Modified By

All other information including the following will be a part of the knowledge base:

-   Node properties, such as cardinality and length

-   Selected code values \(without textual documentation\)
-   Qualification details



<a name="loioe5bd17fbb36242e0bf621a9e0953f9a0__section_jz4_cvz_jbc"/>

## Mapping Guidelines

The following information of MAGs will not be part of the knowledge base:

-   Textual documentation \(names, definitions, notes, summaries\) of all components, such as mapping elements, global parameters, shared code, code values, etc.

-   XSLT code of functions and XPath conditions explicitly marked as confidential
-   XSLT code of functions and XPath conditions containing global parameters
-   Status and status comments
-   Administrative data such as Created By, Modified By

All other information including the following will be a part of the knowledge base:

-   Mapping lines between source and target nodes

-   Constants
-   Code value mappings
-   XSLT code of functions and XPath conditions that are not marked confidential
-   XSLT code of shared code



<a name="loioe5bd17fbb36242e0bf621a9e0953f9a0__section_w3t_qwz_jbc"/>

## Custom Messages

The following information of custom messages will not be part of the knowledge base:

-   Textual documentation \(names, definitions, notes, summaries\) of all components, such as messages, nodes, code values, etc.

-   Administrative data such as Created By, Modified By

All other information including the following will be a part of the knowledge base:

-   Identification of message and codelists

-   Identification of all nodes and types
-   Identification of code values
-   Node properties, such as cardinality and length



<a name="loioe5bd17fbb36242e0bf621a9e0953f9a0__section_h3p_2yq_ndc"/>

## Custom Codelists

The following information of custom codelists will not be part of the knowledge base:

-   Textual documentation \(names, definitions, notes\) of all components, such as codelist and code values

-   Administrative data such as Created By, Modified By

All other information including the following will be a part of the knowledge base:

-   Identification of the custom codelist

-   Identification of code values

