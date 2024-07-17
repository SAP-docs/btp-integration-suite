<!-- loio641c56b41dfb4ca48328e64d284a97be -->

# Setting Up OAuth for Cloud Integration in Cloud Foundry

For Cloud Integration type Provider there are two types of authentications: Basic and OAuth2ClientCredentials.



## Context

Use Basic authentication for sending requests to server. Basic authentication requires you to enter a username and password.

Use OAuth2ClientCredentials for connecting requests to the server. This OAuth2ClientCredentials authentication requires you to enter *clientId*, *clientSecret*, and *tokenUrl*.

> ### Note:  
> The values you provide for the above, are the ones associated with your Cloud Integration tenant.
> 
> **Generate *clientId*, *clientSecret*, and *tokenUrl* Associated with Your Cloud Integration Tenant.**



## Procedure

1.  In your web browser, open the *SAP BTP Cockpit* - [https://cockpit.btp.cloud.sap](https://cockpit.btp.cloud.sap).

2.  From your *Subaccount*, navigate to *Spaces* in your Cloud Foundry environment and choose *Services* \> *Service Marketplace.*

3.  Choose *Process Integration Runtime* and choose *Create*.

4.  In the *Create Instance* dialog that opens, choose the *api* plan.

5.  In the section *Specify parameters*, paste the following JSON codes, to assign a specific role.

    ```
    "roles": [
                "AuthGroup_IntegrationDeveloper",
                "AuthGroup_Administrator"]
    
    ```

6.  Choose *Next* until you reach the *Confirm* section.

7.  In the *Confirm* section, enter a unique *Instance Name* and choose *Finish*.




<a name="loio641c56b41dfb4ca48328e64d284a97be__result_zpd_zy3_zsb"/>

## Results

The creation of service instance is successful.



<a name="loio641c56b41dfb4ca48328e64d284a97be__postreq_am5_zy3_zsb"/>

## Next Steps

Now, for the created service instance, generate a service key from the steps given next:

<a name="task_mc5_3n3_zsb"/>

<!-- task\_mc5\_3n3\_zsb -->

## Creating a Service Key



<a name="task_mc5_3n3_zsb__steps_nqw_m53_zsb"/>

## Procedure

1.  Choose the created service instance link from the visible list.

2.  In the left-hand pane, navigate to *Service Keys* \> *Create Service Key*.

3.  In the *Create Service Key* dialog that opens, provide a *Name* and *Description* \(optional\).

4.  Choose *Save*. The client credentials like *url*, *clientId*, *clientSecret*, and *tokenUrl* details appear for the given instance name.

    The *clientId* and *clientSecret* are necessary credentials required to fetch the Bearer Token.

    The *tokenUrl* is used to fetch the Bearer Token.

    ```
    Example:
            "clientid": "sb-37b5d80e-27f9-4b73-bf58-c29f2a156df8!b16289|it!b12456",
    
            "clientsecret": "311ccbf6-86ef-48bb-910c-a7eee79ea29f$h6xDUyIUoe45qiDGGBhzK9zvDczFeePUHDNLBshnMCk=",
            "url": "https://isuitetestcpi.it-adev001.cfapps.sap.hana.ondemand.com",
            "tokenurl": "https://isuitetestcpi.authentication.sap.hana.ondemand.com/oauth/token"
    
    ```

    *Copy* the client credentials in a notepad and use it while creating the API Provider.


<a name="task_emw_lz3_zsb"/>

<!-- task\_emw\_lz3\_zsb -->

## To Discover and Create an API Proxy for Cloud Integration



<a name="task_emw_lz3_zsb__context_ezz_qz3_zsb"/>

## Context

The service keys provide you with *clientId* and *clientSecret*. The *clientId* can be used as username and secret can be used as password if you would like to connect to your integration flows of Cloud Integration via Basic Authentication. Alternatively, you can leverage the *clientId*, *clientSecret*, and *tokenUrl* from the service keys file to get the OAuth access token and then connect to your integration flow of Cloud Integration via OAuth access token approach. For more information, see [Creating an API Proxy using SAP Cloud Integration API Provider](creating-an-api-proxy-using-sap-cloud-integration-api-provider-aefbd74.md).

