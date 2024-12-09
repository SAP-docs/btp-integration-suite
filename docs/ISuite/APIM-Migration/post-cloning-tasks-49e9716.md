<!-- loio49e9716c499d44059907f18c0659cd69 -->

# Post Cloning Tasks

Post the completion of the cloning process, you must perform some actions, checks, and validations.



The following sections explain the tasks that you must perform after the cloning of your API Management artifacts from the Cloud Foundry to the Cloud Foundry environment is complete.



<a name="loio49e9716c499d44059907f18c0659cd69__section_w3x_lkd_2mb"/>

## User Actions

You can view the status of the cloned artifacts in the `apim-tct-output.xlsx` excel file or in the `apim-tct.log` file, generated in the same folder where the .jar file is present.

Perform the tasks mentioned in the `User Actions` worksheet within the `apim-tct-output.xlsx` excel file.

**The following table describes the actions required for each cloned entity:**


<table>
<tr>
<th valign="top">

Cloned Entity

</th>
<th valign="top">

User Action

</th>
</tr>
<tr>
<td valign="top">

Certificates

</td>
<td valign="top">

All the certificates that are cloned to the target system are dummy certificates.

Perform the following steps:

1.  From your source system, note down the certificate names and the corresponding certificate store name.
2.  From your target system, delete the dummy certificates that were cloned:
    1.  In your target API Management, API portal, navigate to *Configure* \> *Certificates*.
    2.  Select the cloned dummy certificate that you want to delete.
    3.  Click the delete icon under the *Actions* column.

3.  In your target API Management, API portal, upload the relevant certificates, providing the same names and under same certificate store as present in your source system.
    1.  In your target API Management, API portal, navigate to *Configure* \> *Certificates*.
    2.  Click *Create*.
    3.  In the *Create Certificate* window, provide the details and upload the certificate.




</td>
</tr>
<tr>
<td valign="top">

Key Value Maps

</td>
<td valign="top">

Fill in the values for the keys of the encrypted Key Value Maps.

1.  In your target API Management, API portal, navigate to *Configure* \> *Key Value Maps*.
2.  Click on the encrypted key value map.
3.  In the *Edit Key Value Map* window, provide the details and click *Save*.



</td>
</tr>
<tr>
<td valign="top">

API Provider Credentials

</td>
<td valign="top">

Provide the Basic Auth password \(if present in your source system\) for an API Provider.

1.  In your target API Management, API portal, navigate to *Configure* \> *API Providers*.
2.  Click on the desired API provider.
3.  In the *View API Provider* window, click *Catalog Service Settings* \> *Edit*.
4.  Provide the basic auth password for the API provider and click *Save*.

Update open connector credentials:

1.  In your target API Management, API portal, navigate to *Configure* \> *API Providers*.
2.  Click on the desired API provider.
3.  In the *View API Provider* window, click *Catalog Service Settings* \> *Edit*.
4.  Provide the Org ID and User Secret from your corresponding Open Connector subscription.



</td>
</tr>
<tr>
<td valign="top">

Proxy Scoped Key Value Map

</td>
<td valign="top">

Provide instance token value in the proxy scoped Key Value Map.

1.  In your target API Management, API portal, navigate to *Develop* \> *APIs*.
2.  Click on the desired API proxy.
3.  In the *View API* page, scroll down to *Key Value Map Associated* and choose the Key Value Map.
4.  On the *Edit Key Value Map* page, update the *Value* with the instance token value for the corresponding open connector instance.

5.  Provide the Org ID and User Secret from your corresponding Open Connector subscription.



</td>
</tr>
</table>



<a name="loio49e9716c499d44059907f18c0659cd69__section_gjt_245_hmb"/>

## Actions Required on Configurations

Depending on the configurations you have on your source system, you must configure the following in your target system:

