<!-- loiof6eb4332cd5144ef91f4a84cc614ba1c -->

# Setting Up API Management Capability from Integration Suite

You can provision the API Management capability from the **Integration Suite** launchpad.



<a name="loiof6eb4332cd5144ef91f4a84cc614ba1c__prereq_hgt_tfb_stb"/>

## Prerequisites

-   You already have a subaccount and have enable the Cloud Foundry environment in this subaccount. For more information, see [Create a Subaccount](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/05280a123d3044ae97457a25b3013918.html?q=entitlements).

-   An *Integration Suite* entitlement has been created for your subaccount. For more information, see [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/5ba357b4fa1e4de4b9fcc4ae771609da.html?q=entitlements).




<a name="loiof6eb4332cd5144ef91f4a84cc614ba1c__context_kqs_twb_stb"/>

## Context

To set up the API Management capability from Integration Suite, you should first have an Integration Suite subscription.

> ### Note:  
> Ensure that you don’t have an instance of a starter plan created in the same subaccount where you plan to create an Integration Suite subscription. Also, note that API Management capabilities from Integration Suite and API Management subscriptions using the stand-alone tile can’t coexist in the same subaccount.

> ### Note:  
> For visual intructions on how to set up and configure API Management capability from Integration Suite, refer the tutorial [Set Up API Management from Integration Suite | Tutorials for SAP Developers](https://developers.sap.com/tutorials/api-mgmt-isuite-initial-setup.html).



<a name="loiof6eb4332cd5144ef91f4a84cc614ba1c__steps_bnm_ft1_stb"/>

## Procedure

1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

2.  In the navigation area of the subaccount, choose *Services* \> *Service Marketplace* and search for *Integration Suite* and choose *Create*.

3.  On the *New Instances and Subscriptions* dialog, choose Integration Suite as the *Service*, select the *Plan*, and choose *Create*.

    Wait for the subscription to complete successfully.

4.  Choose *View Subscription* on the *Creation in Progress* dialog.

    Check the status of the submission in the *Subscriptions* section on the *Instances and Subscriptions* page. If the subscription is successful, you’ll notice the status of the *Integration Suite* is shown as *Subscribed*.

5.  To access the Integration Suite, assign the *Integration\_Provisioner* role to yourself.

    > ### Note:  
    > If you choose *Go to Application* without assigning the *Integration\_Provisioner* role, an application authentication error appears. If the error persists after assigning the role, clear your web browser cache, and log out of the application and log on again.

    To assign the role:

    1.  On the navigation pane, under *Security*, choose *Users*.

    2.  Select your Username and under *Role Collections* section, choose *Assign Role Collection*.

    3.  In the resulting dialog box, select the *Integration\_Provisioner* role and choose *Assign Role Collection*.


    For detailed instructions, see [Working with Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/393ea0b222754311884123ce564779bd.html?q=SAP%20ID%20Service).

6.  Once the role is assigned, choose *Instances and Subscriptions* on the left navigation pane and under *Subscriptions* look for ***Integration Suite***, and choose **Go To Application**.

    You’re navigated to the *Integration Suite* home page.

7.  On the Integration Suite home page, under *Capabilities*, choose *Add Capabilities*.

8.  On the *Activate Capabilities* dialog, under *Select Capabilities*, select the *Design, Develop and Manage APIs* and choose *Next*.

9.  If you want to activate API business hub enterprise, select the checkbox *Enable API Business Hub Enterprise* and choose **Next**.

10. Choose *Activate* on the *Activate Capabilities* dialog.

    > ### Note:  
    > If you face any issues during activation or the activation fails, then refer SAP Note [2904202](https://launchpad.support.sap.com/#/notes/2904202) and proceed accordingly.

11. On the resulting screen, choose *OK* once the status changes from *In Progress* to *Active*.

12. Log out of *Integration Suite*.

13. At this point, navigate back to the SAP BTP Cockpit and assign the following roles:

    -   *APIManagement.Selfservice.Administrator*: This role is required for the onboarding of API Portal and to get access to its Settings page.

    -   *AuthGroup.SelfService.Admin*: You'll need this role during the onboarding of API business hub enterprise and to get access to it.


    To assign these roles:

    1.  Choose *Security* \> *Users* from the left navigation pane.

    2.  Select your username and under *Role Collections* section, choose *Assign Role Collection*.

    3.  In the resulting dialog box, select the *APIManagement.Selfservice.Administrator* and *AuthGroup.SelfService.Admin* roles and choose *Assign Role Collection*.


14. Once the roles are assigned, log on to the *Integration Suite*.

15. On the *Integration Suite* home page, choose *Settings* \> *APIs* from the left navigation pane.

16. On the *Configure the API Management Service* screen, configure the following and choose *Set Up*:

    -   Select the *Account type*:

        -   Select the *Non Production* account type for non-business critical activities, such as integrating test systems, testing new scenarios, performance testing, and sandbox activities.
        -   Select the *Production* account type for business critical usages, such as integrating production systems, and productive APIs.

    -   In the *Virtual Host* section, enter the *Host Alias*.

    -   Provide an email ID in the *Notification Contact* field to receive updates.


    In the *Set-up Confirmation* window, review the provided details and choose *Confirm* to start the onboarding process.

    You’re redirected to a progress window, which states *API Management Service Setup In Progress*.

    The *Configuration* process is triggered, where the necessary resources are provisioned for you. It’s followed by *Testing the Setup* process, where a simple API Proxy is deployed and invoked to check that everything is set up properly.

    When the processes complete, the indicators turn green to indicate that the processes are successful. A *Release Notification* mail is sent out to the email IDs provided in the *Configure the API Management Service* screen. This email contains details of the newly set up API Management service on your account.

    The API Management capability is now configured.

17. You must log out of *Integration Suite* and log in again.

    You can now create APIs, build API proxies as a service provider, or use APIs and other convenient services.


**Related Information**  


[Setting Up API Portal Application Using API Management Standalone Tile](setting-up-api-portal-application-using-api-management-standalone-tile-9d8c7ae.md "You can provision the API portal using the API Management, API Portal standalone tile from the SAP BTP cockpit.")

[Assign User Roles](assign-user-roles-911ca5a.md "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "Cancel your API portal and API business hub enterprise application subscriptions to disable your account from the API Management service.")

[Build APIs](../APIM-Development/build-apis-74c042b.md "API portal provides a common platform for API designers to define and publish APIs. Every API Management customer is provided with their own API portal application on cloud. The API portal offers capabilities to configure systems, build and publish APIs, analyze and test APIs.")

[Create an API Provider](../APIM-Development/create-an-api-provider-6b263e2.md "Create an API provider to connect to an API provider and browse for APIs.")

[Create an API Proxy](../APIM-Development/create-an-api-proxy-4ac0431.md "Create API proxies.")

[Requesting for Custom Domain for a Virtual Host](requesting-for-custom-domain-for-a-virtual-host-6b9e5a3.md "When you subscribe to API Management service, and are creating API proxies, they get created with the default virtual host, and the default domain. To suit your requirements, you can request for a custom domain.")

[Request for Two-Way SSL Certificate](request-for-two-way-ssl-certificate-9faf7ce.md "Request a two-way SSL certificate for the default domain of the virtual host of your API Management service.")

