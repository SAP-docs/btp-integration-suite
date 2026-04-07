<!-- loiof74f47d2b2944f9dbc645bc179e2d4e1 -->

# Subscribe to Consume APIs from an Application

As an application developer, you need to subscribe to a product to consume the APIs within it. As part of the subscription process, you can either create a new application and add the product to it, or add the product to an existing application.



<a name="loiof74f47d2b2944f9dbc645bc179e2d4e1__prereq_nls_54p_42c"/>

## Prerequisites

The *AuthGroup.API.ApplicationDeveloper* role collection must be assigned to you.



## Procedure

1.  Log on to Developer Hub.

2.  Select the SAP Integration Suite product that you want to subscribe to.

    The product opens, allowing you to view the product details, including APIs and associated applications.

3.  Choose *Subscribe*.

    You can either choose*Create New Subscription for Application* or *Add to ExistingSubscription for Application*.

    -   Create a new subscription for application from the Developer Hub catalog:

        1.  In the *Create New Subscription for Application* dialog box, enter a *Title*, *Short Text*, a *Description* \(optional\), and a *Callback URL* \(optional\) for the application.

        2.  Select the option *Create this application on behalf of someone else* if applicable, and enter the developer’s *User ID*.

            **Only API administrators can create applications on behalf of others. Developers must create their own applications directly. When creating on behalf, the administrator should enter the developer's U**ser ID.

        3.  If you select the *Take me to this new application now* checkbox, you are directly taken to the newly created application.

            You can find the details of the application you just created under the*Application Details* tab. On the *Products* tab, you can find the product you were trying to subscribe to.

        4.  To add additional products, choose *Add Products*.

        5.  In the *Add Products* dialog box, select the products that you want to associate with the application and choose *Add*.


    -   Add to ExistingSubscription for Application **From the Developer Hub Catalog**

        In the *Add to ExistingSubscription for Application* dialog box, select the application and choose *Add*.

        The product gets added to the application you selected.


    Alternatively, you can subscribe to a product from *My Workspace*:

    1.  Navigate to *My Workspace*. The *Applications* tab is selected by default. Choose *Create* and select *Subscription for an Application*.

        The *Create Subscription for Application* wizard opens.

    2.  In *Products*, find and select the product you want to subscribe to, then choose *Next*.

        > ### Note:  
        > If you select a product that includes APIs with an authentication provider of type *External OAuth*, the *Client ID* field appears. You must provide the Client ID details in this field.

    3.  In *Subscription Details*, enter the following and choose *Next*:

        *Title*, a *Description* \(optional\), and a *Callback URL* \(optional\) for the application.

        You can also choose the options *Create this subscription on behalf of someone else* and select the user on whose behalf you are creating this subscriptio. If you already have a custom key and secret, then choose *I already have the key and secret*.

        > ### Note:  
        > While creating the application, if you’ve selected the *Take me to this new subscription now* checkbox, you will be directly navigated to the newly created application.

    4.  *Review* the changes on the next screen and choose *Save*.

        > ### Note:  
        > If governance is set to *Manage Approval Outside Developer Hub* for a subscription, the subscription request must be approved by an external administrator before any actions can be performed on it. Once approved, an email notification with a link to the approved subscription will be sent. Only then you can consume the APIs in the subscription.





<a name="loiof74f47d2b2944f9dbc645bc179e2d4e1__result_z5f_24p_hgc"/>

## Results

You have created the product subscription for application successfully.

