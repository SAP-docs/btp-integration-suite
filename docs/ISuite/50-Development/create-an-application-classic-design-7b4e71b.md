<!-- loio7b4e71b3887f4396aa22ce3e2ed7e0c3 -->

# Create an Application \[Classic Design\]

Create an Application to consume the required APIs.

> ### Note:  
> This document describes the classic design of the API business hub enterprise. To view the documentation for the new design, see [Create an Application \[New Design\]](create-an-application-new-design-a501a6d.md).

**Prerequisites**

-   You either have the `AuthGroup.API.ApplicationDeveloper` role or `AuthGroup.API.Admin` role assigned to you. For more information on roles, see [User Roles in API Management](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/911ca5a620e94ab581fa159d76b3b108.html "Similar to other capabilities of the SAP Integration Suite, the API Management capability defines a set of technical roles that grant specific permissions to users. Users can be assigned roles through SAP BTP's role collection concept. While users have the option to create their own role collections, a set of predefined role collections is automatically created when the API Management capability is provisioned.") :arrow_upper_right:.

    > ### Note:  
    > The AuthGroup.API.ApplicationDeveloper role must not be assigned manually to a user form the SAP BTP Cockpit and this role must not be a part of any user group assignment.
    > 
    > This role is assigned by default to a user who onboards to the API business hub enterprise using the Self-registration process or via Add User flow.
    > 
    > A user must be onboarded to API business hub enterprise only via Self-registration or Add User flow. For more information on registering in API business hub enterprise, see [Register on API business hub enterprise](register-on-api-business-hub-enterprise-c85fafe.md). In the Add User flow, the API business hub enterprise admin adds a user who wants to be onboarded to API business hub enterprise. However, the user who is requesting to be onboarded must ensure that the user details provided to the admin matches the user details obtained from the response of <developer portal url\>/api/1.0/users.


An application is a discrete representation of the actual developer’s application. It provides the developer with an API key to pass-in with every request to the API.

In API Management, similar APIs are bundled together to form products, which are published in the Catalog. An application developer enters necessary details to register to the API business hub enterprise. After successful registration, the Application Developer can explore the required products and APIs to create an application. Once the application has been created successfully, the system generates an AppIication Key and Application Secret. If APIs in the application you created are protected via Verify API Key policy, then to access those APIs, you must pass the generated Application Key. Whereas, if APIs are protected via OAuth policy, then to access those APIs, you must pass an OAuth token that can be obtained by using the combination of generated Application Key and Application Secret.



## Creating an Application with Application Developer Role

1.  Log on to the API business hub enterprise.
2.  Navigate to the *My Workspace* page.

    If you have created applications earlier, they’re displayed under the *Applications* section. For a created application, you can view the total number of calls made in the current month.

    > ### Note:  
    > By default, the *Cost* section displays the cost incurred in the last 6 months and the cost incurred in the current month. However, you can choose a month to view the cost incurred for that month.

    You can choose ![](images/Refresh_icon_ba1b5ab.png) to obtain the latest metering data.

    > ### Note:  
    > You might experience some delay before you see the latest metering data.

    Notation used to display the data is as per metric specifications, for example:

    -   999 shows as 999 and 1000 shows as 1k
    -   999000 shows as 999K and 1000000 shows as 1M
    -   1500000 shows as 1.5M and 1000000000 shows as 1G

3.  To create an application, choose ![](images/Add_icon_587bccc.png) in the *Applications* section.
4.  In the *Create an Application* dialog, enter a `Title`, a `Description` \(optional\), and a `Callback URL` \(optional\) for the application.
5.  Choose ![](images/Add_icon_587bccc.png) to add products to this application.
6.  In the *Add Products* dialog, select the products that you want to associate with the application.

    > ### Note:  
    > You can select multiple products published from the same portal but you can't select products published from different portals. For example, you can select products P1 and P2 from API portal A1. But you can't choose products, P3 and P4 from API portal A2 if you've already selected P1 and P2 from A1.

