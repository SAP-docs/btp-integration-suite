<!-- loio957de135ee4c4d5d9778355d76760572 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Review and Adjust ISA-M Settings

Settings include the SAP Integration Solution Advisory Methodology \(ISA-M\) master data. This data acts as the initial setup for completing the integration assessment.

For more information, see: [SAP Integration Solution Advisory Methodology](sap-integration-solution-advisory-methodology-a2e17f3.md)

Reviewing and adjusting the ISA-M settings is the task of the enterprise architect \(see [Personas for Integration Assessment](60-Security/personas-for-integration-assessment-5df5af1.md)\).

Go to the *Settings* section to inspect the available ISA-M master data predefined by SAP or to adjust the settings by adding your own data.

> ### Note:  
> When you've finished editing an entity, select *Done*.
> 
> You can also define new entities \(for example, a new integration domain\). To do this, click the *\+* icon \(*Create*\).
> 
> You can also delete entities that aren't relevant for you. To do this, select the entity and select :wastebasket: \(*Delete*\).

> ### Note:  
> SAP Standard master data is represented in the application as *Maintained by SAP*. This represents that the associated data is pre-defined and loaded by SAP.

The following settings exist in the system:



<a name="loio957de135ee4c4d5d9778355d76760572__section_ny2_bmj_psb"/>

## Integration Domains

Integration domains provide the entry point into ISA-M and can be used as a “big picture” for integration. They describe typical areas in a hybrid landscape where integration is needed. Integration domains are technology agnostic and can therefore also help in creating a blueprint for a hybrid integration platform consisting of multiple integration services/technologies \(SAP or non-SAP\).

See: [Integration Domains](integration-domains-e8360d2.md)



<a name="loio957de135ee4c4d5d9778355d76760572__section_pdn_2mj_psb"/>

## Integration Styles

An integration style describes a basic category or type of integration, for example, process integration or the integration with things.

Each integration style has specific characteristics. You can refine each integration style with use-case patterns.

> ### Example:  
> When you select the *Process Integration* style, you find the following use case patterns:
> 
> -   B2G Integration
> 
> -   A2A Integration
> 
> -   Master Data Integration
> 
> -   B2B Integration

See: [Integration Styles and Integration Use Case Patterns](integration-styles-and-integration-use-case-patterns-770909d.md)



<a name="loio957de135ee4c4d5d9778355d76760572__section_p42_tmj_psb"/>

## Integration Use Case Patterns

You can refine each integration style with use case patterns that describe frequently found integration use cases in enterprise landscapes. You can do an assessment of your integration architecture by adding the integration use case patterns that are relevant for your organization or that you want to further evaluate.

See: [Integration Styles and Integration Use Case Patterns](integration-styles-and-integration-use-case-patterns-770909d.md)



<a name="loio957de135ee4c4d5d9778355d76760572__section_sm3_wmj_psb"/>

## Integration Areas

An integration area is a combination of integration domains and integration styles.

For example, the integration pattern **IP-3** defines the combination of the *cloud to cloud* domain with the *process integration* style.



<a name="loio957de135ee4c4d5d9778355d76760572__section_gmz_zmj_psb"/>

## Key Characteristics

Key characteristics are criteria that help enterprise architects and integration architects to map integration styles to relevant capabilities of integration technologies.

When you inspect the relevant integration technologies at a later step, Integration Assessment defines the level of support for the key characteristic for each technology \(indicated by a recommendation degree\).

For each key characteristic, the following attributes are displayed:

****


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

 

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Name of key characteristic

</td>
</tr>
<tr>
<td valign="top">

*Description*

</td>
<td valign="top">

Description of key characteristic

</td>
</tr>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

Possible values are:

-   *Multi*

    If you can give many answers to an associated question in a questionnaire.

-   *Single*

    If you can answer an associated question in a questionnaire with Yes or No.




</td>
</tr>
<tr>
<td valign="top">

