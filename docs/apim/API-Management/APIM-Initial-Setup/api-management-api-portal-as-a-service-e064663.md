<!-- loioe0646630540d440aa1177b389f512afa -->

# API Management, API portal as a Service

The *API Management, API* portal as a service on Cloud Foundry provides different capabilities through Route Service plan, On-Premise Connectivity plan, and API Access plan.

The *API Management, API portal* supports the following plans:

-   **apim-as-route-service**: The API Management as Route Service plan helps you in managing Cloud Foundry applications by including policies such as rate limit, quota. The service instance you create through this plan allows you to bind to the route service and creates an API Proxy. This API Proxy serves in establishing a secure connection with your Cloud Foundry application and all the calls made to the Cloud Foundry application are routed via*API Management, API portal*. For more details, see [Route Service plan](route-service-plan-e609a3e.md).

-   **on-premise-connectivity**: The On- Premise Connectivity plan helps in achieving principal propagation while connecting to an on-premise backend system. To accomplish prinipal propagation you require a service key and this plan allows you to obtain a service key by creating a service instance. For more details on On-remise connectivity plan, see [On-Premise Connectivity Plan](on-premise-connectivity-plan-2fc7a5b.md) .
-   **apiportal-apiaccess**: The API Access plan allows you to generate a service key by creating a service instance. The service key, consisting of *url* \(application url\), *clientId*, *clientSecret*, and *tokenUrl* is used to generate a Bearer Token with the help of a REST Console. This Bearer Token, along with the application url and API endpoint are used to trigger the API. Therefore, Bearer Token acts like a key to access the APIs. For more details, see [API Access Plan for API Portal](api-access-plan-for-api-portal-24a2c37.md).

**Related Information**  


[Create an API Provider](../create-an-api-provider-6b263e2.md "Define the details of the host you want an application to reach by creating an API provider.")

