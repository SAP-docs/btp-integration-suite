<!-- loio71c04480f612458b90d9bbc7da6ccb63 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Creating Custom Tags

You can maintain custom attributes in your editable integration packages.

You can tag your integration package using custom attributes that can be created under the *Settings* tab. The tags can help you identify and track your packages based on attributes, for example, such as Author, Line of Business etc.

> ### Remember:  
> You must have the tenant administrator role assigned to access the *Custom Tags* settings. See [Tasks and Permissions for Cloud Integration](../../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

1.  Navigate to the *Settings* \(:gear:\) in the web UI and choose *Custom Tags*.

2.  Choose *Edit* and select *Add* to add custom attributes.

3.  Enter a name for the tag under *Tag Name*.

4.  By default, the *Mandatory* check box is enabled. Uncheck the check box if you don’t want to set your tag mandatory.

5.  In the *Permitted Values* field, type in the possible custom values from which you want the integration developers to choose. For example, with a custom tag name `Department`, you can provide permitted values like `HR`, `Finance`, `Sales`, and `Marketing`. Leave the field blank, if you want the integration developers to type their own values.

6.  Choose *Save*. You can’t rename the tags after saving them. The tags become read-only.

    > ### Note:  
    > -   After adding the necessary custom tags, you can inform the integration developers to maintain the custom tags in the existing packages.
    > 
    > -   For transport scenarios, the custom tags can be exported from source tenants and imported into the target tenant before the package transport, to reflect the custom tag values maintained at source.


The integration developers can now start maintaining the attribute values under the *Tags* tab in the newly created packages. For existing packages without the attributes, the values can be added by editing the package or using OData API.

To know how to work with custom tags using OData API, see [Working with Custom Tags](../get-custom-tags-defined-on-the-tenant-a947374.md) and [Create New Custom Tags Configuration](../create-new-custom-tags-configuration-31e8308.md).

Saving of an edited package or a newly created package fails if the mandatory attributes aren’t maintained.

> ### Note:  
> Deleting a custom tag in the *Settings* that is already maintained in a package only hides the tag from the *Tags* section of the package. But the value of the tag along with the tag name is persisted in the package for easy retrieval. Read this [blog](https://blogs.sap.com/2020/05/11/sap-cloud-integration-custom-tags/) to know more about custom tags and their behaviours.

