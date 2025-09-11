<!-- loio1b1854457c4e4a629cac0b6713a8608b -->

# Add Product Subscription to an Existing Subscription

When consuming APIs, you can add a product subscription to an existing subscription for application rather than creating a new one. This approach allows you to reuse the subscription credentials and maintain consistency in API access, management, and security policies.



<a name="loio1b1854457c4e4a629cac0b6713a8608b__prereq_zvd_yxk_ffc"/>

## Prerequisites

-   The AuthGroup.API.ApplicationDeveloper role must not be assigned manually to a user form the SAP BTP Cockpit. Also, this role must not be a part of any user group assignment.

    > ### Note:  
    > The AuthGroup.API.ApplicationDeveloper role is assigned by default to a user who onboards to Developer Hub using the self-registration process or via *Add User* flow. For more information on registering in Developer Hub, see [Registering on Developer Hub](registering-on-developer-hub-c85fafe.md).

    In the *Add User* flow, the Developer Hub admin adds a user who wants to be onboarded to Developer Hub. However, the user who is requesting to be onboarded must ensure that the user details provided to the admin matches the user details obtained from the response of <developer portal url\>/api/1.0/users.




## Context

To add a product subscription to an existing subscription for application, execute the following steps:



## Procedure

1.  Log on to Developer Hub.

2.  You can subscribe to a product in one of two ways:

    -   From the *Home* page, select the product you want to subscribe to, choose the *Subscribe* button at the top, then choose *Add to Existing Subscription for Application*.

        On the *Add to an Existing Subscription for an Application* dialog, select the desired application from the list of available applications, then choose *Add* to complete the subscription.

    -   Alternatively, go to *My Workspace* and open the *Subscriptions* tab. Select an existing subscription for applications, then navigate to the *Products* tab and choose *Add*. Choose the product you want to add to the selected subscription.


