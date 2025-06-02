<!-- loio4909d3fd2dd94227bdd6d6b515fd60da -->

# Configuring Connector Setup Using the UI \(Recommended Approach\)

Onboard with Catena-X and get started in Data Space Integration by entering your data space identifiers and Cloud Integration parameters. This setup method uses the user interface of Data Space Integration.



<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__prereq_ic1_kkd_l1c"/>

## Prerequisites

-   You've completed the steps described in [Preparatory Steps](preparatory-steps-95366b2.md) where you activate SAP Integration Suite and the Cloud Integration capability.

-   You've completed the steps described in [Activating the Capability](activating-the-capability-b49ad35.md) where you add Data Space Integration to your list of active capabilities of SAP Integration Suite.

-   You've completed the steps described in [Configuring User Access](configuring-user-access-6ae0ff7.md) where you define user roles for Data Space Integration.

-   You've completed the steps described in [Preparing Cloud Integration](preparing-cloud-integration-07f81f2.md) where you create Cloud Integration service keys.

-   You've completed the steps described in [Creating Technical Users in Landscape Portal](creating-technical-users-in-landscape-portal-b95f0ef.md) where you create two technical users in the landscape portal of your chosen data space.


> ### Note:  
> The steps here describe the process for configuring the connector setup using the user interface of Data Space Integration.
> 
> If you want to do the configuration using the API, see [Configuring Connector Setup Using the API \(Alternative Approach\)](configuring-connector-setup-using-the-api-alternative-approach-bfa408c.md).



<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__steps_yct_rkd_l1c"/>

## Procedure

1.  First, register the connector in Data Space Integration.

    1.  Open SAP Integration Suite and navigate to *Settings* \> *Data Spaces*. Choose *Onboard*.

        > ### Note:  
        > If *Settings* \> *Data Spaces* isn't visible to you, you might not have the correct role assigned to your user. Only users with the role `DataspaceTechnicalAdmin` can perform the onboarding.

    2.  In the first tab *Connect to a Data Space*, select the *Landscape* you want to onboard to. It must be the same landscape in which you've created the *Identity Wallet Management* and *Offer Management* role in [Creating Technical Users in Landscape Portal](creating-technical-users-in-landscape-portal-b95f0ef.md).

    3.  Enter the *Business Partner Number* of the company account.

    4.  Choose a *Connector Name* under which you want the connector to be registered in the portal. The *Default Connector URL* is prefilled automatically. You can still edit it in case you want to use a custom domain or protect it using API management.

        If you want to overwrite the *Default Connector URL*, you can enter a *Custom Connector URL*. This URL then replaces the default connector externally. If you don't require a custom connector URL, leave this field empty.

    5.  Fill in the *Offer Management User* information. You can retrieve these details from the *Offer Management* user that you created in the landscape portal.

    6.  Fill in the *Decentral Identity Verification* information with your *IATP STS OAuth Token URL* and the corresponding *Client ID* and *Client Secret*. you can retrieve the client details from the *Identity Wallet Management* user you created in the landscape portal.

        You can find the *IATP STS OAuth Token URL* in the landscape portal:

        1.  For Catena-X, go to *Your Profile* \> ** \> *Connector Management*and choose your connector configuration details to view a dialog with all your details. Copy the *iatp.sts.oauth.token\_url*.

        2.  For Cofinity-X, go to *Technical Setup* \> *Connector Registration* and choose your connector configuration details to view a dialog with all your details. Copy the *iatp.sts.oauth.token\_url*.




        The other information in this section is filled in automatically. If you're using a custom landscape, you must enter these details manually as well.

    7.  Choose *Save*.

        You can now move on to the next tab, *Prepare Connection to Cloud Integration*.


2.  In the *Prepare Connection to Cloud Integration* tab, you're preparing the connection to Cloud Integration, for which you need to enter two service keys.

    1.  Enter the required *API Parameters* from the Cloud Integration service key *Process Integration Runtime*, plan `api`. You can enter the parameters manually or choose *Paste Service Key* to paste the data.

        To get these parameters, access the SAP BTP cockpit, go to *Instances and Subscriptions*, and select the relevant service key. In the expanding details view, choose *key* and then *Copy JSON*. See also [Preparing Cloud Integration](preparing-cloud-integration-07f81f2.md).

    2.  Repeat the previous step for the *Runtime Parameters*, with service key *Process Integration Runtime*, plan `integration-flow`.
    3.  Choose *Save*.


3.  Finally, continue to the tab *Onboard the Data Plane*.

    Simply choose *Onboard*. Data Space Integration then starts deploying the integration package in Cloud Integration using the parameters that you provided in the previous steps.

    The onboarding of Data Space Integration can take up to 20 minutes.




<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__result_zqw_syd_l1c"/>

## Results

You can now use Data Space Integration.



<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__postreq_a2b_xlc_kcc"/>

## Next Steps

Depending on your role, you can now get started with one of the following tasks:

-   Learn how to work with assets, policies, and contract definitions as a provider. See [Data Spaces - Providing Assets, Policies, and Contract Definitions](50-Development/data-spaces-providing-assets-policies-and-contract-definitions-079b342.md).

-   Learn how to discover offers and consume assets provided by other participants of a data space. See [Consuming Data Space Assets](consuming-data-space-assets-5c0cdb8.md).

-   Monitor your active contract agreements. See [Monitoring Agreements](50-Development/monitoring-agreements-a247cc4.md).

-   Discover the APIs Data Space Integration provides on the SAP Business Accelerator Hub and how to work with them. See [Using APIs to Work With Data Space Integration](using-apis-to-work-with-data-space-integration-411fd1e.md).


