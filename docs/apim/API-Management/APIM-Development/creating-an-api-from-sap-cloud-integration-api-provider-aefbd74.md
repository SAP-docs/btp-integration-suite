<!-- loioaefbd743bee543f68b34a95be5f134c9 -->

# Creating an API from SAP Cloud Integration API Provider

Create an API proxy from list of APIs that is deployed in a SAP Cloud Integration tenant.



<a name="loioaefbd743bee543f68b34a95be5f134c9__prereq_uyp_vh1_hkb"/>

## Prerequisites

-   You should have already created an API provider of type SAP Cloud Integration*Configure* tab in the API portal. To do so, see [Create an API Provider](create-an-api-provider-6b263e2.md).



<a name="loioaefbd743bee543f68b34a95be5f134c9__context_q5f_b31_hkb"/>

## Context

Instead of consuming the API services directly, application developers can access APIs exposed via API Management. You do so, by creating an API proxy that covers the service you want to expose. The API maps a publicly available HTTP endpoint backend service. Creating this API proxy lets , from the API Management handle the security and authorizations required to protect, analyze, and monitor your services. Here, you can see how to create an API proxy using an Integration Flow or an API from the list of artifacts deployed in SAP Cloud Integration tenant.



## Procedure

1.  Log on to the API portal.

2.  Choose the navigation icon on the left and choose *Develop*.

3.  To expose a service as an API, choose *Create*.

4.  In order to choose an API of the type OData, REST, or SOAP and create an API Proxy, proceed as follows:

    1.  In the *Create API* dialog, select the *API Provider* radio button.

    2.  From the API Provider dropdown, select an API Provider that belongs to the type *Cloud Integration*.

        The dropdown list contains the providers that you’re connected to. If the provider you need isn’t listed, add an API provider of type *Cloud Integration* from the *Configure*. tab. For more information, see [Create an API Provider](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/6b263e2c1b2d4d9ba20bcd7872eedd9e.html?q=Create%20an%20API%20Provider).

    3.  Choose *Discover*. A list of Integration Flows and APIs belonging to type OData, REST, or SOAP appears from Cloud Integration.

    4.  Choose an API to connect with the API Proxy.

    5.  Choose *Next*.

    6.  In the *Authentication* dialog, if you select:

        -   *Basic* - A Basic authentication is a mode of user verification. If your selected API supports *Basic* authentication, enter the credentials, either *Username* and *Password* or *Client ID* and *Client Secret*. For more information, see [Setting Up Basic Inbound Authentication with ClientId and Clientsecret from Service Key in the Cloud Foundry Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/647eeb3eca5d4c299009cacd1332247e.html).

            > ### Note:  
            > Changing the user credentials for the API might affect proxy execution. However, if necessary, you can modify the user credentials after the proxy creation by following the instructions in the note of step \(6\):

        -   *Client Certificate* - A Client Certificate authentication is a mode of user verification. If your selected API supports*Client Certificate* authentication, you can upload the certificate\(consisting of public and private key including the certificate chain\) in the provided section. The uploaded certificate is stored under a Store \(collection of certificates\). For more information, see [Setting Up Inbound Client Certificate Authentication, Cloud Foundry Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7f84d16aa42741efb08dc9875743e47c.html).

            If you choose:

            -   *Existing Store*:

                The *Existing Store* consists of an already created certificate from the store, that is, selecting *Existing Store* enlists only the stores created by uploading certificates of format .p12 or .pfx. When you choose such a certificate from the *Store Name*, you need to have the password for the Store handy.

                > ### Note:  
                > If you face any issues while importing the .pkcs/.p12 certificates, please consider checking for restricted characters in your password.
                > 
                > If your password for certificates contains any restricted characters such as \(! and \#\), import of such certificates might fail. Therefore, while creating the certificates please choose a password without these restricted characters and try importing again.

                1.  From the *Store Name* dropdown, choose an existing Store.
                2.  In the section *Password*, type in the respective password for the existing Store.

            -   *New Store*:

            1.  Upload a certificate of format .p12 or .pfx format by choosing *Browse*. For more information on the certificates, see [here](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/778c7e7835ff46408aafe0d499720dc7.html).
            2.  Provide a unique name to the store, in the section *Store Name*.
            3.  Provide a unique certificate name, in the field *Name*.
            4.  Set a password for your certificate in the section *Password*.
            5.  Choose *Done*.

        -   *OAuth2ClientCredentials* You can choose to use OAuth2ClientCredentials authentication for your API deployed in SAP Cloud Integration. You would need to enter the following:

            -   *Client ID*
            -   *Client Secret*
            -   *Token URL*

            The Client ID, Client Secret, and Token URL, are those obtained when you configure OAuth authentication, in particular the Client Credentials Grant variant, for Inbound calls from sender systems to the integration platform. For more information, see [Setting Up OAuth Inbound Authentication with Client Credentials Grant](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/6c052ce62b27449385d3e75aeeb08f05.html) 


        In the *Create API* dialog, the *API Details* consisting of *Name*, *Title*, *Description*, *Host Alias*, *API Base Path*, and *Service Type* are auto populated.

    7.  Choose *Create*.

        An API Provider is auto-created with the name that is populated in the *Name* field of the *Create API* dialog. This auto-created API provider helps in storing the user credentials provided in the *Authentication* dialog and connects to the API Proxy.


5.  A *Create API* screen opens with the API Proxy name on the top. You can edit the API Proxy details, if necessary and choose *Save*.

    > ### Note:  
    > While creating API proxies for SOAP and REST, API resources aren’t autogenerated; you must add them manually.
    > 
    > While creating API proxies for OData API, autogeneration of resources may be possible in some cases.

6.  In the top-right corner of the screen, you can either choose *Deploy* to create and deploy the API Proxy or *Cancel* to delete the API Proxy.

    > ### Note:  
    > Choosing *Save* will only create an API Proxy and doesn't deploy an API Proxy.
    > 
    > You can modify the credentials after the API Proxy execution by following the steps:
    > 
    > 1.  Navigate to the auto-created API Provider with the same name as that of your selected API in the *Develop* tab.
    > 2.  Choose *Target EndPoint*.
    > 3.  Choose the link under the *API Provider* section. This API Provider has the user credentials stored.
    > 4.  Choose *Connection*.
    > 5.  Select *Edit* on the top-right corner of the screen. Modify the user credentials.
    > 6.  Choose *Save*.

    **Related Links:**

    -   [Concepts of Secure Communication](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/35458089b5934f0ea49121c4ab5d6bb2.html)



