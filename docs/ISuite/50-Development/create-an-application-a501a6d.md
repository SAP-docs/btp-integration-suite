<!-- loioa501a6d6c5ee466d99de270b07771126 -->

# Create an Application

Create an Application to consume the required APIs.

An application is a discrete representation of the actual developer’s application. It provides the developer with an API key to pass-in with every request to the API.

In API Management, similar APIs are bundled together to form products, which are published in the catalog. An application developer enters necessary details to register to Developer Hub. After successful registration, the application developer can explore the required products and APIs to create an application. Once the application has been created successfully, the system generates an appIication key and application secret. If APIs in the application you created are protected via **Verify API Key** policy, then to access those APIs, you must pass the generated application key. Whereas, if APIs are protected via **OAuth** policy, then to access those APIs, you must pass an OAuth token that can be obtained by using the combination of generated appIication key and application secret.

A user must be onboarded to Developer Hub only via Self-registration or *Add User* flow. For more information on registering in Developer Hub, see [Registering on Developer Hub](registering-on-developer-hub-c85fafe.md). In the *Add User* flow, the Developer Hub admin adds a user who wants to be onboarded to Developer Hub. However, the user who is requesting to be onboarded must ensure that the user details provided to the admin matches the user details obtained from the response of <developer portal url\>/api/1.0/users.

