<!-- loio42124f465fc0472a8ab0de30aa14edef -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Mapping Guidelines \(MAGs\)



A mapping guideline is the runtime artifact that you use in the mapping step of an integration application. This is used as a reference or guidance for implementing mapping in the integration application. By providing such an artifact, you simplify the mapping task for users who use messages that adhere to the A2A/B2B type system standards.

A Mapping Guideline \(MAG\) is based on a source and a target message implementation guideline. It demonstrates how the defined nodes at each side are mapped, describing all mapping elements in detail with definitions or notes and providing further instructions for the transformation, such as functions or code value mappings.



<a name="loio42124f465fc0472a8ab0de30aa14edef__section_cl4_ttt_d4b"/>

## Mapping Guidelines

The *Mapping Guidelines* tab displays an overview of all the MAGs that you've created. Filters are used to search and display MAGs based on various criteria. You can use the *Free text filter* search or the <span class="SAP-icons"></span> \(Extended filter\)at the top of the screen to specify your search criteria. The *Free text filter* search allows you to filter and display MAGs that match your search text. It can be used as a quick filter to match your search text against multiple attributes of your MAGs.

You can also choose <span class="SAP-icons"></span> \(Extended filter\)to filter MAGs based on specific criteria. You can use the required filter fields to list MAGs that match your query. You can also customize the filter bar by choosing *Filters*. You can expand or collapse the filter area using *Show Filter Bar* or *Hide Filter Bar*.

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
</table>



<a name="loio42124f465fc0472a8ab0de30aa14edef__section_end_s4w_qsb"/>

## Code Value Mapping

The *Code Value Mapping* tab displays the list of global code value mappings that can be used in your mapping guideline. Choose and open a code value maping to see the source and target code values. You can also filter for a specific code value using the *Free Text Filter* <span class="SAP-icons"></span> \(Extended filter\) provided at the column level. This serves as an efficient way to filter through when there are many code values.

Choose *Edit* if you want to modify the target code values.

These global code value mappings consist of only the code values that were selected in the source MIG. To add additional source code values from the underlying code list, choose *Add* and select

-   *One source value* if you want to add only one value from the source code list.

-   *All remaining source values* if you want to add all the values that were previously unselected the source code list.



You can:

-   [Creating a New Mapping Guideline](creating-a-new-mapping-guideline-a42920e.md)
-   [Working with a Mapping Guideline \(MAG\)](working-with-a-mapping-guideline-mag-0803ca6.md)

