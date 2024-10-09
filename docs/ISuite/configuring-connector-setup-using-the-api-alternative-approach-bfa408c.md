<!-- loiobfa408ca806d4b9f9a891b37901d75aa -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Configuring Connector Setup Using the API \(Alternative Approach\)

Onboard with Catena-X and get started in Data Space Integration by entering your data space identifiers and Cloud Integration parameters. This setup method uses an API.



<a name="loiobfa408ca806d4b9f9a891b37901d75aa__prereq_h5t_pd5_jyb"/>

## Prerequisites

> ### Note:  
> We want your feedback! Let us know what you think about this documentation by completing this two-minute survey: [SAP Documentation User Experience Survey](https://sapinsights.eu.qualtrics.com/jfe/form/SV_bJ9iYJuEJNrZNUq).

-   You've completed the steps described in [Preparatory Steps](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/247522607cdc4dbebe6dbf09068aaa7e.html "Before you can perform the onboarding steps that are specific to Data Space Integration, you must be onboarded to SAP Integration Suite and have enabled Cloud Integration.") :arrow_upper_right: where you activate SAP Integration Suite and the Cloud Integration capability.

-   You've completed the steps described in [Activating the Capability](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/be375cb46b4a4fada37e62b90efcf0d8.html "Learn how to activate the Data Space Integration capability within SAP Integration Suite.") :arrow_upper_right: where you add Data Space Integration to your list of active capabilities of SAP Integration Suite.
-   You've completed the steps described in [Configuring User Access](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/cc811d8612d64ede9ccf7edcb390ecc2.html "Before users can access the application, you need to assign the relevant role collections to them.") :arrow_upper_right: where you define user roles for Data Space Integration.

-   You've completed the steps described in [Preparing Cloud Integration](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/7014b7d65f2d479d9328d302e5ec0499.html "Data Space Integration interacts with Cloud Integration, so you must perform a few preparatory steps before you can get started with Data Space Integration.") :arrow_upper_right: where you create Cloud Integration service keys.

-   You've completed the steps described in [Create Technical Users in Landscape Portal](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/fb8d9abc5a35406c8565701ddcc7d217.html "Prepare your technical users in the landscape portal of your chosen data space.") :arrow_upper_right: where you create two technical users in the landscape portal of your chosen data space.


> ### Note:  
> The steps here describe the process for configuring the connector setup using an API.
> 
> If you want to do the configuration using the user interface of Data Space Integration, see [Configuring Connector Setup Using the UI (Recommended Approach)](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/802257f4a72642ad80812009e4bd3c54.html "Onboard with Catena-X and get started in Data Space Integration by entering your data space identifiers and Cloud Integration parameters. This setup method uses the user interface of Data Space Integration.") :arrow_upper_right:.



<a name="loiobfa408ca806d4b9f9a891b37901d75aa__steps_p54_vlj_pyb"/>

## Procedure

1.  First, create credentials to access Data Space Integration. The service instance and key your create in this step help you retrieve the connector URL for Data Space Integration.

    1.  Go to the SAP BTP cockpitand navigate to your subaccount that has SAP Integration Suite enabled. From there, go to *Cloud Foundry* \> *Spaces* \> *Your space* \> *Services* \> *Instances*.

    2.  Select *Create* to create a new service instance and select `Data Space Integration API Access`. In the *Plan* field, enter `api`, and add an instance name. Then, choose *Next*.

        > ### Remember:  
        > If `Data Space Integration API Access` isn't available to you, check whether you've enabled beta features for your SAP BTP subaccount. See [Initial Setup](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/e8539cf283184169a71fe45be6719bff.html "Learn how to set up the Data Space Integration capability within SAP Integration Suite.") :arrow_upper_right:.

    3.  Next, select the applicable roles to enforce user authorization. For this specific process, any role works, even `AuthGroup_DataspaceReadOnly`. For an overview of all roles, see [Personas and Roles](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/bb8cd79bd90e4b70ae424d7ff3f8c1e8.html "Get an overview of the personas and roles in Data Space Integration and the tasks they can accomplish.") :arrow_upper_right:.

        Once the roles are selected, select `client_credentials` as the grant type and choose *Next*.

    4.  Review the information and select *Create*.

    5.  Now, you need to create a service key for your service instance - either with ClientID/Secret or Certificate. For the service instance that was created, select *Create Service Key*. Enter a name for the service key and for the *Key Type* select `ClientID/Secret` or `Certificate`. Leave the rest of the fields as they are. Select *Create*.

        This service key contains the connector URL, which you'll need in the next step, so have it ready.


2.  You now need the URL of the Data Space Integration endpoint. You can find this information in the instance of the `Data Space Integration API Access` that you set up in a previous step.

    1.  Go to the SAP BTP cockpit and navigate to your subaccount that has SAP Integration Suite enabled. From there, go to *Cloud Foundry* \> *Spaces* \> *Your space* \> *Services* \> *Instances*. Select `Data Space Integration API Access`.

    2.  A detail view opens. Click on the *More* icon \(<span class="SAP-icons-V5"></span> More\) and select *View*.

    3.  The credentials open. Copy the URL.


3.  To register your connector and connect to the data space, make the following POST call filled with your specific details:

    ```
    POST	/api/v1/dsi/registration
    						
    						{
    						"BPN": "<business partner number>",
    						"location": "<location code>",
    						"connectorName": "<name of the connector>",
    						"connectorUrl": "<URL of the connector>",
    						"connectorUserClientId": "<client ID of the offer management user>",
    						"connectorUserClientSecret": "<client secret of the offer management user>",
    						"centralIdpTokenUrl": "<central IDP token URL>",
    						"backendPortalUrl": "<backend portal URL>",
    						"bdrsServerUrl":"<BDRS server URL>",
    						"did":"<decentral identifier>",
    						"trustedIssuers":["<trusted issuers>"], 
    						"stsDimClientId": "<client ID of the identity wallet management user>",
    						"stsDimClientSecret": "<client secret of the identity wallet management user>",
    						"stsDimTokenUrl": "<IATP STS OAuth token URL>",
    						"stsDimUrl": "<IATP STS decentral identity management URL>"
    						}
    ```

4.  Now, register Cloud Integration using the Data Space Integration onboarding API.

    1.  For the next calls, you need the Data Space Integration connector URL. You've already performed parts of this procedure: Go to the SAP BTP cockpit and navigate to your subaccount that has SAP Integration Suite enabled. From there, go to *Cloud Foundry* \> *Spaces* \> *Your space* \> *Services* \> *Instances*. Select `Data Space Integration API Access`. In the Details view, click the *More* icon \(<span class="SAP-icons-V5"></span>\) and select *View*.

        > ### Note:  
        > Make sure that you're using the `Access Token URL`, `Client ID`, and `Client Secret` from the `Data Space Integration API Access (Plan API)` for the call.

    2.  The credentials open. Copy the URL, and save it for later.

    3.  In the Data Space Integration connector URL, call the following endpoint with the API parameters \(ciapi\) and runtime parameters \(cirt\) from the Cloud Integration service keys. To get these parameters, access the SAP BTP cockpit, go to *Instances and Subscriptions*, and open the details view of the service keys. See: [Preparing Cloud Integration](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/7014b7d65f2d479d9328d302e5ec0499.html "Data Space Integration interacts with Cloud Integration, so you must perform a few preparatory steps before you can get started with Data Space Integration.") :arrow_upper_right:.

        ```
        PUT	/api/v1/dsi/credentials/dataplane
        									
        									[     
        									{
        									"clientid": "<clientid>",
        									"clientsecret":"<clientsecret>",
        									"url": "<URL>",
        									"tokenurl": "<tokenurl>"
        									},
        									{
        									"clientid": "<clientid>",
        									"clientsecret": "<clientsecret>",
        									"url": "<URL>",
        									"tokenurl": "<tokenurl>"
        									}
        									]
        ```

        > ### Note:  
        > You can update the credentials you enter here anytime, for example, if they've been exposed or if they've expired after 12 months.


5.  Use the Data Space Integration connector URL to call the following endpoint:

    > ### Sample Code:  
    > ```
    > POST	/api/v1/dsi/dataplane
    > ```

    The provisioning of Data Space Integration can take up to 20 minutes. You can check the status by triggering a `GET` call to the following URL: `/api/v1/dsi/dataplane`.




<a name="loiobfa408ca806d4b9f9a891b37901d75aa__result_t3z_p25_jyb"/>

## Results

You can now use Data Space Integration.



<a name="loiobfa408ca806d4b9f9a891b37901d75aa__postreq_cy4_m4c_kcc"/>

## Next Steps

Depending on your role, you can now get started with one of the following tasks:

-   Learn how to work with assets, policies, and contract definitions as a provider. See [Data Spaces - Providing Assets in a Data Space](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/e438274e254449429a1d9752b24a3c78.html "In Data Space Integration, as a provider, you want to create assets and policies, and bundle them into contract definitions to facilitate data exchange between different members of your network.") :arrow_upper_right:.

-   Learn how to discover offers and consume assets provided by other participants of a data space. See [Data Spaces - Consuming Data Space Assets](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/32a37405e68246669bb3b4c1a8995e7c.html "In Data Space Integration, as a consumer, you want to consume data assets provided by other members of the data space.") :arrow_upper_right:.

-   Monitor your active contract agreements. See [Monitoring Agreements](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/b0169176b43b4e02a03b3b24c5adf8b6.html "Get an overview of existing agreements both as a provider and a consumer.") :arrow_upper_right:.

-   Discover the APIs Data Space Integration provides on the SAP Business Accelerator Hub and how to work with them. See [Using APIs To Work With Data Space Integration](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/17544cc377394d2885662fbda0bdd00b.html "Data Space Integration provides APIs for accessing and managing resources, which can be tested on the SAP Business Accelerator Hub. To interact with Data Space Integration using the API, you must create a service instance and service key for inbound authentication.") :arrow_upper_right:.


