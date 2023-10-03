<!-- loioe0646630540d440aa1177b389f512afa -->

# API Management, API portal as a Service

The *API Management, API* portal as a service on Cloud Foundry provides different capabilities through Route Service plan, On-Premise Connectivity plan, and API Access plan.

The *API Management, API portal* supports the following plans:

-   **apim-as-route-service**: The API Management as Route Service plan helps you in managing Cloud Foundry applications by including policies such as rate limit, quota. The service instance you create through this plan allows you to bind to the route service and creates an API Proxy. This API Proxy serves in establishing a secure connection with your Cloud Foundry application and all the calls made to the Cloud Foundry application are routed via*API Management, API portal*. For more details, see [Route Service plan](route-service-plan-e609a3e.md).

-   **on-premise-connectivity**: The On- Premise Connectivity plan helps in achieving principal propagation while connecting to an on-premise backend system. To accomplish prinipal propagation you require a service key and this plan allows you to obtain a service key by creating a service instance. For more details on On-remise connectivity plan, see [On-Premise Connectivity Plan](on-premise-connectivity-plan-2fc7a5b.md) .
-   **apiportal-apiaccess**: The API Access plan allows you to generate a service key by creating a service instance. The service key, consisting of *url* \(application url\), *clientId*, *clientSecret*, and *tokenUrl* is used to generate a Bearer Token with the help of a REST Console. This Bearer Token, along with the application url and API endpoint are used to trigger the API. Therefore, Bearer Token acts like a key to access the APIs. For more details, see [API Access Plan for API Portal](api-access-plan-for-api-portal-24a2c37.md).

**Related Information**  


[API Management, API business hub enterprise as a Service](api-management-api-business-hub-enterprise-as-a-service-d59d8f9.md "The API Management, API business hub enterprise as a service on Cloud Foundry provides the API access plan.")

[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-585d639.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Requesting an Additional Virtual Host in Cloud Foundry Environment](requesting-an-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.")

[Requesting a Custom Domain for a Virtual Host](requesting-a-custom-domain-for-a-virtual-host-6b9e5a3.md "Virtual host is an entity where the API proxy gets deployed, and API proxies can be accessed using the URL defined in the virtual host.")

[Request for Two-Way SSL Certificate](request-for-two-way-ssl-certificate-9faf7ce.md "Request a two-way SSL certificate for the default domain of the virtual host of your API Management service.")

[Assign User Roles in API Management](assign-user-roles-in-api-management-911ca5a.md "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.")

[Create an API Provider](50-Development/create-an-api-provider-6b263e2.md "Define the details of the host you want an application to reach by creating an API provider.")