7.  Choose *OK*.
8.  Choose *Save*.

    > ### Note:  
    > While creating an application, if you’ve selected the *Take me to this new application now* checkbox, you’re directly navigated to the newly created application.

    The application you have created appears under the *Applications* section, and also under the *Applications* tab in API portal.

    > ### Note:  
    > If you open any created application, you notice that the system has generated an *API Key* automatically. Use this value to access the API. At any point in time, you can regenerate the API Key using *Regenerate Key* option. When you regenerate the key, both Application key and Secret key are changed. When you trigger API using the old key, then the response is negative. The old API key becomes invalid on regeneration.




<a name="loio7b4e71b3887f4396aa22ce3e2ed7e0c3__section_dbw_v5c_rmb"/>

## Creating an Application with API business hub enterprise Administrator Role

A API business hub enterprise administrator can perform the following tasks:

-   Create an application on behalf of a user \(Application Developer\) and handover the application key and secret to that user.
-   Create new applications in different landscapes\(example: production, nonproduction\) by maintaining the same application key and secret.
-   Create custom attributes at application level and regulate the API call logic

1.  Log on to the API business hub enterprise.
2.  Navigate to the *My Workspace* page.

    ![](images/My_Workspace_315b2dc.png) If you or other application developers have created applications earlier, they’re displayed under the *Applications* section. For a created application, you can view the total number of calls made in the current month.

    > ### Note:  
    > By default, the *Cost* section displays the cost incurred in the last 6 months and the cost incurred in the current month. However, you can choose a month to view the cost incurred for that month.

    > ### Note:  
    > For API business hub enterprise administrators, analytics data is unavailable for those applications that they created on behalf of other users or application developers.

    You can choose ![](images/Refresh_icon_ba1b5ab.png) to obtain the latest metering data.

    > ### Note:  
    > You might experience some delay before you see the latest metering data.

    Notion used to display the data is as per metric specifications, for example:

    -   999 shows as 999 and 1000 shows as 1k
    -   999000 shows as 999K and 1000000 shows as 1M
    -   1500000 shows as 1.5M and 1000000000 shows as 1G

3.  To create an application, under *Applications* section, choose ![](images/Add_icon_587bccc.png).
4.  In the *Create an Application* dialog, enter a `Title`, a `Description` \(optional\), and a `Callback URL` \(optional\) for the application.
5.  As an administrator, you have the option to create an application on behalf of a user \(Application Developer\). To achieve this task, select the *Create this application on behalf of someone else* checkbox and enter the `User ID` of the user on behalf of whom you are creating the application. If you already possess an application key and secret, then select the *Already have Application Key and Secret* checkbox and enter the `Application Key` and `Application Secret` .

    > ### Note:  
    > Application key and secret of an existing org can't be used in a new application in a new org. This implies that you'll not be able to use the same application key and secret in multiple orgs within the same data center and region.

6.  Choose ![](images/Add_icon_587bccc.png) to add products to this application.
7.  In the *Add Products* dialog, select the products that you want to associate with the application.

    > ### Note:  
    > You can select multiple products.

8.  Choose *OK*.
9.  Choose *Save*.

    > ### Note:  
    > While creating an application, if you’ve selected the *Take me to this new application now* checkbox, you’re directly navigated to the newly created application.

    The application you created appears under the *Applications* section, and also under the *Applications* tab in API portal.

    > ### Note:  
    > If you open any created application, you notice that the system has generated an *API Key* automatically. Use this value to access the API. At any point in time, you can regenerate the API Key using *Regenerate Key* option. When you regenerate the key, both Application key and Secret key are changed. When you trigger API using the old key, then the response is negative. The old API key becomes invalid on regeneration.

10. Specify custom attributes.
    1.  Under *My Workspace*, choose an application for which you want to add custom attributes.
    2.  In the *Application Info* screen, under *Custom Attributes* section, choose ![](images/Add_icon_587bccc.png) to add a custom attribute.
    3.  In the *Add Custom Attribute* dialog, enter a name and a value for your custom attribute and choose *Add*.

        > ### Note:  
        > You can create a maximum of 18 custom attributes per application. You cannot modify the name of a created custom attribute. However, you can modify its value whenever required. You can delete a custom attribute if it is no longer needed.

        For more information on the usage of custom attributes in an application, see [Example: Accessing the Custom Attributes of an Application](example-accessing-the-custom-attributes-of-an-application-1cbd94c.md).



