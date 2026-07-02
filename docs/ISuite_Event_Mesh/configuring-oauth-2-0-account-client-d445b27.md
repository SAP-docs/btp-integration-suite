<!-- loiod445b27fe92042eebb48840718ba7394 -->

# Configuring OAuth 2.0 Account Client

You can access an external service provider's \(SAP Integration Suite, SAP BTP, Cloud Foundry environment\) OAuth 2.0 protected web service from an SAP S/4HANA, on-premise edition system. You need to provide credentials and an OAuth 2.0 client ID in the service provider.



<a name="loiod445b27fe92042eebb48840718ba7394__prereq_ry3_5kt_l2b"/>

## Prerequisites

-   You have the *Enterprise Event Enablement* administrator role.

-   You have the OAuth client ID, client secret and token endpoint of the `amqp10ws` protocol from the enterprise messaging service instance. For more information, refer to [Bind an Application to an Enterprise Messaging Service Instance](https://help.sap.com/viewer/bf82e6b26456494cbdd197057c09979f/Cloud/en-US/52407135f98144a6844b51dd2840e982.html).



## Context

The SAP S/4HANA, on-premise edition and private cloud edition system use the credentials and the OAuth 2.0 client ID whenever users request an OAuth 2.0 token to access the service provider's application.



## Procedure

1.  Execute transaction SPRO

2.  Select the *Open SAP Reference IMG* button

3.  Navigate to *SAP Customizing Implementation Guide ABAP Platform Enterprise Event Enablement Administration Channel Connection Settings*.

4.  Execute *Manage OAuth Client Setup*.

5.  Choose *Create*.

6.  In the *OAuth 2.0 Client Profile* field, select the */IWXBE/MGW\_MQTT* profile.

7.  Enter a *Configuration Name*.

8.  In the *OAuth 2.0 Client ID* field, enter the client ID you receive from the SAP Integration Suite, Event Mesh instance.

9.  Choose *OK*.

10. In the *Details* section, choose the *Administration* tab.

    1.  Enter the *Client Secret* you receive from the SAP Integration Suite, Event Mesh instance.

    2.  In the *Authorization Server Settings* section, enter the following:

        -   *Authorization Endpoint*: Enter the token endpoint URL of the service instance and replace `<token>` with `<authorize>`.
        -   *Token Endpoint*: Enter the token endpoint URL of the service instance.

        > ### Note:  
        > While entering the authorization endpoint and the token endpoint URL \(URL from the `amqp10ws` endpoint\), do not prefix `http://` with it.

    3.  In the *Access Settings* section, enter the following:

        -   *Resource Access Authentication*: Select *Header Field*.
        -   *Selected Grant Type*: Select *Client Credentials*.

    4.  \(Optional\) Enter the proxy settings details.


11. Choose *Save*.


**Related Information**  


[Creating SM59 Destination](creating-sm59-destination-5c684ae.md "As an administrator, you create an SM59 destination to connect to the instance created for Event Mesh in SAP Integration Suite.")

[Managing Channels and Parameters](managing-channels-and-parameters-c09c2bf.md "A channel represents a single connection to a service instance of Event Mesh in SAP Integration Suite.")

