<!-- loiodabee6e347f645a6805ec5b29f5d578c -->

# Accessing API business hub enterprise APIs Programmatically

The *devportal-apiaccess* plan allows you to access the API business hub enterprise APIs to programmatically onboard developers, create applications, and more.



<a name="loiodabee6e347f645a6805ec5b29f5d578c__section_e2h_vdn_ylb"/>

## About the Plan

The service key, consisting of url \(application url\), clientId, clientSecret, and tokenUrl is used to generate a bearer token with the help of a REST client. This bearer token, along with the application url and API endpoint, is used to trigger the APIs.

This topic explains how to enable API access for API business hub enterprise.



<a name="loiodabee6e347f645a6805ec5b29f5d578c__section_ybp_nyb_plb"/>

## Prerequisites

-   If you've enabled API Management capability using Integration suite, ensure that you've also enabled API business hub enterprise in Integration suite. For more information, refer [Subscribing to Integration Suite](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/8a3c8b7a6b1c4f249bb81d11644ef806.html?version=CLOUD) and [Activating Capabilities](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/2ffb343c163c48a4b3a90f9f3c487328.html?version=CLOUD). To access API business hub enterprise from Integration Suite, select API business hub enterprise from the *Navigation Links* on the header.

    > ### Note:  
    > Please ensure that you can access API business hub enterprise before creating an instance.

