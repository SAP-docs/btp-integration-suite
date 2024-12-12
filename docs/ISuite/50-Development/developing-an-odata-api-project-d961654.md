<!-- loiod961654cd36b46ad83b668e4434c9f04 -->

# Developing an OData API Project

You can develop OData APIs that expose existing data sources, such as SOAP, as OData endpoints. These OData APIs can be consumed by SAP Fiori apps, SAP BTP Mobile Services, or any other custom app, to implement user-centric scenarios.

![The grafic shows how to realise a user-centric scenario. OData APIs that expose existing data sources, such as SOAP, REST, OData or ODC, can be consumed by SAP Fiori apps, SAP BTP Mobile Services, or any other custom app.](images/OData_API_Overview_38d1448.png)



## Differences Between OData API and Integration Projects

When deciding whether to use OData APIs or integration projects to implement your business scenario, keep the following differences in mind:

****


<table>
<tr>
<th valign="top">

OData APIs

</th>
<th valign="top">

Integration Projects

</th>
</tr>
<tr>
<td valign="top">

An OData API can expose multiple entities and multiple associated operations at the same time.

</td>
<td valign="top">

An integration project can expose only one entity and one associated operation at a time.

</td>
</tr>
<tr>
<td valign="top">

You can configure any application to consume an OData API. As a result, any number of users with access to these applications can consume the OData API.

</td>
<td valign="top">

In an integration project, the credentials of a limited set of users are used to authenticate the integration scenario between two systems.

</td>
</tr>
</table>



## Service Development Process

As a service developer, you can create and deploy an OData API without going through the time-consuming process of writing code. You start off the process by creating an OData API artifact in an integration package. For more information, see [Creating an OData API](creating-an-odata-api-6670029.md). Cloud Integration enables you to further develop the OData API with the following steps:

1.  Import an OData model using simple modeling steps. If you prefer writing code, Cloud Integration also lets you handcraft an OData model or edit an existing one using an editor.
2.  Connect the OData objects to a data source through integration flows.
3.  Tweak the integration flows to enhance business logic.
4.  Deploy and monitor the OData API.

![](images/Image_Map_Service_Development_Process_cecdf75.png)

> ### Note:  
> -   You can deploy OData API artifact for *SAP Cloud Integration* and *SAP Cloud Integration OEM* runtime profiles only.
> -   The OData API artifacts cannot be Externalized.



## Authorization

*User Role* is the default authorization used in OData APIs. Assign the ESBMessaging.send role to users in order for them to access the OData APIs.

**Related Information**  


[Supported OData Features](supported-odata-features-130d00e.md "")

