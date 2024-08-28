<!-- loio06581f4409814723823ed4bb03218fa3 -->

# Content Life Cycle

Incorporate new versions of standard content into your dataset.

At the time of onboarding, the latest available SAP standard content will be available for usage. As and when new version of SAP standard content is released, you have the flexibility to update to the latest version depending on your business needs.

> ### Example:  
> Recommendation Degree 'Not Supported / Not Relevant' is assigned to to Key Characteristic Patterns relevant for the Data Integration Style. After assigning the recommendation degree, a new version of SAP standard content is released. If the standard content is updated to the latest version, it will affect the assessment result. Since the update will impact the existing scenario, you can choose to retain the old version.

Every time a new version of SAP standard content is released, you can choose which changesets to update by selecting or deselecting it. Selecting a changeset will include it and not selecting a changeset will remove it and trigger potential cleanup actions.

> ### Example:  
> Not selecting a "remove action" will trigger the referred content to be not SAP managed any longer.

> ### Note:  
> If you are an old customer and new version of standard content has been updated after your onboarding, you will be able to see *Content Life Cycle* in the left navigation based on a rule. Only the personas *Integration Architect* and *Administrator* will have the rights for "Update".

****


<table>
<tr>
<th valign="top">

Header

</th>
<th valign="top">

Meaning

</th>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

The type of Update. Possible values are:

-   New - New Content

-   Update - Update of existing content

-   Delete - Deletion of old content




</td>
</tr>
<tr>
<td valign="top">

Mandatory For Update

</td>
<td valign="top">

Signifies if the changeset is mandatory if you plan to update it. Possible values are Yes/No.

</td>
</tr>
<tr>
<td valign="top">

Available For Update

</td>
<td valign="top">

Signifies if the changeset is available for update. Possible values are Yes/No.

</td>
</tr>
</table>



<a name="loio06581f4409814723823ed4bb03218fa3__section_xnt_kqk_lyb"/>

## Notification for outdated ISA-M version

To get notified about the content updates delivered by SAP, as an Administrator directly in the tool.

1.  Click on the *Notification* button \(bell icon\) in the shell bar. The badge shows the number of notifications available.
2.  If there is newer content available, the title is displayed as *New Content Available*. The description is displayed as *A newer version of the content maintained by SAP is available for update.*
3.  To view the content updates, click on *View Updates*. The *Content Life Cycle* page with new content is displayed.



<a name="loio06581f4409814723823ed4bb03218fa3__section_ikd_bck_lwb"/>

## Versioning

When there is more than one version of the standard content released, you cannot directly upgrade to the latest version. You will only be able to upgrade to the next version.

> ### Example:  
> If the current version is 1.1, update version is 1.2 and the latest version is 1.3, you will only be able to update first to 1.2 and then to 1.3. You cannot update directly to the latest version.



<a name="loio06581f4409814723823ed4bb03218fa3__section_kpl_xdk_lwb"/>

## Hierarchial Data

The dataset is hierarchical and has a parent-child relationship. Parent nodes are known as *Changesets*, Child nodes are *Change Execution Sets*. Whenever you are trying to update a parent node, the child node should also be considered. Under one parent node, there can be multiple child nodes. There are two types of child nodes:

1.  *Mandatory child node*

    For a mandatory child node, if the parent node is deslected, the child nodes are deselected by default.

2.  *Non-mandatory child node*

    For a non-mandatory child node, if the parent node is deselected, you have the control to select or deselect the child nodes. Sufficient details about what all content is going to be updated as part of this selection/deselection is shown.




<a name="loio06581f4409814723823ed4bb03218fa3__section_dnb_rfk_lwb"/>

## Error Scenario

At the time of update, if there is an error, the update fails. It is all going to be in a single transaction. Its either successfully updated or it is not updated. A red icon is visible which shows the details of the failure and reason for the failure. Accordingly, sufficient action can be taken.

