<!-- loio5ab4cfe5ec724adda074c9773ea6b895 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Exporting Runtime Artifacts

Exporting Runtime Artifacts for Integration Solutions.

> ### Note:  
> Currently, SAP Integration Suite supports exporting runtime artifacts for and SAP Process Orchestration.
> 
> To know more about these runtime artifacts, refer to the blog [The Mapping Artifacts and their Purpose](https://community.sap.com/t5/technology-blogs-by-sap/integration-advisor-the-mapping-runtime-artifacts-and-their-purpose/ba-p/13426356).

By exporting the runtime artifacts, the application automatically generates a number of schemes, scripts, and examples from a mapping guideline, including:

-   Schemes for **syntax conversion**, such as from EDI syntax to XML or from XML to EDI syntax

-   Schemes for precise **payload validation** against the rules and constraints defined in the message implementation guidelines
-   **Pre- and post-processing scripts** for presorting payloads or enriching them with additional required information for the mapping
-   Main mapping XSLT script
-   **Examples** for testing the artifacts in the runtime

    > ### Note:  
    > In the `<MIGName>_testdata_ICA.xml` file, for choice elements, some of the choice options are commented out to be XSD-valid. You can choose to change this in the xml file to have other elements uncommented or commented.


This automatic generation is an enormous time saver because without the application, all these schemes, scripts, or payloads must be created separately and manually.

> ### Note:  
> In SAP Process Orchestration mode
> 
> -   Not all artifacts are relevant and therefore only fewer artifacts are exported.
> 
> -   Exporting MIGs and MAGs based on Tradacoms is not supported \(due to significant structural differences of the Tradacoms message structures\).

You can then import these runtime artifacts in either of these integration solutions and use them to implement your A2A/B2B integration scenario. See [Consuming Artifacts in Integration Flows](consuming-artifacts-in-integration-flows-a33a6c6.md).



<a name="loio5ab4cfe5ec724adda074c9773ea6b895__section_kzc_1zj_32c"/>

## How to Export XSD File from EDI Type System

You can now directly export Message Types of EDI Type Systems as an XSD file, eliminating the need to create a Message Implementation Guideline \(MIG\). This streamlined process saves time and effort. Follow the following procedure to know more:

1.  Login to your application.
2.  Navigate to the *Type Systems* tab from the left pane.
3.  Open the Type System containing the Message Type you want to export as an XSD file.
4.  Navigate to the *Messages* tab and open the specific version of the message type you want to export .
5.  Choose *Download XSD* to download this message type in an XSD file format.



<a name="loio5ab4cfe5ec724adda074c9773ea6b895__section_ggv_f2f_zhb"/>

## How to Export Runtime Artifacts?

1.  Access the Message Implementation Guideline \(MIG\) or the Mapping Guideline \(MAG\) section.
2.  Select the MIG or MAG in which you want to export the runtime artifacts.
3.  Choose <span class="SAP-icons-V5"></span> and then choose *Export*.
4.  You see two options for exporting the artifacts. Choose the appropriate option based on your needs.


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP Cloud Integration Runtime Artifacts*
    
    </td>
    <td valign="top">
    
    The MIG/MAG is exported in a format where you can directly import them in SAP Cloud Integration.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP Process Integration Runtime Artifacts*
    
    </td>
    <td valign="top">
    
    The MIG/MAG is exported in a format where you can directly import them in SAP Process Integration.
    
    </td>
    </tr>
    </table>
    



<a name="loio5ab4cfe5ec724adda074c9773ea6b895__section_gp5_4mt_plb"/>

## How to consume Runtime Artifacts?

The SAP Integration Suite works with any kind of interface/API format; its automatically generated artifacts can be used in a variety of runtimes or implementations. Each different runtime has specific approaches, formats, pre-conditions, and implementation instructions. These must be considered, if the generated runtime artifacts are implemented into these runtimes and if the involved applications will be connected. SAP’s intention is to provide templates and mechanisms that accelerate the onboarding of the runtime artifacts into the diverse supported runtime systems such as

-   SAP Process Orchestration



<a name="loio5ab4cfe5ec724adda074c9773ea6b895__section_sxj_qxd_mmb"/>

## Change of XSD file name for EANCOM

There's now a unified naming convention for these Message XSDs for all messages from EDIFACT and EDIFACT subsets. Therefore, Message XSDs for an EANCOM MIG will have a new file name which will comply to this naming convention. The details of this naming convention is:


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

New Naming Convention

</td>
<td valign="top">

UN-EDIFACT\_<MessageType\>\_<Version\>\_<AssociationCode\>.xsd

> ### Example:  
> -   UN-EDIFACT\_APERAK\_D01B.xsd
> 
> -   UN-EDIFACT\_APERAK\_D01B\_EAN003.xsd



</td>
</tr>
<tr>
<td valign="top">

MessageType

</td>
<td valign="top">

Type of message on which the MIG is based on. \(Corresponding to UNH \> S009 \> 0065.\)

</td>
</tr>
<tr>
<td valign="top">

Version

</td>
<td valign="top">

EDIFACT version. In case of subsets, the version of the parent EDIFACT is considered. \(Corresponding to UNH \> S009 \> 0052 and 0054.\)

</td>
</tr>
<tr>
<td valign="top">

AssociationCode

</td>
<td valign="top">

Subset-specific code that identifies the Message Guideline. \(Corresponding to UNH \> S009 \> 0057.\)

> ### Note:  
> -   This is an optional part. It's included into the XSD file name if the field *0057* contains either a *Fixed Value* or a single code value. Preference will be given to the *Fixed Value* set in the field.
> 
> -   If no unique value for *AssociationCode* is found in the MIG, the standard EDIFACT file name convention will be applied.



</td>
</tr>
</table>

> ### Note:  
> The old EANCOM naming convention is still supported. However, if there is an integration flow for EANCOM with old XSD files and you want to use Message XSD from the new SAP Integration Suite Export, then you would need to replace the older EANCOM files with the new UN-EDIFACT file in your EDI Flow Steps.



<a name="loio5ab4cfe5ec724adda074c9773ea6b895__section_x2t_2jl_4xb"/>

## Extended Namespace Support for MIGs

Few pointers to be considered for your MIGs for SAP S/4HANA SOAP type systems and Custom Messages created before June 2023.

> ### Note:  
> If your MIG is affected, there's a warning icon for the root node in the MIG editor.

The application was extended in June 2023 to support namespace handling. Earlier, namespace prefixes were only allowed at the root node level and these prefixes were removed as part of internal processing. The recent addition of GS1 XML to our Type System library has enabled the support of XML elements and attributes which are a part of the namespace and require a namespace declaration.

To elaborate on the changes, a node now carries its namespace prefix in the internal payload format if it's required by the message standard. In other words, the namespace prefix is no longer removed as part of the internal processing.

The change is relevant for the message types of the following type system:

-   S/4HANA Cloud SOAP

-   S/4HANA On-Premise SOAP
-   Custom Messages \(if the message is defined in a namespace\)

In case your MIG is affected by this change, you need to make sure to follow the following guidelines \(particularly for the first new Export of Runtime Artifacts after the change date\). When you update your integration flow, you need to replace all the files using the latest export of runtime artifacts. You can't update/replace only a few files as a mix of old and updated artifacts causes compatibility issues.

You might come across the following scenarios while trying to update your integration flow:

-   Your MIG uses XSD Assertions and, the XPath of any of your MIG Assertions uses an absolute path starting from the root node.

    -   If this is the case, you need to change the XPath of your Assertion to include the namespace prefix of the root node.

    -   Or use a relative XPath starting from the level where you've defined the XSD Assertion.

-   •Your integration flow has an additional flow step within the internal processing and this flow step defines an absolute XPath including the root node.
    -   If so, you also need to add the root node namespace prefix to this XPath.


-   Your integration flow has an additional flow step within the internal processing and this flow step executes an additional processing/transformation \(like a Groovy or XSLT script\).
    -   If so, you need to check if your script needs to be updated as well.





<a name="loio5ab4cfe5ec724adda074c9773ea6b895__section_jpx_kgq_1fc"/>

## Use Full or Reduced Message XSD File

You can decide if you want to use the full or the reduced message XSD file in our message implementation guideline.

> ### Note:  
> This property only applies to EDI type systems \(for example, `ASC X12`, `UN/EDIFACT`, `ODETTE` or `TRADACOMS`\).

1.  Open your message implementation guideline and go to the tab *Runtime Context*.

2.  In the section *EDI Flat File*, you can choose between the following options for property *Use complete Message XSD in EDI Flow Steps*:

    -   *true \(Default\)*: The XSD contains all segments from the message type, independent of the MIG.

        With this option, you can avoid unexpected conversion errors in the EDI-To-XML-Conversion flow step.

    -   *false*: The XSD contains only the segments from the message type that are also selected in the MIG.

        With this option, unexpected segments in the EDI payload automatically fail the EDI payload validation in the EDI Splitter flow step and can be used to produce a negative acknowledgment.


    > ### Note:  
    > For all new message implementation guidelines, the default value of this property is *true*.
    > 
    > However, for compatibility reasons, all message implementation guidelines created before May 2025 receive the value *false*.

3.  Save your changes.

