<!-- loio06581f4409814723823ed4bb03218fa3 -->

# Update Content Maintained by SAP

Incorporate new versions of standard content into your dataset.

At the time of onboarding, the latest SAP standard content is available for usage. When a new version of SAP standard content is released, you can choose to manually update to the latest version depending on your business needs if you have the required privileges.



<a name="loio06581f4409814723823ed4bb03218fa3__section_agc_rwy_ddc"/>

## New Content Updates

Check [What's New for SAP Business Technology Platform](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?Component=Integration+Assessment;Migration+Assessment&locale=en-US) to stay informed on new content releases and a description of what they include.

Once there are content updates delivered by SAP, you also get a notification directly in the tool. The notification has the *View Updates* button. Selecting the button takes you to the *Content Life Cycle* page where new content is visible for update.

> ### Note:  
> Alternatively, you can navigate to *Settings* \> *Content Life Cycle* to view the updates available.



<a name="loio06581f4409814723823ed4bb03218fa3__section_hf3_kwy_ddc"/>

## Required Privileges

The *Content Life Cycle* page is only visible to users who have the right to update the content. This privilege is granted to the following personas:

-   Enterprise Architect
-   Administrator

For more information on personas, see: [Personas for Integration Assessment](60-Security/personas-for-integration-assessment-5df5af1.md).



<a name="loio06581f4409814723823ed4bb03218fa3__section_ozm_4xy_ddc"/>

## Content Update Process

To start the process, either select the button in the notification or use the navigation *Settings* \> *Content Life Cycle*.

Every time a new version of SAP standard content is released, you can choose which data to update.

> ### Note:  
> When there's more than one version of the standard content released, you cannot directly upgrade to the latest version. You will only be able to upgrade to the next version.
> 
> > ### Example:  
> > If the current version is 1.1, update version is 1.2 and the latest version is 1.3, you can only update first to 1.2 and then to 1.3. You can't update directly to the latest version.

The possible types of updates are the following:


<table>
<tr>
<td valign="top">

New

</td>
<td valign="top">

New Content

</td>
</tr>
<tr>
<td valign="top">

Update

</td>
<td valign="top">

Update of existing content

</td>
</tr>
<tr>
<td valign="top">

Delete

</td>
<td valign="top">

Remove existing content

</td>
</tr>
</table>

Selecting a change set includes it in the update. When you don't select it, the change set is removed and potential cleanup actions are initiated.

The change sets can be either *Mandatory for Update* or *Available for Update* as described in the following table.


<table>
<tr>
<th valign="top">

Change set type

</th>
<th valign="top">

Meaning

</th>
</tr>
<tr>
<td valign="top">

Mandatory For Update

</td>
<td valign="top">

Signifies whether the change set is mandatory for the planned update.

</td>
</tr>
<tr>
<td valign="top">

Available For Update

</td>
<td valign="top">

Signifies whether the change set is available for update.

</td>
</tr>
</table>

The dataset is hierarchical and has a parent-child relationship. Whenever you're trying to update a parent node, the child node should also be considered. Under one parent node, there can be multiple child nodes. The two types of child nodes are as follows:

-   Mandatory child node

    For a mandatory child node, if the parent node is deselected, the child nodes are deselected by default.

-   Non-mandatory child node

    For a non-mandatory child node, if the parent node is deselected, you have the control to select or deselect the child nodes. Sufficient details about what all content is going to be updated as part of this selection/deselection is shown.


Select *Update* once you're done.

> ### Note:  
> If there's any error during the update, the entire content update fails. An error marker is placed at the respective position. By selecting it, error details including the reason are shown.

