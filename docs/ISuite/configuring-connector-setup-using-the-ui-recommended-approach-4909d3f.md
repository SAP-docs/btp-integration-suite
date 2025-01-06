<!-- loio4909d3fd2dd94227bdd6d6b515fd60da -->

# Configuring Connector Setup Using the UI \(Recommended Approach\)

Onboard with Catena-X and get started in Data Space Integration by entering your data space identifiers and Cloud Integration parameters. This setup method uses the user interface of Data Space Integration.



<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__prereq_ic1_kkd_l1c"/>

## Prerequisites

-   You've completed the steps described in  <?sap-ot O2O class="- topic/xref " href="247522607cdc4dbebe6dbf09068aaa7e.xml" text="" desc="" xtrc="xref:1" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?>  where you activate SAP Integration Suite and the Cloud Integration capability.

-   You've completed the steps described in  <?sap-ot O2O class="- topic/xref " href="be375cb46b4a4fada37e62b90efcf0d8.xml" text="" desc="" xtrc="xref:2" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?>  where you add Data Space Integration to your list of active capabilities of SAP Integration Suite.

-   You've completed the steps described in  <?sap-ot O2O class="- topic/xref " href="cc811d8612d64ede9ccf7edcb390ecc2.xml" text="" desc="" xtrc="xref:3" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?>  where you define user roles for Data Space Integration.

-   You've completed the steps described in  <?sap-ot O2O class="- topic/xref " href="7014b7d65f2d479d9328d302e5ec0499.xml" text="" desc="" xtrc="xref:4" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?>  where you create Cloud Integration service keys.

-   You've completed the steps described in  <?sap-ot O2O class="- topic/xref " href="fb8d9abc5a35406c8565701ddcc7d217.xml" text="" desc="" xtrc="xref:5" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?>  where you create two technical users in the landscape portal of your chosen data space.


> ### Note:  
> The steps here describe the process for configuring the connector setup using the user interface of Data Space Integration.
> 
> If you want to do the configuration using the API, see  <?sap-ot O2O class="- topic/xref " href="8ba870459c8a4804874db89542fbab5d.xml" text="" desc="" xtrc="xref:6" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .



<a name="loio4909d3fd2dd94227bdd6d6b515fd60da__steps_yct_rkd_l1c"/>

## Procedure

1.  First, register the connector in Data Space Integration.

    1.  Open SAP Integration Suite and navigate to *Settings* \> *Data Spaces*. Choose *Onboard*.

        > ### Note:  
        > If *Settings* \> *Data Spaces* isn't visible to you, you might not have the correct role assigned to your user. Only users with the role `DataspaceTechnicalAdmin` can perform the onboarding.

    2.  In the first tab *Connect to a Data Space*, select the *Landscape* you want to onboard to. It must be the same landscape in which you've created the *Identity Wallet Management* and *Offer Management* role in  <?sap-ot O2O class="- topic/xref " href="fb8d9abc5a35406c8565701ddcc7d217.xml" text="" desc="" xtrc="xref:7" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

    3.  Enter the *Business Partner Number* of the company account.

    4.  Choose a *Connector Name* under which you want the connector to be registered in the portal. The *Connector URL* is prefilled automatically. You can still edit it in case you want to use a custom domain or protect it using API management.

    5.  Fill in the *Offer Management User* information. You can retrieve these details from the *Offer Management* user that you created in the landscape portal.

    6.  Fill in the *Decentral Identity Verification* information. Enter the *IATP STS OAuth Token URL* and the corresponding *Client ID* and *Client Secret*. You can retrieve the client details from the *Identity Wallet Management* user you created in the landscape portal. The other information in this section is filled in automatically.

    7.  Choose *Save*.

        You can now move on to the next tab, *Prepare Connection to Cloud Integration*.


2.  In the *Prepare Connection to Cloud Integration* tab, you're preparing the connection to Cloud Integration, for which you need to enter two service keys.

    1.  Enter the required *API Parameters* from the Cloud Integration service key *Process Integration Runtime*, plan `api`. You can enter the parameters manually or choose *Paste Service Key* to paste the data.

        To get these parameters, access the SAP BTP cockpit, go to *Instances and Subscriptions*, and select the relevant service key. In the expanding details view, choose *key* and then *Copy JSON*. See also  <?sap-ot O2O class="- topic/xref " href="7014b7d65f2d479d9328d302e5ec0499.xml" text="" desc="" xtrc="xref:8" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

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

-   Learn how to work with assets, policies, and contract definitions as a provider. See  <?sap-ot O2O class="- topic/xref " href="e438274e254449429a1d9752b24a3c78.xml" text="" desc="" xtrc="xref:9" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

-   Learn how to discover offers and consume assets provided by other participants of a data space. See  <?sap-ot O2O class="- topic/xref " href="32a37405e68246669bb3b4c1a8995e7c.xml" text="" desc="" xtrc="xref:10" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

-   Monitor your active contract agreements. See  <?sap-ot O2O class="- topic/xref " href="b0169176b43b4e02a03b3b24c5adf8b6.xml" text="" desc="" xtrc="xref:11" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

-   Discover the APIs Data Space Integration provides on the SAP Business Accelerator Hub and how to work with them. See  <?sap-ot O2O class="- topic/xref " href="17544cc377394d2885662fbda0bdd00b.xml" text="" desc="" xtrc="xref:12" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/4909d3fd2dd94227bdd6d6b515fd60da.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .


