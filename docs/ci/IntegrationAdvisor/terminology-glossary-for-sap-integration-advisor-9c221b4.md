<!-- loio9c221b48799a4ce59367b0e3367f5a8f -->

# Terminology & Glossary for SAP Integration Advisor


<table>
<tr>
<th valign="top">

Term

</th>
<th valign="top">

Definition

</th>
</tr>
<tr>
<td valign="top">

Type System

</td>
<td valign="top">

A "Type System" is an independent system of data description format of reusable message and data types, which is based on a combination of:

-   Responsible agency
-   Syntax rules for syntax representation
-   Schema notation and definition
-   Methodology for modeling, naming, and structuring of complete messages
-   Template library

Only a single agency \(organization ANSI ASC X12 for the Type System ASC X12 or organization SAP SE for the Type System SAP IDoc\) is responsible for the development and maintenance of the syntax, concept \(methodology\) and library.

</td>
</tr>
<tr>
<td valign="top">

Message Implementation Guideline \(MIG\)

</td>
<td valign="top">

A Message Implementation Guideline \(also called as Message Guideline or MIG\) is a detailed documentation of a A2A/B2B message type considering just these aspects and constraints for fulfilling the needs of the user's business purpose in a given business context.

</td>
</tr>
<tr>
<td valign="top">

Mapping Guideline \(MAG\)

</td>
<td valign="top">

A Mapping Guideline \(also called as a MAG\) is an artifact that you can directly use in the mapping step of an integration application.

A Mapping Guideline \(MAG\) is based on a source and a target message implementation guideline. It demonstrates how the defined nodes at each side are mapped, describing all mapping elements in detail with definitions or notes and providing further instructions for the transformation, such as functions or code value mappings.

</td>
</tr>
<tr>
<td valign="top">

Business Context

</td>
<td valign="top">

The formal description of a specific business circumstance as identified by the values of a set of context categories, allowing different business circumstances to be uniquely distinguished.

The business context is a very important part of the MIG. It labels the MIG so that the system can give you an appropriate proposal based on the defined business context and will be used for statistical information, which will be provided in future releases of IA. Therefore, at least one business context value must be set. IA provides for setting the own business context and the business partner's business context five different business context categories with a list of business context values. These business context categories are:

-   *Business Process* - In describing a business situation, generally the most important aspect of that situation is the business activity being conducted. Business process context provides a way to unambiguously identify the business activity.

-   *Product Classification* - It describes those aspects of a business situation related to the goods or services being exchanged by, or otherwise manipulated, or concerned, in the business process.
-   *Industry Classification* - It provides a description of the industry or sub-industry in which the business process takes place.
-   *Geo Political*- Allows the description of those aspects of the business context that are related to region, nationality, or geographically based cultural factors. The starting point of the geo political context category is country.
-   *Business Process Role* - It describes those aspects of a business situation that are specific to an actor or actors within the business process.

The accuracy of the proposal depends on the selected number of business context categories and business context values. As more business context categories and values you selected as tighter will be the proposal.

</td>
</tr>
<tr>
<td valign="top">

Message

</td>
<td valign="top">

A message is used to describe business document transactions between two business partners in electronic manner.

</td>
</tr>
<tr>
<td valign="top">

Complex Types

</td>
<td valign="top">

Reusable complex structures that are used for assembling a message. Each complex type has a complex structure of child elements for expressing the properties of a complex object such as *Partner*, *Location* or *Address*.

</td>
</tr>
<tr>
<td valign="top">

Simple Types

</td>
<td valign="top">

Reusable simple types are defining the characteristics and properties of leaf elements that are used for carrying data in an instance

</td>
</tr>
<tr>
<td valign="top">

Codelists

</td>
<td valign="top">

A codelist is a stable collection of code values that’s maintained by a responsible agency. Codelists can be used in several ways:

1.  A fixed list of commonly used acronyms and abbreviations that provides a common understanding of the names, meanings, or objects that are represented by code values; for example, the country codelist.

2.  Shorter representation and controlled list of methods, conditions, or rules, that provides the system further instruction for processing or validating data; for example, the status list, which tells if something is new or in progress.
3.  List of qualifying values that provide a more precise meaning to semantically generic elements in an interface; for example, the qualifiers for the generic group *Party* might be *seller* or *buyer*.

Codelists require consideration when you use them in MIGs, for the following reasons:

-   Code values must be mapped from the source side to the target side in a mapping guideline \(MAG\).

-   Code values are used as qualifiers that make MIG semantics more precise.
-   Code values are used when generating, processing, or validating payloads.



</td>
</tr>
<tr>
<td valign="top">

Qualifiers

</td>
<td valign="top">

The qualifier reference approach in IA supports the semantic qualification in a very efficient manner. The qualifier references bring both, the semantically generic elements and the leaf elements who provide the additional meaning by code values together. This new approach is very powerful, because it increases the understanding of customized interfaces in MIGs on business meaning level and furthermore, it significantly reduces the efforts in mappings.

</td>
</tr>
<tr>
<td valign="top">

Notes

</td>
<td valign="top">

Notes gives further details to the definition and meaning of a node. These details can be categorized by different kinds of notes, which describe usage scenarios, further constraints, a comment or a usage example.

The *Usage* category is used for specification of possible usages of a node.

The *Constraint* category is used to provide information about the qualifiers.

The *Example* category is used to provide example data.

The *Comment* category is used to provide addition information.

</td>
</tr>
</table>

