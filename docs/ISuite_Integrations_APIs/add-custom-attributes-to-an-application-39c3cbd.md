<!-- loio39c3cbdd38f54431b95cb4f3ccdbde5c -->

# Add Custom Attributes to an Application

You can create applications on behalf of other application developers, add custom attributes to your applications, and manage them.

The custom attributes at application level have values assigned to them. These values help in configuring and accessing them on runtime easily. Here, when admin creates an application on behalf of developer at application level, custom attributes can be assigned by the admin. Therefore, this helps you in enhancing the functionality and performing attribute specific runtime enforcements for your API.

**Role of a Developer Hub Administrator**:

-   Create an application on behalf of a user and handover the application key and secret to that user.
-   Create new applications in different landscapes\(example: production, non-production\) by maintaining the same application key and secret.
-   Define custom attributes at application level and regulate the API call logic.

**Visibility of List of Applications**

When a user has permission, "ManageAllAPISubscriptions" or is a Developer Hub admin, they can view *My Workspace* tab on the home page of the Developer Hub. After choosing *My Workspace* tab, they can view the following changes:

-   A list of all the applications created for the tenant by all the developers.
-   Navigate to the application details screen by selecting one of the applications. Hence, *My Workspace* tab also helps in managing all the applications.

    > ### Note:  
    > You can delete the application that is no longer needed or not in use.


**Creation of Application on Behalf of a User \(Application developer\)**

Creation of application on behalf of a user is only possible if you have the permission "ManageAllAPISubscriptions". Follow the steps mentioned below:

1.  Choose *My Workspace*.
2.  In order to create an application, choose the *\+* button next to the *Search* field.
3.  On the *Create an Application* screen, enter the following:
    -   *Application Title*

    -   *Description\(optional\)*

    -   *Call Back URL*


4.  Select the checkbox *Create this application on behalf of someone else*.
5.  Mention the *User ID* of the user or select it from the filtered drop down list. The drop down list will contain \(First\_name, Last\_name and User ID\) of the user.
6.  If you already have an application key and secret, the checkbox, *Already have Application Key and Secret*can be selected. Then the two input boxes with application key and secret appears. Enter the same in the given field.

    > ### Note:  
    > You can reuse the same application key and secret if you have created an application in a different landscape \(example: production, non-production\).

7.  You shall be able to add more products, associated with this application by choosing the *\+* button at the bottom.
8.  The checkbox *Take me to this application now* is already selected. It can be unchecked, if not necessary.
9.  Choose *Save* option.

You shall be navigated to your created application, if step 8 is followed. Otherwise an application of your choice can be selected from *My Workspace* screen. Therefore:

-   In the section *Application Info*, you can edit name, decription and call back URL.
-   Add/Remove products in *Products* section.
-   Add/Delete/Modify in *Custom Attribute* section. You can only modify the value of a custom attribute and not the attribute name.

**Reading Custom Attributes on Behalf of the user**

As a user having permission “ReadAllCustomAttributes”, you can now see a tab/section where All Custom Attributes for an application will be visible.

**Constraints**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Custom attribute name size for Application

</td>
<td valign="top">

235 characters

</td>
</tr>
<tr>
<td valign="top">

Custom attribute value size for Application

</td>
<td valign="top">

1024 characters

</td>
</tr>
<tr>
<td valign="top">

Number of custom attributes permitted for Application

</td>
<td valign="top">

18

</td>
</tr>
</table>

**Updating Custom Attributes on behalf of the user**

As a user having permission "ManageAllCustomAttributes", you can update the custom attributes for an application and also delete custom attributes .

