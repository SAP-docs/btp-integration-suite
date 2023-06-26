<!-- loiodf6df2b90c354ca7b83c4e7045b2279c -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Cancel API Management Service Subscription

Cancel your API portal and API business hub enterprise application subscriptions to disable your account from the API Management service.

> ### Remember:  
> If you’re using the stand-alone service for API Management, ensure that you first cancel the subscription for the API business hub enterprise application, followed by the API portal application.
> 
> If you’re using API Management via the Integration Suite, you can unsubscribe from the applications in any order of your preference.
> 
> Unsubscribing deletes the data stored in the respective applications.

-   **Cancel the API Management Subscription for Standalone API Management Service**

    Perform the following steps to cancel the subscriptions for API portal and the API business hub enterprise for the stand-alone API Management service:

    1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

    2.  From the left pane, choose *Services* \> *Instances and Subscriptions*.

    3.  Select *API Management, API Business Hub Enterprise* under *Subscriptions* section, choose <span class="SAP-icons"></span> Actions , and choose *Delete*. In the *Delete Subscription* confirmation dialog, choose *Delete Subscription*.

    4.  Select *API Management, API portal* under *Subscriptions* section, choose <span class="SAP-icons"></span> Actions, and choose *Delete*. In the *Delete Subscription* confirmation dialog, choose *Delete Subscription*.


-   **Cancel the API Management Subscription from Integration Suite**

    If you've enabled the API Management capability via Integration Suite, perform the following steps to cancel the API portal and the API business hub enterprise subscriptions:

    1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

    2.  Navigate to *Services* \> *Instances and Subscriptions*.

    3.  Select *Integration Suite* under *Subscriptions*, choose <span class="SAP-icons"></span> Actions, and choose *Go To Application*.

        You’re navigated to the *Integration Suite* home page where the *Design, Develop, and Manage APIs* tile is displayed.

    4.  On the *Design, Develop, and Manage APIs* tile, choose <span class="SAP-icons"></span> Actions , and choose *Manage Capability*.

        You’re navigated to the *Integration Suite* *Provisioning* page.

    5.  To cancel the API Management subscription, choose *Deactivate*.

        The *Deactivate API Management* confirmation dialog appears.

    6.  Once you choose *Deactivate*, the *API Management, API Portal* and *API Management, API Business Hub Enterprise* applications are deactivated.



