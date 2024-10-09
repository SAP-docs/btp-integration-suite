<!-- loio4909d3fd2dd94227bdd6d6b515fd60da -->

# Configuring Connector Setup Using the UI \(Recommended Approach\)

Onboard with Catena-X and get started in Data Space Integration by entering your data space identifiers and Cloud Integration parameters. This setup method uses the user interface of Data Space Integration.



<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__prereq_ic1_kkd_l1c"/>

## Prerequisites

> ### Note:  
> We want your feedback! Let us know what you think about this documentation by completing this two-minute survey: [SAP Documentation User Experience Survey](https://sapinsights.eu.qualtrics.com/jfe/form/SV_bJ9iYJuEJNrZNUq).

-   You've completed the steps described in [Preparatory Steps](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/247522607cdc4dbebe6dbf09068aaa7e.html "Before you can perform the onboarding steps that are specific to Data Space Integration, you must be onboarded to SAP Integration Suite and have enabled Cloud Integration.") :arrow_upper_right: where you activate SAP Integration Suite and the Cloud Integration capability.

-   You've completed the steps described in [Activating the Capability](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/be375cb46b4a4fada37e62b90efcf0d8.html "Learn how to activate the Data Space Integration capability within SAP Integration Suite.") :arrow_upper_right: where you add Data Space Integration to your list of active capabilities of SAP Integration Suite.

-   You've completed the steps described in [Configuring User Access](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/cc811d8612d64ede9ccf7edcb390ecc2.html "Before users can access the application, you need to assign the relevant role collections to them.") :arrow_upper_right: where you define user roles for Data Space Integration.

-   You've completed the steps described in [Preparing Cloud Integration](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/7014b7d65f2d479d9328d302e5ec0499.html "Data Space Integration interacts with Cloud Integration, so you must perform a few preparatory steps before you can get started with Data Space Integration.") :arrow_upper_right: where you create Cloud Integration service keys.

-   You've completed the steps described in [Create Technical Users in Landscape Portal](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/fb8d9abc5a35406c8565701ddcc7d217.html "Prepare your technical users in the landscape portal of your chosen data space.") :arrow_upper_right: where you create two technical users in the landscape portal of your chosen data space.


> ### Note:  
> The steps here describe the process for configuring the connector setup using the user interface of Data Space Integration.
> 
> If you want to do the configuration using the API, see [Configuring Connector Setup Using the API (Alternative Approach)](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/8ba870459c8a4804874db89542fbab5d.html "Onboard with Catena-X and get started in Data Space Integration by entering your data space identifiers and Cloud Integration parameters. This setup method uses an API.") :arrow_upper_right:.



<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__steps_yct_rkd_l1c"/>

## Procedure

1.  First, register the connector in Data Space Integration.

    1.  Open SAP Integration Suite and navigate to *Settings* \> *Data Spaces*. Choose *Onboard*.

        > ### Note:  
        > If *Settings* \> *Data Spaces* isn't visible to you, you might not have the correct role assigned to your user. Only users with the role `DataspaceTechnicalAdmin` can perform the onboarding.

    2.  In the first tab *Connect to a Data Space*, select the *Landscape* you want to onboard to. It must be the same landscape in which you've created the *Identity Wallet Management* and *Offer Management* role in [Create Technical Users in Landscape Portal](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/fb8d9abc5a35406c8565701ddcc7d217.html "Prepare your technical users in the landscape portal of your chosen data space.") :arrow_upper_right:.

    3.  Enter the *Business Partner Number* of the company account.

    4.  Choose a *Connector Name* under which you want the connector to be registered in the portal. The *Connector URL* is prefilled automatically. You can still edit it in case you want to use a custom domain or protect it using API management.

    5.  Fill in the *Offer Management User* information. You can retrieve these details from the *Offer Management* user that you created in the landscape portal.

    6.  Fill in the *Decentral Identity Verification* information. Enter the *IATP STS OAuth Token URL* and the corresponding *Client ID* and *Client Secret*. You can retrieve the client details from the *Identity Wallet Management* user you created in the landscape portal. The other information in this section is filled in automatically.

    7.  Choose *Save*.

    8.  Wait for about 5 minutes to let the registration finish, even after the section reached the status *Successful*. Otherwise, you can get an error.


2.  After waiting for 5 minutes for the registration of the data space to finish, refresh the page, and move on to the next tab, *Prepare Connection to Cloud Integration*.

3.  In the *Prepare Connection to Cloud Integration* tab, you're preparing the connection to Cloud Integration, for which you need to enter two service keys.

    1.  Enter the required *API Parameters* from the Cloud Integration service key *Process Integration Runtime*, plan `api`. You can enter the parameters manually or choose *Paste Service Key* to paste the data.

        To get these parameters, access the SAP BTP cockpit, go to *Instances and Subscriptions*, and select the relevant service key. In the expanding details view, choose *key* and then *Copy JSON*. See also [Preparing Cloud Integration](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/7014b7d65f2d479d9328d302e5ec0499.html "Data Space Integration interacts with Cloud Integration, so you must perform a few preparatory steps before you can get started with Data Space Integration.") :arrow_upper_right:.

    2.  Repeat the previous step for the *Runtime Parameters*, with service key *Process Integration Runtime*, plan `integration-flow`.
    3.  Choose *Save*.


4.  Finally, continue to the tab *Onboard the Data Plane*.

    Simply choose *Onboard*. Data Space Integration then starts deploying the integration package in Cloud Integration using the parameters that you provided in the previous steps.

    The onboarding of Data Space Integration can take up to 20 minutes.




<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__result_zqw_syd_l1c"/>

## Results

You can now use Data Space Integration.



<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__postreq_a2b_xlc_kcc"/>

## Next Steps

Depending on your role, you can now get started with one of the following tasks:

-   Learn how to work with assets, policies, and contract definitions as a provider. See [Data Spaces - Providing Assets in a Data Space](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/e438274e254449429a1d9752b24a3c78.html "In Data Space Integration, as a provider, you want to create assets and policies, and bundle them into contract definitions to facilitate data exchange between different members of your network.") :arrow_upper_right:.

-   Learn how to discover offers and consume assets provided by other participants of a data space. See [Data Spaces - Consuming Data Space Assets](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/32a37405e68246669bb3b4c1a8995e7c.html "In Data Space Integration, as a consumer, you want to consume data assets provided by other members of the data space.") :arrow_upper_right:.

-   Monitor your active contract agreements. See [Monitoring Agreements](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/b0169176b43b4e02a03b3b24c5adf8b6.html "Get an overview of existing agreements both as a provider and a consumer.") :arrow_upper_right:.

-   Discover the APIs Data Space Integration provides on the SAP Business Accelerator Hub and how to work with them. See [Using APIs To Work With Data Space Integration](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/17544cc377394d2885662fbda0bdd00b.html "Data Space Integration provides APIs for accessing and managing resources, which can be tested on the SAP Business Accelerator Hub. To interact with Data Space Integration using the API, you must create a service instance and service key for inbound authentication.") :arrow_upper_right:.


