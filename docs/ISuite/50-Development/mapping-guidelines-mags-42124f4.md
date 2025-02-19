<!-- loio42124f465fc0472a8ab0de30aa14edef -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Mapping Guidelines \(MAGs\)



A mapping guideline is the runtime artifact that you use in the mapping step of an integration application. This is used as a reference or guidance for implementing mapping in the integration application. By providing such an artifact, you simplify the mapping task for users who use messages that adhere to the A2A/B2B type system standards.

A Mapping Guideline \(MAG\) is based on a source and a target message implementation guideline. It demonstrates how the defined nodes at each side are mapped, describing all mapping elements in detail with definitions or notes and providing further instructions for the transformation, such as functions or code value mappings.



<a name="loio42124f465fc0472a8ab0de30aa14edef__section_cl4_ttt_d4b"/>

## Mapping Guidelines

The *Mapping Guidelines* tab displays an overview of all the MAGs that you've created.

The following buttons are provided in *Mapping Guidelines* tab.

-   *Create*: You can create a new MAG. To know more, see [Creating a New Mapping Guideline](creating-a-new-mapping-guideline-a42920e.md)

-   *Export*: You can export your mapping guidelines. To know more, see [Exporting MIG/MAG](exporting-mig-mag-c8bba26.md)
-   *Import*: You can import mapping guidelines into your tenant. To know more, see [Importing MIG/MAG](importing-mig-mag-7139aad.md)
-   *Update MAGs*: You can filter and update mapping guidelines in bulk. To know more, see

Filters are used to search and display MAGs based on various criteria. You can use the *Free text filter* search or the <span class="SAP-icons-V5"></span> \(Extended filter\)at the beginning of the screen to specify your search criteria. The *Free text filter* search allows you to filter and display MAGs that match your search text. It can be used as a quick filter to match your search text against multiple attributes of your MAGs.

You can also choose <span class="SAP-icons-V5"></span> \(Extended filter\)to filter MAGs based on specific criteria. You can use the required filter fields to list MAGs that match your query. You can also customize the filter bar by choosing *Filters*. You can expand or collapse the filter area using *Show Filter Bar* or *Hide Filter Bar*.

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

The Name of the MAG provided in the *General Information* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

MAG Version

</td>
<td valign="top">

The Version of the MAG provided in the *General Information* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Status

</td>
<td valign="top">

The Status of the MAG provided in the *General Information* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Source MIG Name

</td>
<td valign="top">

The Name of the source MIG provided in the *Source and Target MIGs* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Type System of Source MIG

</td>
<td valign="top">

The Type System of the source MIG provided in the *Source and Target MIGs* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Type System Version of Source MIG

</td>
<td valign="top">

The Type System version of the source MIG provided in the *Source and Target MIGs* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Message Type

</td>
<td valign="top">

The Message Type of the source MIG provided in the *Source and Target MIGs* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Target MIG Name

</td>
<td valign="top">

The Name of the target MIG provided in the *Source and Target MIGs* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Type System of Target MIG

</td>
<td valign="top">

The Type System of the target MIG provided in the *Source and Target MIGs* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Type System Version of Target MIG

</td>
<td valign="top">

The Type System version of the target MIG provided in the *Source and Target MIGs* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Message Type

</td>
<td valign="top">

The Message Type of the target MIG provided in the *Source and Target MIGs* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Created By

</td>
<td valign="top">

The unique identifier of the user who created the MAG. It is available in the *Administrative Data* section of the *Overview* tab.

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

The unique identifier of the user who modified the MAG. It is available in the *Administrative Data* section of the *Overview* tab.

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

The unique identifier of the user who last imported the MAG. It is available in the *Administrative Data* section of the *Overview* tab.

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

You can also view the version history of a specific mapping guideline. Choose *History* which you can find after the version details of a MAG in the *Mapping Guidelines* page. The resulting screen would display the following version history details of the MAG:

-   *Version*: This column displays the version numbers of the MAG

-   *Status*: This column displays the status of each version of the MAG. There is always only one active version of a MAG. The previous version of the active MAG will be in draft status and all other MAG versions before that will be deprecated.

-   *Name*: Displays the name of the MAG in each version.

-   *Modified On*: Displays the last modified timestamp.

-   *Modified By*: Displays the unique identifier of the user who modified the MAG.

-   *Last Imported On*: Displays the last imported date and time.

-   *Last Imported By*: Displays the unique identifier of the user who imported the MAG.
-   *Imported*: This column lets you know if the MAG is imported or not.
-   <span class="SAP-icons-V5"></span> \(Action\) allows you to copy, migrate or compare your MAG.

The *Code Value Mapping* tab displays the list of global code value mappings that can be used in your mapping guideline. To know more, see [Global Code Value Mapping](global-code-value-mapping-fd1d3ff.md).



You can:

-   [Creating a New Mapping Guideline](creating-a-new-mapping-guideline-a42920e.md)
-   [Working with a Mapping Guideline \(MAG\)](working-with-a-mapping-guideline-mag-0803ca6.md)

