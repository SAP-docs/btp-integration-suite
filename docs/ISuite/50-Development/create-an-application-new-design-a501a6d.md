<!-- loioa501a6d6c5ee466d99de270b07771126 -->

# Create an Application \[New Design\]

Create an Application to consume the required APIs.

> ### Note:  
> This document describes the new design of the API business hub enterprise. To view the documentation for the classic design, see [Create an Application \[Classic Design\]](create-an-application-classic-design-7b4e71b.md).

An application is a discrete representation of the actual developer’s application. It provides the developer with an API key to pass-in with every request to the API.

In API Management, similar APIs are bundled together to form products, which are published in the catalog. An application developer enters necessary details to register to the API business hub enterprise. After successful registration, the application developer can explore the required products and APIs to create an application. Once the application has been created successfully, the system generates an appIication key and application secret. If APIs in the application you created are protected via **Verify API Key** policy, then to access those APIs, you must pass the generated application key. Whereas, if APIs are protected via **OAuth** policy, then to access those APIs, you must pass an OAuth token that can be obtained by using the combination of generated appIication key and application secret.

A user must be onboarded to API business hub enterprise only via Self-registration or *Add User* flow. For more information on registering in API business hub enterprise, see [Register on API business hub enterprise](register-on-api-business-hub-enterprise-c85fafe.md). In the *Add User* flow, the API business hub enterprise admin adds a user who wants to be onboarded to API business hub enterprise. However, the user who is requesting to be onboarded must ensure that the user details provided to the admin matches the user details obtained from the response of <developer portal url\>/api/1.0/users.

