<!-- loio24a2c37abd754915a74ae0914bebaa5b -->

# Accessing API Management APIs Programmatically

The *apiportal-apiaccess* plan offers external applications the ability to access the public APIs of the SAP Integration Suite API Management capability. These APIs are used by the external applications to perform CRUD operations on API Management features like API proxies or products. These APIs are built on REST and OData principles and are extensively documented on the SAP Business Accelerator Hub.



<a name="loio24a2c37abd754915a74ae0914bebaa5b__section_r4c_mzb_plb"/>

## About the Plan

The *apiportal-apiaccess* plan allows you to programmatically import/export API proxies, create products, key value maps. It is especially useful when integrating API Management with a CI/CD process or when migrating from a Neo to Cloud Foundry environment using the migration tool.

The API Access plan allows you to generate a service key by creating a service instance. By creating a service instance, you can generate a service key that includes the application url, clientId, clientSecret, and tokenUrl is used to generate a bearer token with the help of a REST Console. This Bearer Token, along with the application url and API endpoint are used to trigger the API. Therefore, bearer token acts like a key to access the APIs.



<a name="loio24a2c37abd754915a74ae0914bebaa5b__section_ybp_nyb_plb"/>

## Prerequisites

-   You've enabled API Management capability using SAP Integration Suite. For more information, refer [Subscribing to Integration Suite](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/8a3c8b7a6b1c4f249bb81d11644ef806.html?version=CLOUD) and [Activating Capabilities](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/2ffb343c163c48a4b3a90f9f3c487328.html?version=CLOUD).

    **OR**

    You have subscribed to the standalone *API Management, API portal* tile in the Cloud Foundry environment. For more information, see [Set Up API Portal Application](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/29c281b4a002404eba44e91c6fad0d34.html "To create APIs, products, import policy templates, and view applications, set up the API portal application.") :arrow_upper_right:.

-   As a subaccount administrator, you additionally need the role of \(org member\) and *space developer* in the Cloud Foundry space in which the SAP Integration Suite is provisioned.


To enable API access for API Management, API portal execute the steps in the sections below:



<a name="loio24a2c37abd754915a74ae0914bebaa5b__section_s3d_qgc_plb"/>

## Creating a Service Instance in the API Management, API portal

Create a service instance using API Access plan to generate a service key.