-   You have the `space developer` role assigned to you.
-   You have created a service instance under the *Authorization and Trust Management* tile.
    1.  In your web browser, open the *SAP BTP Cockpit* - [https://cockpit.btp.cloud.sap](https://cockpit.btp.cloud.sap).
    2.  From your *Subaccount*, navigate to *Spaces* in your Cloud Foundry environment and choose *Services* \> *Service Marketplace*.
    3.  Choose *Authorization and Trust Management* \> *Instances* \> *New Instance*.
    4.  In the *Create Instance* dialog that opens, choose the *apiaccess* plan.
    5.  Click *Next* until you reach the *Confirm* section.
    6.  In the section *Confirm*, enter a unique *Instance Name* and choose *Finish*.

-   You have created a service key for the service instance above.
    1.  Choose the service instance that you created above.
    2.  In the left-hand pane, navigate to *Service Keys* \> *Create Service Key*.
    3.  In the *Create Service Key* dialog that opens, provide a name.
    4.  Click *Save*.

        The client credentials like url, clientId, and clientSecret details appear for the given service key.


-   You have created a destination of type `OAuth2Credentials` to the XSUAA APIs by using the credentials you derived from creating the service key. This is required to access the XSUAA APIs for authorization and trust mangement services.
    1.  From your *Subaccount*, navigate to *Connectivity* \> *Destinations* \> *New Destination*.
    2.  Choose the service instance that you created above.
    3.  In the *Destination Configuration* window, provide the details.

        > ### Note:  
        > You must enter the details exactly as mentioned below:

        ```
        Name: apimgmt-platform-access
        Type: HTTP
        Description: 
        URL: https://yourxsuua.authentication.sap.hana.ondemand.com (Provide the value of the url field from the service key you created above.)
        Proxy Type: Internet
        Authentication: Oauth2ClientCredentials
        Client ID: apiacess-client_id (Provide the value of the "clientid" field from the service key you created above.)
        Client Secret: xxxxxxxxxxxxxxxxxxxxxxxxxx (Provide the value of the "clientsecret" field from the service key you created above.)
        Token Service URL: https://yourxsuua.authentication.sap.hana.ondemand.com (Provide the value of the url field from the service key you created above.)
        Token Service User:
        Token Service Password:
        
        ```

        -   For URL, provide the value of the `url` field from the service key you created above.
        -   For Client ID, provide the value of the `clientid` field from the service key you created above.
        -   For Client Secret, provide the value of the `clientsecret` field from the service key you created above.
        -   For the Token Service URL, provide the value of the `url` field from the service key you created above.

    4.  Click *Save*.




<a name="loiodabee6e347f645a6805ec5b29f5d578c__section_s3d_qgc_plb"/>

## Creating a Service Instance in the API Management, API business hub enterprise 

Create a service instance using *devportal-apiaccess* plan.

1.  In your web browser, open the *SAP BTP Cockpit* - [https://account.hana.ondemand.com/cockpit](https://account.hana.ondemand.com/cockpit).
2.  From your *Subaccount*, navigate to *Spaces* in your Cloud Foundry environment and choose *Services* \> *Service Marketplace.*
3.  Choose **API Management, API business hub enterprise**, *Instances* \> *New Instance*.
4.  In the *Create Instance* dialog that opens, choose *devportal-apiaccess*.
5.  Click *Next*.
6.  In the section *Specify parameters*, provide the details as mentioned below, based on the role you require.

    The roles that support API access in the API business hub enterprise are `AuthGroup.API.Admin`, `AuthGroup.Content.Admin`, and `AuthGroup.API.ApplicationDeveloper`.

    Create a service instance with the `AuthGroup.API.Admin` role to access the API business hub enterprise APIs \(applications and attributes, API packages, API proxies and products, app developer and metering\), and perform operations like create, update, and delete on various API business hub enterprise entities as specified in the [Business Accelerator Hub](https://api.sap.com/package/APIMgmt?section=Artifacts).

    ```
    
    {
        "role": "AuthGroup.API.Admin"
    }
    
    ```

    Create a service instance with the `AuthGroup.Content.Admin` role to manage the domain categories in API business hub enterprise and add the related products into relevant categories.

    ```
    {
        "role": "AuthGroup.Content.Admin"
    }
    
    ```

    Create a service instance with the `AuthGroup.API.ApplicationDeveloper` role to access the API business hub enterprise APIs \(applications, API packages, and API proxies and products\), and perform operations like create, update, and delete on variousAPI business hub enterprise entities as specified in the [Business Accelerator Hub](https://api.sap.com/package/APIMgmt?section=Artifacts).

    ```
    
    {
        "role": "AuthGroup.API.ApplicationDeveloper"
        "developerId": "developerId"
    }
    ```

    > ### Note:  
    > **What is `developerId`**:
    > 
    > Providing an invalid or an empty `developerId` throws an error in the service instance creation process.
    > 
    > To successfully create an application via the API business hub enterprise, you must provide a valid `developerId`. This means that you must have already registered as an application developer to the API Management, API business hub enterprise service or you must have been onboarded by your adminstrator.
    > 
    > -   If you have registered to the API Management, API business hub enterprise application, provide your `developerId`.
    > 
    >     See the section below to know how to obtain your `developerId`.
    > 
    > -   If you have not registered to the API Management, API business hub enterprise application, follow the steps in [Register on API business hub enterprise](register-on-api-business-hub-enterprise-c85fafe.md) and try again.
    > -   If you are not registered to the API Management, API business hub enterprise application, and require your admin to onboard you, contact your admin. See [Onboard an Application Developer](onboard-an-application-developer-786d107.md).
    > 
    > **How to obtain the `developerId`**:
    > 
    > -   If you are a registered developer in the API business hub enterprise, access the following URL in your browser to obtain your `developerId`:
    > 
    >     ```
    >     https://devportal-url/api/1.0/user
    >     #Response
    >     [{"Name":"",
    >     "FirstName":"",
    >     "LastName":"",
    >     "LoggedOut":false,
    >     "Email":""}]
    >     ```
    > 
    >     The `Name` field in the response is your `developerId`.
    > 
    > -   If you are an admin and are obtaining the `developerId` for a developer you have already onboarded, pick the `userId` that you provided during the developer onboarding.
    > 
    >     To view a list of the registered developers, access the following URL in your browser. The `userId` field in the response is the `developerId`.
    > 
    >     ```
    >     https://devportal-url/api/1.0/registrations?type=registered
    >     #Response
    >     autoReLogin: false
    >     country: ""
    >     emailId: ""
    >     firstName: ""
    >     lastName: ""
    >     rolesAccess: [{status: "registered", role: "API_ApplicationDeveloper"}]
    >     0: {status: "registered", role: "API_ApplicationDeveloper"}
    >     userId: ""
    >     ```
    > 
    > 
    > **Limitation**: Self-service onboarding request is not supported for a developer. So, the POST operation under the **API business hub enterprise- Registering Users** tile in the [API Business Hub](https://api.sap.com/api/DevPortal_RegisteringUsers/resource) cannot be made by the application developer service key. As an alternative, you can invoke this API using the admin service key.

7.  In the section *Confirm*, enter a unique *Instance Name*, and choose *Finish*.

The service instance is successfully created and listed in the *Instances* window.



<a name="loiodabee6e347f645a6805ec5b29f5d578c__section_it1_4nn_ylb"/>

## Create a Service Key

Generate a service key for the service instance that you created above:

1.  From the *Instances* window, choose the service instance that you created above.
2.  In the left-hand pane, navigate to *Service Keys* \> *Create Service Key*.
3.  In the *Create Service Key* dialog that opens, provide a name.
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
    
    `"binding-secret"`\(without payload\)
    
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
    	"url": "https://developer-portal-application-url",
    	"tokenUrl": "https://token-enpoint-url/oauth/token",
    	"clientId": "your-admin-client-id",	
    	"clientSecret": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx="
    }
    ```

    For developer role:

    ```
    {
    	"url": "https://developer-portal-application-url",
    	"tokenUrl": "https://token-enpoint-url/oauth/token",
    	"developerId": "developerID-associated-with-the-current-instance",
    	"clientId": "your-dev-client-id",     	
    	"clientSecret": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx="
    }
    ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `"binding-secret"`\(with payload\)
    
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
    	"url": "https://developer-portal-application-url",
    	"tokenUrl": "https://token-enpoint-url/oauth/token",
    	"clientId": "your-admin-client-id",	
    	"clientSecret": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx="
    }
    ```

    For developer role:

    ```
    {
    	"url": "https://developer-portal-application-url",
    	"tokenUrl": "https://token-enpoint-url/oauth/token",
    	"developerId": "developerID-associated-with-the-current-instance",
    	"clientId": "your-dev-client-id",     	
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

    For developer role:

    ```
    {
        "url": "https://xxxxxxxxxxxx.cfapps.sap.hana.ondemand.com",
        "certificate": "xxxxxxxxxxxxxxxxx",
        "certurl": "https://xxxxxx.authentication.cert.sap.hana.ondemand.com",
        "clientId": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "developerId": "xxxxxxxxxxxxx",
        "privateKey": "xxxxxxxxxxxxxxxxxxxxxxxxxx",
        "tokenUrl": "https://xxxxxx.authentication.sap.hana.ondemand.com/oauth/token"
    }
    ```


    
    </td>
    </tr>
    </table>
    
5.  Click *Save*.

The credentials like url, tokenUrl, developerId \(for developer role\), clientId, and clientSecret details are displayed for the given service key.

-   The application url is used to make API calls.
-   The clientId and clientSecret are necessary credentials required to fetch the Bearer Token.
-   The tokenUrl is used to fetch the Bearer Token.

Make a note of these credentials as you will need them in the next steps to obtain a bearer token, in order to access the API business hub enterprise APIs.

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



<a name="loiodabee6e347f645a6805ec5b29f5d578c__section_ccb_vxj_fmb"/>

## Updating a Service Instance in the API Management, API business hub enterprise

You can update an already provisioned service instance of an API access plan by performing the following steps:

**Prerequisite:**

You must have the Cloud Foundry CLI installed.

1.  Log in to the Cloud Foundry CLI by running the `cf login` command.
2.  Select *Org*.
3.  Run the following command to update your service instance. `cf update-service <service-instance-name> -c <empty-json-file>.json`.

    > ### Sample Code:  
    > ```
    > Sample json: {}
    > ```




<a name="loiodabee6e347f645a6805ec5b29f5d578c__section_khs_pht_ylb"/>

## Next Steps

`Obtaining a Bearer Token`

In the REST client:

1.  Paste the copied *tokenUrl*. Append `?grant_type=client_credentials` to the *tokenUrl*.
2.  Choose `Basic Auth` as the `Authorization` type.
3.  Similarly, paste the *clientId* and *clientSecret* in the place of `Username` and `Password`.
4.  Make a POST Call.
5.  Obtain the Bearer Token from the output and copy it in a notepad.
    -   Now, to trigger an API, in the same REST client, append the API endpoint \(obtained from the API business hub enterprise APIs that are located in the SAP API Management package of SAP Business Hub Acclerator\) to the *url*.

    -   Choose `Bearer Token` as the `Authorization` type and paste the copied Bearer Token in the specified space.
    -   Include payloads, if needed.
    -   Make an API call.


