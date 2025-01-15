<!-- loiodf4f777329c744f3a054bddc6011ab6b -->

# Creating an Application with Developer Hub Administrator Role

With the Developer Hub administrator role you can create an application on behalf of a user \(application developer\), and view the existing application details, and its associated products, custom attributes, and analytics data.



<a name="loiodf4f777329c744f3a054bddc6011ab6b__prereq_ryh_xch_w5b"/>

## Prerequisites

> ### Note:  
> The availability of this feature is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see [User Roles and Responsibilities in Developer Hub](../user-roles-and-responsibilities-in-developer-hub-54b4607.md). You can also refer to the SAP Notes [2903776](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fme.sap.com%2Fnotes%2F2903776) and [3463620](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fme.sap.com%2Fnotes%2F3463620).

You should have the *AuthGroup.API.Admin* role assigned to you. For more information on roles, see [Assign User Roles in API Management](https://help.sap.com/viewer/de4066bb3f9240e3bfbcd5614e18c2f9/Cloud/en-US/911ca5a620e94ab581fa159d76b3b108.html "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.") :arrow_upper_right:.



## Context

A Developer Hub administrator can perform the following tasks:

-   Create an application on behalf of a user \(Application Developer\) and handover the application key and secret to that user.
-   Create new applications in different landscapes\(example: production, nonproduction\) by maintaining the same application key and secret.
-   Create custom attributes at application level and regulate the API call logic.



<a name="loiodf4f777329c744f3a054bddc6011ab6b__steps_wlt_fdh_w5b"/>

## Procedure

1.  Log on to **Developer Hub** and navigate to *My Workspace*.

    If you or other application developers have created applications earlier, they’re displayed under the Applications section. For a created application, you can view the total number of calls made in the current month.

    > ### Note:  
    > For Developer Hub administrators, analytics data is unavailable for those applications that they created on behalf of other users or application developers.

2.  To create an application, choose *Create New Application* in the *Applications* section.

    Alternatively, you can select a product from the home page, choose the *Subscribe* button within the product and choose *Create New Application*.

3.  In the *Create an Application* dialog, enter a *Title*, a *Description* \(optional\), and a *Callback URL* \(optional\) for the application.

    As an administrator, you have the option to create an application on behalf of a user \(application developer\). To achieve this task, select the *Create this application on behalf of someone else* checkbox, and enter the *User ID* of the user on behalf of whom you are creating the application. If you already possess an application key and secret, then select the *Already have Application Key and Secret* checkbox and enter the *Application Key* and *Application Secret*.

    > ### Note:  
    > Application key and secret of an existing org can't be used in a new application in a new org. This implies that you'll not be able to use the same application key and secret in multiple orgs within the same data center and region.

    > ### Note:  
    > While creating the application, if you’ve selected the *Take me to this new application now* checkbox, you’re directly navigated to the newly created application.

4.  To add products to this application, choose *Add Products*.

5.  In the *Add Products* dialog, select the products that you want to associate with the application.

    > ### Note:  
    > You can select multiple products published from the same portal but you can't select products published from different portals. For example, you can select products P1 and P2 from API portal A1. But you can't choose products, P3 and P4 from API portal A2 if you've already selected P1 and P2 from A1.

6.  Choose *Create*.

    You can find the details of the application you just created under the *Application Details* tab.

7.  To add a custom attribute, choose *Custom Attributes* \> *Add Custom Attributes*.

8.  In the *Add Custom Attribute* dialog, enter a name and a value for your custom attribute and choose *Add*

    > ### Note:  
    > You can create a maximum of 18 custom attributes per application. You cannot modify the name of a created custom attribute. However, you can modify its value whenever required. You can delete a custom attribute if it is no longer needed.

    For more information on the usage of custom attributes in an application, see [Example: Accessing the Custom Attributes of an Application](example-accessing-the-custom-attributes-of-an-application-1cbd94c.md).


