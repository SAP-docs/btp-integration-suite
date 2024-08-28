<!-- loio7bd9d9f8f8324403b1aff8b0fffed25c -->

# Monitor the Health of Custom Domain Virtual Host Certificates Using SAP Cloud ALM

You can use SAP Cloud Application Lifecycle Management \(ALM\) application to proactively detect issues and monitor the health of custom domain virtual host certificates in API Management.

The SAP Cloud Application Lifecycle Management \(ALM\) platform allows you to monitor environment backlogs and status of automation processes regarding execution status, application status, start delay, and runtime of various SAP Cloud solutions and services. To integrate the Cloud Application Lifecycle Management \(ALM\) application with the Health service endpoint, refer [SAP Cloud ALM Onboarding](https://www.youtube.com/playlist?list=PLFrwZZeBUtfjx9Ta9pZw8ccAuJe3n2FcA).

The API*https://<host\>:<port\>/api/1.0/Health*, which has been provisioned in API Management, can be integrated with Cloud Application Lifecycle Management \(ALM\) to provide information about the custom domain virtual host certificates expiry details. You can use this API to read information about the certificates provided by the customers for their custom domain virtual hosts.

> ### Note:  
> You have to enable API access with *APIPortal. Administrator* role to use the *https://<host\>:<port\>/api/1.0/Health* API. To access this API from the Cloud Application Lifecycle Management \(ALM\) application, use *OAuth* authentication.

**Related Information**  


[Limits in API Management](limits-in-api-management-f70f425.md "This topic describes the product configuration and the naming conventions for API Management.")

[API Management FAQs](api-management-faqs-2d16070.md "Frequently asked questions for SAP API Management.")

