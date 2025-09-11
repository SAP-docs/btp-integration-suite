<!-- loio7bd9d9f8f8324403b1aff8b0fffed25c -->

# Monitor the Health of Certificates Using SAP Cloud ALM

You can use SAP Cloud Application Lifecycle Management \(ALM\) application to proactively detect issues and monitor the health of certificates in API Management.

The SAP Cloud Application Lifecycle Management \(ALM\) platform allows you to monitor environment backlogs and status of automation processes regarding execution status, application status, start delay, and runtime of various SAP Cloud solutions and services. To integrate the Cloud Application Lifecycle Management \(ALM\) application with the Health service endpoint, refer [SAP Cloud ALM Onboarding](https://www.youtube.com/playlist?list=PLFrwZZeBUtfjx9Ta9pZw8ccAuJe3n2FcA).



<a name="loio7bd9d9f8f8324403b1aff8b0fffed25c__section_k3v_c55_zfc"/>

## Monitor the Health of Custom Domain Virtual Host Certificates Using SAP Cloud ALM

You can monitor the health of custom domain virtual host certificates using SAP Cloud ALM by integrating it with the Health API provided by API Management \(https://<host\>:<port\>/api/1.0/Health\). This API returns expiry details for certificates uploaded by customers for their custom domain virtual hosts.

> ### Note:  
> To enable access, go to the SAP BTP Cockpit, create a service instance with the *apiportal-apiaccess* plan, and assign the *APIManagement.SelfService.Administrator* role. Once the instance is created, generate a service key, which includes the base URL—append */api/1.0/Health* to this URL to access the API. For secure access from SAP Cloud ALM, use *OAuth* authentication.



<a name="loio7bd9d9f8f8324403b1aff8b0fffed25c__section_u2l_255_zfc"/>

## Monitor the Health of Centralized Developer Hub Certificates Using SAP Cloud ALM

You can monitor the health of centralized Developer Hub certificates by integrating API Management \(APIM\) with SAP Cloud Application Lifecycle Management \(CALM\). By leveraging CALM’s health monitoring capabilities, you can configure automated email notifications when certificates approach their expiry, enabling proactive certificate management and helping prevent unexpected disruptions.

> ### Note:  
> To enable access, go to the SAP BTP Cockpit, create a service instance with the *devportal-apiaccess* plan, and assign the *AuthGroup.API.Admin* role. Once the instance is created, generate a service key, which includes the base URL—append */api/1.0/Health* to this URL to access the API. For secure access from SAP Cloud ALM, use *OAuth* authentication.

> ### Note:  
> You can monitor the health of centralized Developer Hub certificates either directly from the Centralized Developer Hub or from each individual API Portal connected to it. For more information, see [Centralized Developer Hub](APIM-Initial-Setup/centralized-developer-hub-38422de.md).

