<!-- loio99515fc73df2466b989bf285300860a4 -->

# Creating an Application with Application Developer Role

As an application developer you can create an application, and view the existing application details, and its associated products, custom attributes and analytics data.



<a name="loio99515fc73df2466b989bf285300860a4__prereq_rbm_rjr_v5b"/>

## Prerequisites

-   You have the *AuthGroup.API.ApplicationDeveloper* role assigned to you. For more information on roles, see [Assign User Roles in API Management](https://help.sap.com/viewer/de4066bb3f9240e3bfbcd5614e18c2f9/Cloud/en-US/911ca5a620e94ab581fa159d76b3b108.html "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.") :arrow_upper_right:.

    > ### Note:  
    > The *AuthGroup.API.ApplicationDeveloper* role must not be assigned manually to a user form the SAP BTP Cockpit. Also, this role must not be a part of any user group assignment.
    > 
    > The *AuthGroup.API.ApplicationDeveloper* role is assigned by default to a user who onboards to Developer Hub using the self-registration process or via*Add User* flow. For more information on registering in Developer Hub, see [Registering on Developer Hub](registering-on-developer-hub-c85fafe.md).
    > 
    > In the Add User flow, the Developer Hub admin adds a user who wants to be onboarded to Developer Hub. However, the user who is requesting to be onboarded must ensure that the user details provided to the admin matches the user details obtained from the response of <developer portal url\>/api/1.0/users.




## Context

You are about to create an application and add products to your application. You can also select an existing application and view its details under the *Application Details* tab. Navigate to the *Products* tab to view the products and the rate plan associated with this application. You can add custom attributes to your applications, and manage them from the *Custom Attributes* tab. For more information, see [Add Custom Attributes to an Application](add-custom-attributes-to-an-application-39c3cbd.md). Navigate to the *Analytics* tab to analyze application usage, performance, and error count. For more information, see [Analyze Applications](analyze-applications-deb57dd.md).



## Procedure

1.  Log on to Developer Hub and navigate to *My Workspace*.

    The applications you created earlier, are displayed under the *Applications* tab. For an existing application, you can view the total number of calls made in the current month on the *Applications* page.

2.  To create an application, choose *Create New Application* in the *Applications* section.

    Alternatively, you can select a product from the home page, choose the *Subscribe* button within the product and choose *Create New Application*.

3.  In the *Create an Application* dialog, enter a *Title*, a *Description* \(optional\), and a *Callback URL* \(optional\) for the application.

    You can also choose the options *Create this application on behalf of someone else* or *Already have Application Key & Secret*.

    > ### Note:  
    > While creating the application, if you’ve selected the *Take me to this new application now* checkbox, you’re directly navigated to the newly created application.

4.  To add products to this application, choose *Add Products*.

5.  In the *Add Products* dialog, select the products that you want to associate with the application.

    > ### Note:  
    > You can select multiple products published from the same portal but you can't select products published from different portals. For example, you can select products P1 and P2 from API portal A1. But you can't choose products, P3 and P4 from API portal A2 if you've already selected P1 and P2 from A1.

6.  Choose *Create*.

    You can find the details of the application you just created under the *Application Details* tab.

    > ### Note:  
    > The system generates an *Application Key* automatically when an application is created. You should use this application key value to access the API. At any point in time, you can regenerate the application key using *Regenerate Key* option. When you regenerate the key, both the application key and the secret key are changed. When you trigger API using the old key, then the response is negative. The old application key becomes invalid on regeneration.

7.  To add a custom attribute, choose *Custom Attributes* \> *Add Custom Attributes*.

8.  In the *Add Custom Attribute* dialog, enter a name and a value for your custom attribute and choose *Add*

    > ### Note:  
    > You can create a maximum of 18 custom attributes per application. You cannot modify the name of a created custom attribute. However, you can modify its value whenever required. You can delete a custom attribute if it is no longer needed.

    For more information on the usage of custom attributes in an application, see [Example: Accessing the Custom Attributes of an Application](example-accessing-the-custom-attributes-of-an-application-1cbd94c.md).