-   Custom IDP Setup \(if any\)
-   Default role assignment to users
-   Custom Role creation and its assignments
-   Cloud Connector setup
-   Principal Propagation setup at the subaccount level
-   Changes to Principal Propagation policy for on-premise connectivity
-   Migration of route service bindings. For more information, see [Migrating Route Service Binding](post-cloning-tasks-49e9716.md#loio49e9716c499d44059907f18c0659cd69__routebinding)
-   Any integrations with other systems \(like SAP Web IDE\)
-   Any other configurations that you created for API Management at the subaccount level of your source system

To know more about the entities that are cloned and the entities that aren’t cloned, see [Cloned and Uncloned Entities](cloned-and-uncloned-entities-b2b393d.md).



<a name="loio49e9716c499d44059907f18c0659cd69__routebinding"/>

## Migrating Route Service Binding

If you've used the [Managing Cloud Foundry Microservices through API Management](../managing-cloud-foundry-microservices-through-api-management-e609a3e.md) to manage your Cloud Foundry applications, you can now migrate the existing route service binding, from the API Management instance on Cloud Foundry to the new API Management instance on Cloud Foundry.



### Prerequisites

-   A route service binding exists between your application on Cloud Foundry and the API Management service instance in the Cloud Foundry environment.
-   You have enabled API Management on your Cloud Foundry sub account
-   You have the space developer role assigned to you.

Depending upon the location of your application, and your API Management service instance, the steps to migrate the route service binding vary.



### Cloud Foundry Application and API Management capability on the same subaccount

If your cloud foundry application and the API Management capability are on the same sub account, then use the following steps to migrate the route service binding:

1.  Create an API Management, API portal service instance using the service plan, apim-as-route-service. For more information, see [Creating an API Management, API portal Service Instance](../managing-cloud-foundry-microservices-through-api-management-e609a3e.md#loioe609a3efe6d64e1781cbf81ae5592071__CreatingAPIMInstance)
2.  Unbind your application from the API Management service instance on Cloud Foundry. For more information, see [Unbinding a Multi-Cloud Foundation Application from an API Management, API portal Service Instance](../unbinding-a-multi-cloud-foundation-application-from-an-api-management-api-portal-service-09fd33a.md) 
3.  Bind your application to the API Management service instance on Cloud Foundry. For more information, see [Binding a Cloud Foundry Application to an API Management, API portal Service Instance](../managing-cloud-foundry-microservices-through-api-management-e609a3e.md#loioe609a3efe6d64e1781cbf81ae5592071__Binding)



### Cloud Foundry Application and API Management capability on different sub accounts

If your Cloud Foundry application and the API Management capability are on different sub accounts, then use the following steps to migrate the route service binding:

1.  Create a User Provided Service in the sub account where your Cloud Foundry application is present, using the proxy URL from the sub account in which your API Management instance is present. In order to create this User Provided Service, open the command prompt and use the following command

    > ### Sample Code:  
    > ```
    > cf create-user-provided-service apim-route-service -r https://apiproxy.url.from.source.
    > OK
    > ```

    For more information, see [User Provided Service](https://docs.cloudfoundry.org/services/route-services.html#user-provided)

2.  Unbind your application from the API Management service instance on Cloud Foundry. For more information, see [Unbinding a Multi-Cloud Foundation Application from an API Management, API portal Service Instance](../unbinding-a-multi-cloud-foundation-application-from-an-api-management-api-portal-service-09fd33a.md) 
3.  Bind the User Provided Service created in the first step to the Cloud Foundry Application. For this binding, use the following command:

    > ### Sample Code:  
    > ```
    > cf bind-route-service cfapps.eu10.hana.ondemand.com --hostname <your-app-host>  apim-route-service
    > ```




<a name="loio49e9716c499d44059907f18c0659cd69__section_wxz_gnd_2mb"/>

## Validate Your Target API Management System

Validate that all your API Management artifacts have been cloned to the target system and that all your artifacts and route bindings are in working condition.



<a name="loio49e9716c499d44059907f18c0659cd69__section_ems_jnd_2mb"/>

## Switch Over from Source to Target System

You can choose to switch over completely from your source to target system after you've successfully cloned all the entities, performed the post-cloning tasks, and validated that your target system is working correctly.

This section explains the various scenarios for a switch-over:



### Switching Over Runtime Proxy URLs


<table>
<tr>
<th valign="top" colspan="2">

Scenario

</th>
<th valign="top">

Actions Required for Switchover

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

If you want to retain the same proxy URL as that of your source system

</td>
<td valign="top">

If the proxy URL of your source system is on a domain managed by SAP

</td>
<td valign="top">

There’s no option to retain the old proxy URL.

You must adopt the new proxy URL that is generated for your target system.

</td>
</tr>
<tr>
<td valign="top">

If the proxy URL of your source system is on a custom domain

</td>
<td valign="top">

1.  Update the virtual host of the target system to that of the source system.

    See [Configuring Additional Virtual Host in Cloud Foundry Environment](../configuring-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md).

2.  Perform a DNS change from the old cluster to a new cluster.



</td>
</tr>
<tr>
<td valign="top">

If you have multiple virtual hosts configured on your source system subscription, and want to retain those on your target system

</td>
<td valign="top">

 

</td>
<td valign="top">

1.  Create multiple virtual hosts on your target system.

    See [Configuring Additional Virtual Host in Cloud Foundry Environment](../configuring-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md).

2.  Bind each API proxy to the desired virtual host on your target system.



</td>
</tr>
</table>

> ### Note:  
> If your source and target belongs to the same data center and your source has a custom domain virtual host, and if you are planning to carry forward the same custom domain virtual host to target, please ensure that the following aspects are considered:
> 
> 1.  Since custom domain virtual host URL and port should be unique in a data center accross tenants. It is not possible to have the same virual host URL in both source and target at the same time. Therefore, delete the custom domain virtual host from source and then create the same custom domain virtual host in the target. See, [Configuring Additional Virtual Host in Cloud Foundry Environment](../configuring-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md).
> 
> 2.  When virtual host gets deleted in the source tenant, there will be downtime for all the APIs in the source account. The downtime will continue untill the virtual host configuration gets completed. This configuration activity will require manual intervention by the API Mangement Operations team and also your DNS service provider for DNS cutover. We recommend that you plan this activity during your planned maintenance window.



### Switching Over Design time URLs of API portal and Developer Hub portals

-   Domains managed by SAP can't be switched over.
-   To switch over a custom domain, create an incident on the component OPU-API-OD-OPS through the [SAP Support Portal](https://support.sap.com/en/index.html).