1.  In your web browser, open the *SAP BTP Cockpit* - [https://cockpit.btp.cloud.sap](https://cockpit.btp.cloud.sap).
2.  From your *Subaccount*, navigate to *Spaces* in your Cloud Foundry environment and choose *Services* \> *Service Marketplace.*
3.  Select the *API Management, API portal* tile, and in the details section, choose *Create*.

    > ### Note:  
    > If you are unable to view the *API Management, API Portal* tile, please check your entitlements. For more information, see [Managing Entitlements and Quotas Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c8248745dde24afb91479361de336111.html).

4.  In the *New Instance or Subscription* dialog that opens, choose the *apiportal-apiaccess* plan.
5.  Enter a name for your instance in the *Instance Name* field and choose *Next*.
6.  Under *Parameters*, paste one of the following JSON codes, to assign a specific role and choose *Next*.

    The following roles are supported for the current scenario:

    -   Assign `APIPortal.Administrator` role to access the API portal APIs and perform operations like create, update, delete on various API portal entities as specified in the SAP Business Accelerator Hub.

        ```
        
        {
            "role": "APIPortal.Administrator"
        }
        
        ```

    -   Assign `APIPortal.Guest` role to access the API portal APIs in read-only mode. You can view the API portal entities as specified in the API Business Hub.

        ```
        
        {
            "role": "APIPortal.Guest"
        }
        ```

    -   Assign `APIManagement.SelfService.Administrator` role to configure additional virtual hosts.

        ```
        
        {
            "role": "APIManagement.SelfService.Administrator"
        }
        ```


7.  Review and verify the instance details and choose *Create*.

You'll receive a success message that your service instance is created.

> ### Note:  
> If the service instance creation fails, you may encounter the following errors:
> 
> -   Service instance provision failed with error: "Could not find credentials service."
> 
>     Solution: Retry after some time. If the issue persists, report the issue by creating an incident in the [SAP Support Portal](https://support.sap.com/en/index.html). Please use the component OPU-API-OD-DT for reporting..
> 
> -   "An error occurred during the clone creation due to invalid role creation"
> 
>     Solution: Ensure the roles are entered in the correct JSON format as shown in Step 6.

Once the service instance is created successfully, generate a service key from the steps given below:



<a name="loio24a2c37abd754915a74ae0914bebaa5b__section_k4g_d4c_plb"/>

## Creating a Service Key

1.  Choose the created service instance link from the visible list.
2.  In the left-hand pane, navigate to *Service Keys* \> *Create Service Key*.
3.  In the *Create Service Key* dialog that opens, provide a *Name* and *Description* \(optional\).
4.  In the text box enter one of the following payloads as per your requirement:


    <table>
    <tr>
    <th valign="top">

    To create service key of credential type…
    
    </th>
    <th valign="top">

    Use payload…
    
    </th>
    <th valign="top">

    Level of Security
    
    </th>
    <th valign="top">

    Important Notes
    
    </th>
    <th valign="top">

    Sample of generated credentials
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    "binding-secret"\(without payload\)
    
    </td>
    <td valign="top">
    

    
    </td>
    <td valign="top">
    
    Medium
    
    </td>
    <td valign="top">
    
    For binding-secret, the clientSecret generated for every key is unique.
    
    </td>
    <td valign="top">
    
    For admin role:

    ```
    {
        "url": "https://apiportal-application-url",
        "tokenUrl": "https://token-enpoint-url/oauth/token",
    	"clientId": "your-client-id",	
    	"clientSecret": "xxxxxxxxxxxxxxxxxxxxxxx="
    }
    ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `"binding-secret"(with payload)` 
    
    </td>
    <td valign="top">
    
    ```
    {
       "xsuaa":{
          "credential-type":"binding-secret"
       }
    }
    
    ```


    
    </td>
    <td valign="top">
    
    Medium
    
    </td>
    <td valign="top">
    
    For binding-secret, the clientSecret generated for every key is unique.
    
    </td>
    <td valign="top">
    
    For admin role:

    ```
    {
    	"url": "https://apiportal-application-url",
    	"tokenUrl": "https://token-enpoint-url/oauth/token",
    	"clientId": "your-client-id",	
    	"clientSecret": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx="
    }
    ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `"x509"`

    \(certificate based\)
    
    </td>
    <td valign="top">
    
    ```
    {
       "xsuaa":{
          "credential-type":"x509",
          "x509":{
             "key-length":2048,
             "validity":65,
             "validity-type":"DAYS"
          }
       }
    }
    
    ```


    
    </td>
    <td valign="top">
    
    High
    
    </td>
    <td valign="top">
    
    For X509, ensure that the credential rotation is done based on the validity provided in the payload. For example, delete and create a new service key every 65 days.
    
    </td>
    <td valign="top">
    
    For admin role:

    ```
    {
        "url": "https://xxxxxxxxxxxx.cfapps.sap.hana.ondemand.com",
        "certificate": "xxxxxxxxxxxxxxxxxxx",
        "certurl": "https://xxxxxx.authentication.cert.sap.hana.ondemand.com",
        "clientId": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "privateKey": "xxxxxxxxxxxxxxxxxxxxxx",
        "tokenUrl": "https://xxxxxx.authentication.sap.hana.ondemand.com/oauth/token"
    }
    ```


    
    </td>
    </tr>
    </table>
    
5.  Click *Save*. The client credentials like *url*, *clientId*, *clientSecret*, and *tokenUrl* details appear for the given instance name.

    The application *url* is used to make API calls.

    The *clientId* and *clientSecret* are necessary credentials required to fetch the Bearer Token.

    The *tokenUrl* is used to fetch the bearer token.

    Example:

    ```
    url --cert client.crt --key client.key --location --request POST '<URL from the response>' \
    --header 'Content-Type: application/x-www-form-urlencoded' \
    --header 'Authorization: No Auth \
    --data '{"client_id":"clientid"}' ‘grant_type=client_credentials' 
    
    ```

    The generated credentials \(tokenUrl, clientId and clientSecret\) can then be used by an application developer to authenticate the client \(or user\) via OAuth, and access the APIs exposed by the service.

    Copy the client credentials in a notepad.

    > ### Note:  
    > Once your client is setup you can use it to authenticate against the x509 endpoint by providing the client certificate and key.
    > 
    > Create the certificate.cer and certificate.key files based on the public and private keys obtained from the x509 credentials respectively.
    > 
    > For certificate.cer file:
    > 
    > 1.  Copy the "certificate" value starting from `-----BEGIN CERTIFICATE----- all the way to -----END CERTIFICATE-----\n` \(the certificate value might contain multiple certificates\). Make sure you copy all the certificates.
    > 
    > 2.  Paste it in a text editor. Find and replace all the occurrences of \\\\n by \\n.
    > 
    > 3.  Save the file as `certificate.cer`.
    > 
    > 
    > For certificate.key file:
    > 
    > 1.  Copy the "certificate" value starting from `-----BEGIN RSA PRIVATE KEY-----\n... all the way to ....-----END RSA PRIVATE KEY-----\n`
    > 
    > 2.  Paste it in a text editor. Find and replace all the occurrences of \\\\n by \\n.
    > 
    > 3.  Save the file as `certificate.key`.
    > 
    > 
    > Open a command prompt/terminal in the folder where you have saved the certificate files and execute the following curl command to get the response in the `my-oauth-response.json` file in the same folder. From this file, you can fetch the bearer token from the value of "access\_token".
    > 
    > ```
    > curl --cert certficate.cer --key certificate.key --location --request POST '<certurl from the servicekey x509 credentials>/oauth/token?grant_type=client_credentials' \
    > --header 'Content-Type: application/x-www-form-urlencoded' \
    > --data-urlencode 'client_id=<clientId from the servicekey x509 credentials>' \
    > --cert certificate.cer \
    > --key certificate.key \
    >   > my-oauth-response.json
    > 
    > ```


> ### Note:  
> You can update an already provisioned service instance of an API access plan by performing the following steps:
> 
> **Prerequisite:**You must have the Cloud Foundry CLI installed.
> 
> 1.  Log in to the Cloud Foundry CLI by running the `cf login` command.
> 2.  Select *Org*.
> 3.  Run the following command to update your service instance. `cf update-service <service-instance-name> -c <empty-json-file>.json`.
> 
>     > ### Sample Code:  
>     > ```
>     > Sample json: {}
>     > ```



<a name="loio24a2c37abd754915a74ae0914bebaa5b__section_dsn_k54_dmb"/>

## Next Steps: Obtaining a Bearer Token

In the REST Console:

1.  Paste the copied *tokenUrl*. Append `?grant_type=client_credentials` to the *tokenUrl*.
2.  Choose `Basic Auth` as the `Authorization` type.
3.  Similarly, paste the *clientId* and *clientSecret* in the place of `Username` and `Password`.
4.  Make a POST Call.
5.  Obtain the Bearer Token from the output and copy it in a notepad.
    -   Now, to trigger an API, in the same REST Console, append the API endpoint \(obtained from the API portal APIs that are located in the SAP API Management package in SAP Business Accelerator Hub\) to the *url*.

        > ### Note:  
        > Currently, the *apiportal-apiaccess* plan allows you to access only the API Management APIs from the SAP API Management package in SAP Business Accelerator Hub.

    -   Choose `Bearer Token` as the `Authorization` type and paste the copied Bearer Token in the specified space.
    -   Include payloads, if needed.


> ### Example:  
> This example summerizes the steps that we have executed so far.
> 
> To fetch all the available API proxies in your API portal, you can make a call to the URL that appears in the endpoint`<url>/apiportal/api/1.0/Management.svc/APIProxies`.
> 
> To successfully trigger this API, you need to enable the 'API portal API Access Plan'. Once the plan is enabled and suitable roles are assigned, you can generate a service key using the created service instance. The service key should include your URL, client ID, client secret, and token URL. Copy the URL and append \`/apiportal/api/1.0/Management.svc/APIProxies\` to it, as shown here: `<url>/apiportal/api/1.0/Management.svc/APIProxies`
> 
> In addition, to establish a connection with this API, you will need to generate a bearer token. Take the token URL and append the grant type to it: `https://token-enpoint-url/oauth/token?grant_type=client_credentials`
> 
> Now, execute a GET operation on this API with the Client ID and Client secret as your Basic auth credentials. The bearer token will be embedded in the response code. Next, append the bearer token to the URL as shown here: `<url>/apiportal/api/1.0/Management.svc/APIProxies/<bearer token>`
> 
> By calling this URL, you will be able to list all the API proxies available in your API portal.

