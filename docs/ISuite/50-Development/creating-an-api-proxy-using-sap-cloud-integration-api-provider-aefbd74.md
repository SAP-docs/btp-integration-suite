<!-- loioaefbd743bee543f68b34a95be5f134c9 -->

# Creating an API Proxy using SAP Cloud Integration API Provider

Create an API proxy from list of APIs that is deployed in a SAP Cloud Integration tenant.



<a name="loioaefbd743bee543f68b34a95be5f134c9__prereq_uyp_vh1_hkb"/>

## Prerequisites

-   You should have already created an API provider of type SAP Cloud Integration in *Configure* \> *APIs* tab in the Integration Suite. To do so, see [Create an API Provider](create-an-api-provider-6b263e2.md).



<a name="loioaefbd743bee543f68b34a95be5f134c9__context_q5f_b31_hkb"/>

## Context

Instead of consuming the API services directly, application developers can access APIs exposed via API Management. You do so, by creating an API proxy that covers the service you want to expose. The API maps a publicly available HTTP endpoint backend service. Creating this API proxy lets , from the API Management handle the security and authorizations required to protect, analyze, and monitor your services. Here, you can see how to create an API proxy using an Integration Flow or an API from the list of artifacts deployed in SAP Cloud Integration tenant.

Instead of directly consuming API services, application developers can access APIs throughAPI Management. This is done by creating an API proxy that acts as a gateway for the service you want to expose. The API proxy maps a publicly available HTTP endpoint to a backend service. By creating this API proxy, API Management can handle the security and authorizations needed to protect, analyze, and monitor your services. In this guide, you will learn how to create an API proxy using either an Integration Flow or an API from the list of artifacts deployed in your Cloud Integration tenant.



## Procedure

1.  Log on to the Integration Suite.

2.  Choose *Configure* \> *APIs* from the left navigation.

3.  To expose a service as an API, choose *Create*.

4.  In order to choose an API of the type OData, REST, or SOAP and create an API Proxy, proceed as follows:

    1.  In the *Create API* dialog, select the *API Provider* radio button.

    2.  From the API provider dropdown, select an API provider that belongs to the type *Cloud Integration*.

        The dropdown list contains the providers that you’re connected to. If the provider you need isn’t listed, add an API provider of the type *Cloud Integration* from the *Configure* \> *APIs*. tab. For more information, see [Create an API Provider](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/6b263e2c1b2d4d9ba20bcd7872eedd9e.html?q=Create%20an%20API%20Provider).

    3.  Choose *Discover*.

        A list of Integration Flows and APIs belonging to type OData, REST, or SOAP appears from Cloud Integration.

    4.  Choose an API to connect with the API proxy.

    5.  Choose *Next*.

    6.  In the *Authentication* dialog, select one of the following authentication methods:

        -   *Basic* - Basic authentication is a method of user verification. If the API you have selected supports Basic authentication, you need to enter the credentials, which can be either a Username and Password or a Client ID and Client Secret. For more information, see [Setting Up Basic Inbound Authentication with ClientId and Clientsecret from Service Key in the Cloud Foundry Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/647eeb3eca5d4c299009cacd1332247e.html).

            > ### Note:  
            > Changing the user credentials for the API might affect proxy execution. However, if necessary, you can modify the user credentials after the proxy creation by following the instructions in the note of step \(6\):

        -   *Client Certificate* - Client Certificate authentication is another method of user verification. If the API you have chosen supports Client Certificate authentication, you have the option to upload a certificate in the provided section. The certificate should include both the public and private keys, as well as the certificate chain. The uploaded certificate will be stored in a Store, which is a collection of certificates. For more information, see [Setting Up Inbound Client Certificate Authentication, Cloud Foundry Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7f84d16aa42741efb08dc9875743e47c.html).

            If you choose:

            -   *Existing Store*:

                The *Existing Store* option refers to a certificate that has already been created and is currently stored in the system. When you select this option, you will have the ability to choose from a list of certificates that have been uploaded in either .p12 or .pfx format. To proceed, simply select the desired certificate from the *Store Name* dropdown menu. However, please note that you will need to provide the password for the store in order to access and utilize the chosen certificate.

                > ### Note:  
                > If you face any issues while importing the .pkcs/.p12 certificates, please consider checking for restricted characters in your password.
                > 
                > If your password for certificates contains any restricted characters such as \(! and \#\), import of such certificates might fail. Therefore, while creating the certificates please choose a password without these restricted characters and try importing again.

                1.  From the *Store Name* dropdown, choose an existing store.
                2.  Type in the respective password for the existing store.

            -   *New Store*:

            1.  Upload a certificate in either .p12 or .pfx format by selecting the *Browse* option. For more information on the certificates, see [here](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/778c7e7835ff46408aafe0d499720dc7.html).
            2.  Enter a unique name for the store in the *Store Name* field.
            3.  Enter a unique name for the certificate in the *Name* field.
            4.  Set a password for your certificate in the *Password* field.
            5.  Choose *Done*.

        -   To implement *OAuth2ClientCredentials* authentication for your API deployed in Cloud Integration, you will need to provide the following information:

            -   *Client ID*
            -   *Client Secret*
            -   *Token URL*

            The Client ID, Client Secret, and Token URL, are those obtained when you configure OAuth authentication, in particular the Client Credentials Grant variant, for Inbound calls from sender systems to the integration platform. For more information, see [Setting Up OAuth Inbound Authentication with Client Credentials Grant](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/6c052ce62b27449385d3e75aeeb08f05.html).


        In the *Create API* dialog, the *API Details* consisting of *Name*, *Title*, *Description*, *Host Alias*, *API Base Path*, and *Service Type* are auto populated.

    7.  Enter a short introductory text in the *Short Text* field.

    8.  Choose *Create*.

        An API provider is auto-created with the name that is populated in the *Name* field of the *Create API* dialog. This creates an API provider of type *Cloud Integration Flow*. This auto-created API provider helps in storing the user credentials provided in the *Authentication* dialog and connects to the API proxy.


5.  A *Create API* screen opens with the API proxy name on the top. You can edit the API proxy details, if necessary and choose*Save*.

    > ### Note:  
    > While creating API proxies for SOAP and REST, API resources aren’t autogenerated; you must add them manually.
    > 
    > While creating API proxies for OData API, autogeneration of resources may be possible in some cases.

6.  In the top-right corner of the screen, you have the *Deploy* and *Delete* option. Choosing *Deploy* will deploy the API proxy. On the other hand, if you choose *Delete*, the API proxy will get deleted. It's important to note that selecting *Save* will only create the API proxy without deploying it.

    > ### Note:  
    > To modify the credentials after creating the API proxy, please follow these steps::
    > 
    > 1.  Go to the *Configure* \> *APIs* tab and select the API. You'll find the auto-created API provider with the same name as the selected API.
    > 2.  Select the *Target EndPoint* tab.
    > 3.  Choose the link under *API Provider*. This is where the user credentials are stored.
    > 
    >     You'll get redirected to the *View API Provider* \> *Overview* tab.
    > 
    > 4.  Select the *Connection* tab.
    > 5.  On the top-right corner of the screen, choose *Edit*.
    > 6.  Modify the user credentials as needed.
    > 7.  Finally, click on the *Save* button to save the changes.

    **Related Links:**

    -   [Concepts of Secure Communication](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/35458089b5934f0ea49121c4ab5d6bb2.html)