*Key Characteristic Group*

</td>
<td valign="top">

Logical grouping of Key Characteristics. The possible values are:

-   Connectivity

-   Integration Use Cases
-   Metadata Management
-   Monitoring and Operations
-   Transformations



</td>
</tr>
<tr>
<td valign="top">

*Key Characteristic Values*

</td>
<td valign="top">

The basis for predefined answers in a questionnaire.

</td>
</tr>
</table>

See: [Key Characteristics](key-characteristics-c16258e.md)



<a name="loio957de135ee4c4d5d9778355d76760572__section_mgy_cnj_psb"/>

## Deployment Models

Deployment means the hosting of software. Cloud services can be provided in different ways. The deployment model depends on the application and integration technology.

The following deployment models are predefined:

-   Hybrid

-   On-premise

-   Private cloud

-   Public cloud


Choose the *Domain Determination* tab to find out which integration domain is related to a combination of source and target deployment models.



<a name="loio957de135ee4c4d5d9778355d76760572__section_r2l_lnj_psb"/>

## Questionnaires

The questionnaire is a list of questions that is used during the request process. Integration Assessment differentiates between questionnaires predefined by SAP and custom questionnaires. There are two groups of questionnaires: interface request questionnaires \(technical perspective\), and business solution request questionnaires \(business perspective\).

To review the predefined questionnaires, go to *Settings* \> *Questionnaires*.

When you select a questionnaire, under *Properties*, the following metadata is displayed:

****


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Name of the questionnaire

</td>
</tr>
<tr>
<td valign="top">

*Description*

</td>
<td valign="top">

Short description of the purpose

</td>
</tr>
<tr>
<td valign="top">

*Style*

</td>
<td valign="top">

Relevant integration style

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Shows whether the questionnaire is active

</td>
</tr>
</table>

Under *Sections*, you can find a list of questions.

For each question, the following attributes are displayed:


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*Position*

</td>
<td valign="top">

Position of the question in the questionnaire

</td>
</tr>
<tr>
<td valign="top">

*Question*

</td>
<td valign="top">

The text of the question

</td>
</tr>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

Possible values are:

-   *Multi Select*

    An associated question can have more than one answer.

-   *Single Select*

    An associated question can only be answered with Yes or No.




</td>
</tr>
<tr>
<td valign="top">

*Answer Source*

</td>
<td valign="top">

Source where to retrieve the answer to the question.

If *Key Characteristic* is shown, the possible answers to the question are given by the definition of the key characteristic.

See: [Key Characteristics](key-characteristics-c16258e.md)

</td>
</tr>
</table>

Select a question to see more information about the answer options.

You can also add your own questionnaires.

Depending on the *Request Type* parameter, you can define two different types of questionnaires:


<table>
<tr>
<th valign="top">

Request Type

</th>
<th valign="top">

Type of Questionnaire

</th>
</tr>
<tr>
<td valign="top">

*Integration Request*

</td>
<td valign="top">

Questionnaire for a specific integration request.

Use this kind of questionnaire to guide the user through the creation of an interface request.

</td>
</tr>
<tr>
<td valign="top">

*Business Solution Request*

</td>
<td valign="top">

Questionnaire for a specific business solution request

Use this kind of questionnaire to guide the user through the creation of a business solution request.

</td>
</tr>
</table>



<a name="loio957de135ee4c4d5d9778355d76760572__section_bkj_ys1_rwb"/>

## Content Life Cycle

The Content Life Cycle update gives you the ability to incorporate relevant changes to the latest standard content, delivered by SAP, into your existing SAP standard content. You can select/deselect the listed updates based on your requirements and apply them as the latest version of your dataset.

See: [Update Content Maintained by SAP](update-content-maintained-by-sap-06581f4.md)

**Related Information**  


[Questionnaires](questionnaires-da3f7d8.md "")

[Create a Questionnaire](create-a-questionnaire-4dc1b9c.md "")

