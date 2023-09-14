<!-- loio7ac1d3ab712a49f793e0a2af168ac22d -->

# Authorize the HTTP Client to Call the Integration Flow Endpoint, Cloud Foundry Environment

You perform these steps to authorize the sender \(HTTP client\) to call the SAP Cloud Integration integration flow endpoint.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Cloud Foundry environment.

> ### Note:  
> You need to perform these steps only in case you use SAP Cloud Integration in the Cloud Foundry environment.

These steps imply that you create a service instance on SAP BTP and generte a service key for it. The credentials which you get as a result can be used by the HTTP client to call the integration flow endpoint.



<a name="loio7ac1d3ab712a49f793e0a2af168ac22d__section_jlh_c1l_whb"/>

## Create Service Instance

A service instance defines how an application on SAP BTP can be called by a sender \(in our scenario, the HTTP client\). In technical terms, it is an OAuth client.

Go to SAP BTP cockpit and perform the steps described at [Creating Service Instance and Service Key for Inbound Authentication](../ConnectionSetup/creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md).

When defining the service instance, enter the following JSON content:

> ### Sample Code:  
> ```
> {
>  "roles":[
>  "ESBMessaging.send"
>  ]
> }
> 
> ```



<a name="loio7ac1d3ab712a49f793e0a2af168ac22d__section_lsf_d1l_whb"/>

## Create Service Key

With this step, you generate credentials to communicate with a service instance.

Perform the steps described at [Creating Service Instance and Service Key for Inbound Authentication](../ConnectionSetup/creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md).

The sender application \(HTTP client\) uses these credentials \(`clientid` and `clientsecret`\) to access the SAP Cloud Integration integration flow endpoint.

You need to copy the values of `clientid` and `clientsecret` to your clipboard or to a text editor for later reference.

These values specify the credentials of the user associated with the sending application.

