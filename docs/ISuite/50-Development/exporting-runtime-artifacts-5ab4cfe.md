<!-- loio5ab4cfe5ec724adda074c9773ea6b895 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Exporting Runtime Artifacts

Once you have created the Message Implementation Guidelines \(MIG\) and Mapping Guidelines \(MAG\), the next step is to use these artifacts in the integration solution to enable integrations with your business partner/s. Currently, SAP Integration Suite supports exporting runtime artifacts for and SAP Process Orchestration.

By exporting the runtime artifacts, the application automatically generates a number of schemes, scripts, and examples from a mapping guideline, including:

-   Schemes for **syntax conversion**, such as from EDI syntax to XML or vice versa

-   Schemes for precise **payload validation** against the rules and constraints defined in the message implementation guidelines
-   **Pre- and post-processing scripts** for presorting payloads or enriching them with additional required information for the mapping
-   Main mapping XSLT script
-   **Examples** for testing the artifacts in the runtime

    > ### Note:  
    > In the `<MIGName>_testdata_ICA.xml` file, for choice elements, some of the choice options are commented out to be XSD-valid. You can choose to change this in the xml file to have other elements uncommented or commented.


This automatic generation is a particularly enormous time saver, because without the application, all these schemes, scripts, or payloads must be created separately and manually.

> ### Note:  
> In SAP Process Orchestration mode not all artifacts are relevant and therefore only fewer artifacts are exported.

You can then import these runtime artifacts in either of these integration solutions and use them to implement your A2A/B2B integration scenario. To know more, see [Consuming Artifacts in Integration Flows](consuming-artifacts-in-integration-flows-a33a6c6.md)



<a name="loio5ab4cfe5ec724adda074c9773ea6b895__section_ggv_f2f_zhb"/>

## How to Export Runtime Artifacts?

1.  Access the Message Implementation Guideline \(MIG\) or the Mapping Guideline \(MAG\) section.
2.  Select the MIG or MAG in which you want to export the runtime artifacts.
3.  Choose <span class="SAP-icons"></span> and then choose *Export*.
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

    The MIG/MAG will be exported in a format where you can directly import them in SAP Cloud Integration.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *SAP Process Integration Runtime Artifacts*


    
    </td>
    <td valign="top">

    The MIG/MAG will be exported in a format where you can directly import them in SAP Process Integration.


    
    </td>
    </tr>
    </table>
    



<a name="loio5ab4cfe5ec724adda074c9773ea6b895__section_gp5_4mt_plb"/>

## How to consume Runtime Artifacts?

The SAP Integration Suite works with any kind of interface/API format; its automatically generated artifacts can be used in a variety of runtimes or implementations. Each different runtime has specific approaches, formats, pre-conditions, and implementation instructions. These must be considered, if the generated runtime artifacts are implemented into these runtimes and if the involved applications will be connected. SAP’s intention is to provide templates and mechanisms that accelerate the onboarding of the runtime artifacts into the diverse supported runtime systems such as

-   SAP Process Orchestration



<a name="loio5ab4cfe5ec724adda074c9773ea6b895__section_sxj_qxd_mmb"/>

## Change of XSD file name for EANCOM

There is now an unified naming convention for these Message XSDs for all messages from EDIFACT and EDIFACT subsets. Therefore, Message XSDs for an EANCOM MIG will have a new file name which will comply to this naming convention. The details of this naming convention is:


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

EDIFACT version. In case of subsets, the version of the parent EDIFACT will be considered. \(Corresponding to UNH \> S009 \> 0052 and 0054.\)



</td>
</tr>
<tr>
<td valign="top">

AssociationCode



</td>
<td valign="top">

Subset-specific code that identifies the Message Guideline. \(Corresponding to UNH \> S009 \> 0057.\)

> ### Note:  
> -   This is an optional part. It will be included into the XSD file name if the field *0057* contains either a *Fixed Value* or a single code value. Preference will be given to the *Fixed Value* set in the field.
> 
> -   If no unique value for *AssociationCode* is found in the MIG, the standard EDIFACT file name convention will be applied.



</td>
</tr>
</table>

> ### Note:  
> The old EANCOM naming convention is still supported. However, if there is an integration flow for EANCOM with old XSD files and you want to use Message XSD from the new SAP Integration Suite Export, then you would need to replace the older EANCOM files with the new UN-EDIFACT file in your EDI Flow Steps.

