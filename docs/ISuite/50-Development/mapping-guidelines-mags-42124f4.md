<!-- loio42124f465fc0472a8ab0de30aa14edef -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Mapping Guidelines \(MAGs\)

Learn what mapping guidelines are and how to work with the mapping guideline page.



Mapping guidelines are runtime artifacts that you use in the mapping step of an integration application. They're used as reference or guidance for implementing mapping in the integration application. By providing such an artifact, you simplify the mapping task for users who use messages that adhere to the A2A/B2B type system standards.

Mapping guidelines are based on a source and a target message implementation guideline. They demonstrate how the defined nodes at each side are mapped, describing all mapping elements in detail with definitions or notes and providing further instructions for the transformation, such as functions or code value mappings.



## Types of Mapping Guidelines

You can create the following types of MAGs:

-   **Standard Graphical MAGs** serve as the foundation for your mapping guidelines. They contain the core mapping rules and instructions that apply to all users. Standard MAGs are used as the default or standard mapping guidelines for your organization.

-   **Overlay Graphical MAGs**: Overlay MAGs, on the other hand, allow you to create customized mapping guidelines that build upon the Standard MAGs. These overlays enable you to tailor mapping rules and instructions for specific use cases, projects, or user groups. Overlay MAGs provide flexibility and adaptability, ensuring that your mapping guidelines remain relevant and effective in diverse contexts.

-   **XSLT MAGs** differ from standard graphical MAGs due to their mapping source: As opposed to graphical MAGs, in which source nodes are dragged towards the target node to create a mapping, for XSLT MAGs, you upload an XSLT file that contains the finished mapping definition.




<a name="loio42124f465fc0472a8ab0de30aa14edef__section_cl4_ttt_d4b"/>

## Mapping Guidelines Tab



### Global Actions

The *Mapping Guidelines* tab displays an overview of all the MAGs that you've created.

In the tab, you can perform the following actions for any selected mapping guideline:

-   *Create*: Create a new mapping guideline, either *Graphical MAG: Standard*, *Graphical MAG: Overlay*, or *XSLT MAG*. See [Creating Mapping Guidelines](creating-mapping-guidelines-725d8b3.md).

-   *Export*: Export your mapping guideline. See [Exporting MIG/MAG](exporting-mig-mag-c8bba26.md).
-   *Import*: Import mapping guidelines to your tenant. See [Importing MIG/MAG](importing-mig-mag-7139aad.md).
-   *Mass-Update MAGs*: Filter and update mapping guidelines in bulk. See [Updating Mapping Guidelines](updating-mapping-guidelines-655ceb1.md).



### Search and Filter

Filters are used to search and display MAGs based on various criteria. You can use the *Free text filter* search or the <span class="SAP-icons-V5"></span> \(Extended filter\) at the beginning of the screen to specify your search criteria. The *Free text filter* search allows you to filter and display MAGs that match your search text. It can be used as a quick filter to match your search text against multiple attributes of your MAGs.

You can also choose <span class="SAP-icons-V5"></span> \(Extended filter\) to filter MAGs based on specific criteria. You can use the required filter fields to list MAGs that match your query. You can also customize the filter bar by choosing *Filters*. You can expand or collapse the filter area using *Show Filter Bar* or *Hide Filter Bar*.

**Filter Criteria**


<table>
<tr>
<th valign="top">

Filter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

MAG Name

</td>
<td valign="top">

The name of the MAG provided under *Overview* \> *General Information*.

</td>
</tr>
<tr>
<td valign="top">

MAG Version

</td>
<td valign="top">

The version of the MAG provided under *Overview* \> *General Information*.

</td>
</tr>
<tr>
<td valign="top">

Status

</td>
<td valign="top">

The status of the MAG provided under *Overview* \> *General Information*.

</td>
</tr>
<tr>
<td valign="top">

Source MIG Name

</td>
<td valign="top">

