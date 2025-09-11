<!-- loio99515fc73df2466b989bf285300860a4 -->

# Creating a Subscription for Application with Application Developer Role

As an application developer you can create a subscription for application, and view the existing subscription details, and its associated products, custom attributes and analytics data.



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

You are about to create an subscription for application and add products to your subscription. You can also select an existing application and view its details under the *Application Details* tab. Navigate to the *Products* tab to view the products and the rate plan associated with this application. Navigate to the *Analytics* tab to analyze application usage, performance, and error count. For more information, see [Analyze Applications](analyze-applications-deb57dd.md).



## Procedure

1.  Log on to Developer Hub.

2.  You can subscribe to a product in one of two ways:

    -   From the *Home* page, select the product you want to subscribe to, choose the *Subscribe* button at the top, then choose *Create New Subscription for Application*.
    -   Alternatively, go to *My Workspace* and choose *Create* under *Subscriptions* tab.

    The applications you created earlier, are displayed under *Applications*. For an existing subscription, you can view the total number of calls made in the current month..

3.  In the *Create Subscription for Application* dialog, enter the following *Subscription Details* and choose *Next*:

    *Title*, a *Description* \(optional\), and a *Callback URL* \(optional\) for the application.

    You can also choose the options *Create this subscription on behalf of someone else* or *I already have key and secret*.

    > ### Note:  
    > While creating the application, if you’ve selected the *Take me to this new subscription now* checkbox, you’re directly navigated to the newly created application.

4.  To add products to this application, choose *Add Products*.

5.  In the *Add Products* dialog, select the products that you want to associate with the subscription.

    > ### Note:  
    > You can select multiple products published from the same portal but you can't select products published from different portals. For example, you can select products P1 and P2 from API portal A1. But you can't choose products, P3 and P4 from API portal A2 if you've already selected P1 and P2 from A1.

6.  Choose *Create*.

    You can find the details of the application you just created under *Application*.

    > ### Note:  
    > The system generates a key automatically when the subscription is created. You should use this key value to access the API. At any point in time, you can regenerate the key using *Regenerate Key* option. When you regenerate the key, both the key and the secret key are changed. When you trigger API using the old key, then the response is negative. The old key becomes invalid on regeneration.


