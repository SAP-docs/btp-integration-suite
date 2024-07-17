<!-- loio116d82c83b6a4665a6f30f21a0e6e0d8 -->

# Post Cloning Tasks

Post the completion of the cloning process, you must perform some actions, checks, and validations.



The following sections outline the tasks that need to be completed after the cloning of your API Management content from Neo to the multi-cloud foundation.



<a name="loio116d82c83b6a4665a6f30f21a0e6e0d8__section_w3x_lkd_2mb"/>

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
<tr>
<td valign="top">

Custom Domain based Virtual Host

> ### Note:  
> This is only relevant for starter plan migration.



</td>
<td valign="top">

If you have custom domain based virtual host in the source system, then perform the following checks to verify whether the custom domain based virtual hosts are cloned on the target systems:

If the URL of virtual hosts looks different in target, which means if the sub domain of the URL is different than the source, revert in the same migration ticket asking the Operations team to set the correct URL for this virtual host.

Please ensure that you provide the following virtual host details \(from the source\) to the Operations team:

-   Custom domain virtual host URL

-   Virtual host ID


The Operations team will use these details to update the virtual host domain in the target system so that it matches with the source.

> ### Note:  
> This step has to be completed before starting the Switch Over stage.
> 
> If you have multiple customain based vitual host, perform the same procedure for each vitual host.



</td>
</tr>
</table>



<a name="loio116d82c83b6a4665a6f30f21a0e6e0d8__section_gjt_245_hmb"/>

## Actions Required on Configurations

Depending on the configurations you have on your source system, you must configure the following in your target system:

-   Custom IDP Setup \(if any\)
-   Default role assignment to users
-   Custom Role creation and its assignments
-   Cloud Connector setup
-   Principal Propagation setup at the subaccount level
-   Changes to Principal Propagation policy for on-premise connectivity
-   Migration of route service bindings. For more information, see [Migrating Route Service Binding](post-cloning-tasks-116d82c.md#loio116d82c83b6a4665a6f30f21a0e6e0d8__routebinding)
-   Any integrations with other systems \(like SAP Web IDE\)
-   Any other configurations that you created for API Management at the subaccount level of your source system

To know more about the entities that are cloned and the entities that aren’t cloned, see [Cloned and Uncloned Entities](cloned-and-uncloned-entities-8973ca0.md).

> ### Note:  
> For the on-premise APIs, the URL of the target.basepath changes while migrating from Neo to multi-cloud foundation. If you’ve customized any of the policies, where the target.basepath is being used, then make sure that you update the content of the policy accordingly in the target multi-cloud foundation system. For example, after migration the target basepath URL in multi-cloud foundation might have an additional segment. You need to verify if this additional segment adversely affects the policy execution in targetmulti-cloud foundation system.



<a name="loio116d82c83b6a4665a6f30f21a0e6e0d8__routebinding"/>

## Migrating Route Service Binding

If you've used the [Managing Cloud Foundry Microservices through API Management](../managing-cloud-foundry-microservices-through-api-management-e609a3e.md) to manage your multi-cloud foundation applications, you can now migrate the existing route service binding, from the API Management instance on Neo to the new API Management instance on multi-cloud foundation.



### Prerequisites

-   A route service binding exists between your application on multi-cloud foundation and the API Management service instance in the Neo environment.
-   You have enabled API Management on your multi-cloud foundation subaccount.
-   You have the space developer role assigned to you.

Depending upon the location of your application, and your API Management service instance, the steps to migrate the route service binding vary.



### Multi-Cloud Foundation Application and API Management capability on the same subaccount

If your cloud foundry application and the API Management capability are on the same sub account, then use the following steps to migrate the route service binding:

1.  Create an API Management, API portal service instance using the service plan, apim-as-route-service. For more information, see [Creating an API Management, API portal Service Instance](../managing-cloud-foundry-microservices-through-api-management-e609a3e.md#loioe609a3efe6d64e1781cbf81ae5592071__CreatingAPIMInstance)
2.  Unbind your application from the API Management service instance on Neo. For more information, see [Unbinding a Multi-Cloud Foundation Application from an API Management, API portal Service Instance](../unbinding-a-multi-cloud-foundation-application-from-an-api-management-api-portal-service-09fd33a.md) 
3.  Bind your application to the API Management service instance on multi-cloud foundation. For more information, see [Binding a Muti-Cloud Foundation Application to an API Management, API portal Service Instance](../managing-cloud-foundry-microservices-through-api-management-e609a3e.md#loioe609a3efe6d64e1781cbf81ae5592071__Binding)



### Multi-Cloud Foundation Application and API Management capability on different sub accounts

If your multi-cloud foundation application and the API Management capability are on different sub accounts, then use the following steps to migrate the route service binding:

1.  Create a **User Provided Service** in the subaccount where your multi-cloud foundation application is present, using the proxy URL from the sub account in which your API Management instance is present. In order to create this **User Provided Service**, open the command prompt and use the following command

    > ### Sample Code:  
    > ```
    > cf create-user-provided-service apim-route-service -r https://apiproxy.url.from.source.
    > OK
    > ```

    For more information, see [User Provided Service](https://docs.cloudfoundry.org/services/route-services.html#user-provided)

2.  Unbind your application from the API Management service instance on Neo. For more information, see [Unbinding a Multi-Cloud Foundation Application from an API Management, API portal Service Instance](../unbinding-a-multi-cloud-foundation-application-from-an-api-management-api-portal-service-09fd33a.md) 
3.  Bind the User Provided Service created in the first step to the multi-cloud foundation application. For this binding, use the following command:

    > ### Sample Code:  
    > ```
    > cf bind-route-service cfapps.eu10.hana.ondemand.com --hostname <your-app-host>  apim-route-service
    > ```




<a name="loio116d82c83b6a4665a6f30f21a0e6e0d8__section_wxz_gnd_2mb"/>

## Validate Your Target API Management System

Validate that all your API Management artifacts have been cloned to the target system and that all your artifacts and route bindings are in working condition.



<a name="loio116d82c83b6a4665a6f30f21a0e6e0d8__section_ems_jnd_2mb"/>

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



### Switching Over Design time URLs of API portal and Developer portals

-   Domains managed by SAP can't be switched over.
-   To switch over a custom domain, create an incident on the component OPU-API-OD-OPS through the [SAP Support Portal](https://support.sap.com/en/index.html).



### Applicable Only During Starter Plan Migration

During the switchover, the Tenant Cloning Tool has a wait time of five minutes for the design-time to connect to the runtime on the target API portal. You can enable this feature by setting the "targetDestinationRefreshOnSwitchOver" parameter to true.

Once this parameter is set to true, the wait time is prompted on the console. Use this time to create a test API proxy on the target API portal and try to deploy the same on the virtual host, which is cloned from the source API portal. Once done, key in *Yes* on the Tenant Cloning Tool console.

> ### Note:  
> When you try to deploy the test proxy on the target, you might encounter an API proxy deployment error because at this point, the connection between the design time and the runtime is still being refreshed. We recommend that you keep trying until the proxy gets deployed successfully. Without a successful deployment, do not proceed with the next steps.

> ### Caution:  
> Do not attempt the Stage Switchover of the Tenant Cloning Tool unless it is a "Runtime Reuse Design time Only Migration" scenario.

