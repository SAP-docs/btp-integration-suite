<!-- loiof9f2bab3ff3a4d86863199f6531ee695 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Message Implementation Guidelines \(MIGs\)



Message implementation guideline, also referred to as MIG, is used as the source or target in a mapping guideline \(MAG\) of SAP Integration Suite. This is created using one of the messages in the type system that is relevant to your scenario as the template.

The MIG contains all the information for implementing a customized message interface. SAP Integration Suite uses the message in a type system as a starting point to ensure that you don't have to refer to any additional documents to implement the interface. By providing a MIG, you ensure that all users who are involved in the process of implementing the interface have a clear understanding of the guidelines.



<a name="loiof9f2bab3ff3a4d86863199f6531ee695__section_ejb_gxt_d4b"/>

## Filtering MIGs

The *Message Implementation Guidelines* screen displays an overview of all the MIGs that you've created. Filters are used to search and display MIGs based on various criteria. You can use the *Free text filter* search or the <span class="SAP-icons-V5"></span> \(Extended filter\)at the top of the screen to specify your search criteria. The *Free text filter* search allows you to filter and display MIGs that match your search text. It can be used as a quick filter to match your search text against multiple attributes of your MIGs.

You can also choose <span class="SAP-icons-V5"></span> \(Extended filter\)to filter MIGs based on specific criteria. You can use the required filter fields to list MIGs that match your query. You can also customize the filter bar by choosing *Filters*. You can expand or collapse the filter area using *Show Filter Bar* or *Hide Filter Bar*.

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

MIG Name

</td>
<td valign="top">

The Name of the MIG provided in the *General Information* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Summary

</td>
<td valign="top">

The Summary of the MIG provided in the *Documentation* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

MIG Version

</td>
<td valign="top">

The Version of the MIG provided in the *General Information* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Status

</td>
<td valign="top">

The Status of the MIG provided in the *General Information* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Type System

</td>
<td valign="top">

The Type System of the MIG provided in the *General Information* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Type System Version

</td>
<td valign="top">

The Type System Version of the MIG provided in the *General Information* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Message Type

</td>
<td valign="top">

The Message Type of the MIG provided in the *General Information* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Created By

</td>
<td valign="top">

The unique identifier of the user who created the MIG. It is available in the *Administrative Data* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Created Between

</td>
<td valign="top">

The date range during which the MIG was created.

</td>
</tr>
<tr>
<td valign="top">

Modified By

</td>
<td valign="top">

The unique identifier of the user who modified the MIG. It is available in the *Administrative Data* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Modified Between

</td>
<td valign="top">

The date range during which the MIG was modified.

</td>
</tr>
<tr>
<td valign="top">

Last Imported By

</td>
<td valign="top">

The unique identifier of the user who last imported the MIG. It is available in the *Administrative Data* section of the *Overview* tab.

</td>
</tr>
<tr>
<td valign="top">

Last Imported Between

</td>
<td valign="top">

The date range during which the MIG was imported.

</td>
</tr>
</table>

You can also view the version history of a specific message implementation guideline. Choose the *History* button provided below the version details of a MIG in the *Message Implementation Guidelines* page. The resulting screen would display the following version history details of the MIG:

-   *Version*: This column displays the version numbers of the MIG

-   *Status*: This column displays the status of each version of the MIG. There is always only one active version of a MIG. The previous version of the active MIG will be in draft status and all other MIGs versions before that will be deprecated.

-   *Name*: Displays the name of the MIG in each version.

-   *Modified On*: Displays the last modified timestamp.

-   *Modified By*: Displays the unique identifier of the user who modified the MIG.

-   *Last Imported On*: Displays the last imported date and time.

-   *Last Imported By*: Displays the unique identifier of the user who imported the MIG.
-   *Imported*: This column lets you know if the MIG is imported or not.
-   The action <span class="SAP-icons-V5"></span> button allows you to copy, migrate or compare your MIG.



Here are the next steps for you:

-   [Creating a New Message Implementation Guideline](creating-a-new-message-implementation-guideline-b894de0.md)
-   [Working with a Message Implementation Guideline](working-with-a-message-implementation-guideline-9d1c1df.md)