The name of the source MIG provided under *Overview* \> *Source and Target MIGs*.

</td>
</tr>
<tr>
<td valign="top">

Type System of Source MIG

</td>
<td valign="top">

The type system of the source MIG provided under *Overview* \> *Source and Target MIGs*.

</td>
</tr>
<tr>
<td valign="top">

Type System Version of Source MIG

</td>
<td valign="top">

The type system version of the source MIG provided under *Overview* \> *Source and Target MIGs*.

</td>
</tr>
<tr>
<td valign="top">

Message Type

</td>
<td valign="top">

The Message Type of the source MIG provided under *Overview* \> *Source and Target MIGs*.

</td>
</tr>
<tr>
<td valign="top">

Target MIG Name

</td>
<td valign="top">

The Name of the target MIG provided under *Overview* \> *Source and Target MIGs*.

</td>
</tr>
<tr>
<td valign="top">

Type System of Target MIG

</td>
<td valign="top">

The Type System of the target MIG provided under *Overview* \> *Source and Target MIGs*.

</td>
</tr>
<tr>
<td valign="top">

Type System Version of Target MIG

</td>
<td valign="top">

The Type System version of the target MIG provided under *Overview* \> *Source and Target MIGs*.

</td>
</tr>
<tr>
<td valign="top">

Message Type

</td>
<td valign="top">

The Message Type of the target MIG provided under *Overview* \> *Source and Target MIGs*.

</td>
</tr>
<tr>
<td valign="top">

Created By

</td>
<td valign="top">

The unique identifier of the user who created the MAG. This information is available under *Overview* \> *Administrative Data*.

</td>
</tr>
<tr>
<td valign="top">

Created Between

</td>
<td valign="top">

The date range during which the MAG was created.

</td>
</tr>
<tr>
<td valign="top">

Modified By

</td>
<td valign="top">

The unique identifier of the user who modified the MAG. This information is available under *Overview* \> *Administrative Data*.

</td>
</tr>
<tr>
<td valign="top">

Modified Between

</td>
<td valign="top">

The date range during which the MAG was modified.

</td>
</tr>
<tr>
<td valign="top">

Last Imported By

</td>
<td valign="top">

The unique identifier of the user who last imported the MAG. This information is available under *Overview* \> *Administrative Data*.

</td>
</tr>
<tr>
<td valign="top">

Last Imported Between

</td>
<td valign="top">

The date range during which the MAG was imported.

</td>
</tr>
</table>



### History

You can also view the version history of a specific mapping guideline. Choose *History* which you can find after the version details of a MAG in the *Mapping Guidelines* page. The resulting screen would display the following version history details of the MAG:

-   *Version*: This column displays the version numbers of the MAG

-   *Status*: This column displays the status of each version of the MAG. There's always only one active version of a MAG. The previous version of the active MAG is in draft status and all other MAG versions before that are deprecated.

-   *Name*: Displays the name of the MAG in each version.

-   *Modified On*: Displays the last modified timestamp.

-   *Modified By*: Displays the unique identifier of the user who modified the MAG.

-   *Last Imported On*: Displays the last imported date and time.

-   *Last Imported By*: Displays the unique identifier of the user who imported the MAG.
-   *Imported*: This column lets you know if the MAG is imported or not.
-   <span class="SAP-icons-V5"></span> Action allows you to copy, migrate, or compare your MAG.



### Code Value Mapping

The *Code Value Mapping* tab displays the list of global code value mappings that you can use in your mapping guideline. See [Global Code Value Mappings](global-code-value-mappings-fd1d3ff.md).

**Related Information**  


[Creating Mapping Guidelines](creating-mapping-guidelines-725d8b3.md "Before you create a new mapping guideline (MAG), you need to decide on the mapping method that you want to use.")

[Working with Mapping Guidelines \(MAGs\)](working-with-mapping-guidelines-mags-0803ca6.md "Learn how to work with mapping guidelines, also known as MAGs.")

