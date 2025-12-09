<!-- loio3b53c260afcd4ae785be5fdc0783c9a0 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Consume API Management Service Instance from Kyma

Kyma environment provides a fully managed Kubernetes runtime based on the open-source project "Kyma". You can use the Kyma environment to search and discover API Portal andDeveloper Hub applications.



<a name="loio3b53c260afcd4ae785be5fdc0783c9a0__section_g5c_xbc_ntb"/>

## Prerequisites

-   You already have a subaccount and have the required entitlements for *API Management, API Portal* and *API Management, Developer Hub*Developer Hub.

-   You’ve subscribed to *Integration Suite*, and have enabled *API Management, API Portal* and **Developer Hub** capability.

    > ### Note:  
    > If you’re using the API Management stand-alone service, ensure that you’ve already subscribed to API Management, API portal and Developer Hub.

-   Ensure that the Kyma environment has already been enabled. For more information, see [Getting Started in the Kyma Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/getting-started-in-kyma-environment?version=Cloud).

    > ### Note:  
    > You can also see the following tutorial for visual instructions to discover and consume APIs from Kyma: [Consume API Management Service Instance from Kyma](https://developers.sap.com/tutorials/api-mgmt-kyma-getting-started.html).




**Discover and Consume API Management Service Instance from Kyma**

Before creating the service key, the **API Management, API Portal** and the **API Management, Developer Hub** cluster services must be provisioned in the default namespace.

1.  Log on to SAP BTP Cockpit.

2.  Choose *Kyma Environment* tab and choose *Console URL: Link to dashboard* to navigate to the Kyma dashboard.

3.  Choose *Namespaces* from the left navigation pane. At this point, only the *default* namespace appears.

4.  From the left navigation pane, choose *Service Management* \> *BTP Service Instances*.

5.  Choose,*Create Service Instance +* and on the *Create Service Instance* dialog fill in the following:

    -   *Name*: Provide a name or generate it by choosing :arrows_clockwise:

    -   *Offering Name*: You can find the SAP BTP service offering name in the*Service Marketplace* of the SAP BTP cockpit. Search for the API Management, API Portal/ API Management, Developer Hub service and copy the name of the service instance.

    -   *Plan Name*: Similarly, you can find the relevant plan for the respective API Management, API Portal/ API Management,Developer Hub services in the*Service Marketplace* of the SAP BTP cockpit.


6.  Choose *Advance* tab on the *Create Service Instance* dialog and expand *Instance Parameters*.

    To create an instance of *API Management, API Portal*, enter `role` as the key in the first textbox and `APIPortal.Administrator` as the value in the second textbox.

    Similarly, to create an instance of *API Management, Developer Hub*, enter `role` in the first textbox and `AuthGroup.API.Admin` in the second textbox.

7.  Choose *Create*.

    You're directed to the *Service Management* \> *Instances* page, where an instance of the newly provisioned *API Management, API Portal* or *API Management, Developer Hub* service appears.




**Creating the Service Key**

To create the service key:

1.  Navigate to the instance that you just created and choose *Add Service Binding +*.

2.  Generate a *Name* for the service binding and select the *Service Instance Name* from the dropdown menu, and choose *Create*.

    The service instance name, secret, and external name appears under *Binding Data* on the *Instances* page.

3.  Select the link next to *Secret* and make a note of the *clientId*, *clientSecret* *orgId*,*tokenUrl* and the *url* details.

    You can use the *clientId*, *clientSecret* and the *tokenUrl* to fetch the token, and the application URL to perform operation on the APIs.


