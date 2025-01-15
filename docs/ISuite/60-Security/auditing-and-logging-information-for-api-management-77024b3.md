<!-- loio77024b3e29e749a799b3d724f1535d34 -->

# Auditing and Logging Information for API Management

Here you can find a list of the security events that are logged by TECHNICAL COMPONENT.

**Security events written in audit logs**


<table>
<tr>
<th valign="top">

Event grouping

</th>
<th valign="top">

What events are logged

</th>
<th valign="top">

How to identify related log events

</th>
<th valign="top">

Additional information

</th>
</tr>
<tr>
<td valign="top">

API Proxy

</td>
<td valign="top">

Create API Proxy

</td>
<td valign="top">

-   action: create

-   objectType: PROXY


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"b370c7ed-a995-4ac8-b207-9ba59f470e55\",
> \"success\":true,\"object\":{\"type\":\"PROXY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.APIProxyProcessor\",
> \"objectId\":\"PROXY\",\"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Different Methods of Creating an API Proxy](../50-Development/different-methods-of-creating-an-api-proxy-4ac0431.md) 

</td>
</tr>
<tr>
<td valign="top">

API Proxy

</td>
<td valign="top">

Update API Proxy

</td>
<td valign="top">

-   action: update

-   objectType: PROXY


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"PROXY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.APIProxyProcessor\",
> \"objectId\":\"PROXY\",\"action\":\"update\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Edit an API Proxy](../50-Development/edit-an-api-proxy-a64b952.md) 

</td>
</tr>
<tr>
<td valign="top">

API Proxy

</td>
<td valign="top">

Delete API Proxy

</td>
<td valign="top">

-   action: delete

-   objectType: PROXY


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"PROXY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.APIProxyProcessor\",
> \"objectId\":\"PROXY\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

API Product

</td>
<td valign="top">

Create API Product

</td>
<td valign="top">

-   action: create

-   objectType: APIPRODUCT


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"APIPRODUCT\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.APIProductProcessor\",
> \"objectId\":\"APIPRODUCT\",\"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Create a Product](../50-Development/create-a-product-d769622.md) 

</td>
</tr>
<tr>
<td valign="top">

API Product

</td>
<td valign="top">

Update API Product

</td>
<td valign="top">

-   action: update

-   objectType: APIPRODUCT


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"APIPRODUCT\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.APIProductProcessor\",
> \"objectId\":\"APIPRODUCT\",\"action\":\"update\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

API Product

</td>
<td valign="top">

Delete API Product

</td>
<td valign="top">

-   action: delete

-   objectType: APIPRODUCT


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"APIPRODUCT\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.APIProductProcessor\",
> \"objectId\":\"APIPRODUCT\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Application

</td>
<td valign="top">

Create Application Name

</td>
<td valign="top">

-   action: create

-   objectType: APPLICATION


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"APPLICATION\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.ApplicationProcessor\",
> \"objectId\":\"APPLICATION\",\"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Create an Application](../50-Development/create-an-application-a501a6d.md) 

</td>
</tr>
<tr>
<td valign="top">

Application

</td>
<td valign="top">

Update Application Name

</td>
<td valign="top">

-   action: update

-   objectType: APPLICATION


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"APPLICATION\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.ApplicationProcessor\",
> \"objectId\":\"APPLICATION\",\"action\":\"update\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Application

</td>
<td valign="top">

Delete Application Name

</td>
<td valign="top">

-   action: delete

-   objectType: APPLICATION


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"APPLICATION\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.ApplicationProcessor\",
> \"objectId\":\"APPLICATION\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

API Provider

</td>
<td valign="top">

Create API Provider

</td>
<td valign="top">

-   action: create

-   objectType: APIPROVIDER


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"APIPROVIDER\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.APIProviderProcessor\",
> \"objectId\":\"APIPROVIDER\",\"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Create an API Provider](../50-Development/create-an-api-provider-6b263e2.md) 

</td>
</tr>
<tr>
<td valign="top">

API Provider

</td>
<td valign="top">

Update API Provider

</td>
<td valign="top">

-   action: update

-   objectType: APIPROVIDER


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"APIPROVIDER\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.APIProviderProcessor\",
> \"objectId\":\"APIPROVIDER\",\"action\":\"update\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

API Provider

</td>
<td valign="top">

Delete API Provider

</td>
<td valign="top">

-   action: delete

-   objectType: APIPROVIDER


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"b370c7ed-a995-4ac8-b207-9ba59f470e55\",
> \"success\":true,\"object\":{\"type\":\"APIPROVIDER\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.APIProviderProcessor\",
> \"objectId\":\"APIPROVIDER\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Developer

</td>
<td valign="top">

Create Developer

</td>
<td valign="top">

-   action: create

-   objectType: DEVELOPER


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"DEVELOPER\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.DeveloperProcessor\",
> \"objectId\":\"DEVELOPER\",\"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Onboarding an Application Developer](../50-Development/onboarding-an-application-developer-786d107.md) 

</td>
</tr>
<tr>
<td valign="top">

Developer

</td>
<td valign="top">

Update Developer

</td>
<td valign="top">

-   action: update

-   objectType: DEVELOPER


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"PROXY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.DeveloperProcessor\",
> \"objectId\":\"APPLICATION\",\"action\":\"update\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Developer

</td>
<td valign="top">

Delete Developer

</td>
<td valign="top">

-   action: delete

-   objectType: DEVELOPER


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"DEVELOPER\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.DeveloperProcessor\",
> \"objectId\":\"DEVELOPER\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Environment

</td>
<td valign="top">

Create Environment

</td>
<td valign="top">

-   action: create

-   objectType: ENVIRONMENT


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"ENVIRONMENT\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.model.listener.EnvironmentEntityListener\",
> \"objectId\":\"ENVIRONMENT\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Environment

</td>
<td valign="top">

Delete Environment

</td>
<td valign="top">

-   action: delete

-   objectType: ENVIRONMENT


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"ENVIRONMENT\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.model.listener.EnvironmentEntityListener\",
> \"objectId\":\"ENVIRONMENT\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

XProperty

</td>
<td valign="top">

Create XProperty

</td>
<td valign="top">

-   action: create

-   objectType: XPROPERTY


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"XPROPERTY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.model.listener.XPropertyEntityListener\",
> \"objectId\":\"XPROPERTY\",\"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

XProperty

</td>
<td valign="top">

Delete XProperty

</td>
<td valign="top">

-   action: delete

-   objectType: XPROPERTY


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"XPROPERTY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.model.listener.XPropertyEntityListener\",
> \"objectId\":\"XPROPERTY\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

XTenantProperty

</td>
<td valign="top">

Create XTenantProperty

</td>
<td valign="top">

-   action: create

-   objectType: XTENANTPROPERTY


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"XPROPERTY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.model.listener.XTenantPropertyEntityListener\",
> \"objectId\":\"XTENANTPROPERTY\",\"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

XTenantProperty

</td>
<td valign="top">

Delete XTenantProperty

</td>
<td valign="top">

-   action: delete

-   objectType: XTENANTPROPERTY


Audit Log:

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\"
> \"success\":true,\"object\":{\"type\":\"XTENANTPROPERTY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.model.listener.XTenantPropertyEntityListener\",
> \"objectId\":\"XTENANTPROPERTY\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Application

</td>
<td valign="top">

Create Application

</td>
<td valign="top">

-   action: create

-   objectType: APPLICATION


Audit Log

Example:

> ### Output Code:  
> ```
> "message": "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-07-13T05:58:25.864Z\",
> \"id\":\"<msg GUID>\",
> \"object\":{\"type\":\"APPLICATION\",\"id\":{\"class\":\"com.sap.it.spc.apimgmt.entityhandlers.DomainHook\",
> \"objectId\":\"Application\",\"action\":\"create\",
> \"message\":\"application.update\",\"user\":\"<user e-mail>"}},
> \"attributes\":[{\"Application Id"\":\"value\"}],\"status\":\"BEGIN\",
> \"category\":\"audit.configuration\",\"tenant\":\"tenantid\",\"customDetails\":{}}
> 
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Application ID

</td>
<td valign="top">

Update Application ID

</td>
<td valign="top">

-   action: update

-   objectType: APPLICATION


Audit Log

Example:

> ### Output Code:  
> ```
> "message": "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-07-13T05:58:25.864Z\",
> \"id\":\"<msg GUID>\",
> \"object\":{\"type\":\"APPLICATION\",\"id\":{\"class\":\"com.sap.it.spc.apimgmt.entityhandlers.DomainHook\",
> \"objectId\":\"Application\",\"action\":\"update\",
> \"message\":\"application.update\",\"user\":\"<user e-mail>"}},
> \"attributes\":[{\"Application Id"\":\"value\"}],\"status\":\"BEGIN\",
> \"category\":\"audit.configuration\",\"tenant\":\"tenantid\",\"customDetails\":{}}
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Application ID

</td>
<td valign="top">

Delete Application ID

</td>
<td valign="top">

-   action: delete

-   objectType: APPLICATION


Audit Log

Example:

> ### Output Code:  
> ```
> "message": "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-07-13T05:58:25.864Z\",\"id\":\"<msg GUID>\",
> \"object\":{\"type\":\"APPLICATION\",\"id\":{\"class\":\"com.sap.it.spc.apimgmt.entityhandlers.DomainHook\",
> \"objectId\":\"Application\",\"action\":\"delete\",
> \"message\":\"application.delete\",\"user\":\"<user e-mail>"}},
> \"attributes\":[{\"Application Id"\":\"value\"}],\"status\":\"BEGIN\",
> \"category\":\"audit.configuration\",\"tenant\":\"tenantid\",\"customDetails\":{}}
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Subscription

</td>
<td valign="top">

Create Subscription

</td>
<td valign="top">

-   action: create

-   objectType: SUBSCRIPTION


Audit Log

Example:

> ### Output Code:  
> ```
> "message": "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-07-13T05:58:25.864Z\",\"id\":\"<msg GUID>\",
> \"object\":{\"type\":\"user\",\"id\":{\"class\":\"com.sap.it.spc.apimgmt.entityhandlers.DomainHook\",
> \"objectId\":\"Subscription\",\"action\":\"aboutToCreate\",
> \"message\":\"subscription.create\",\"user\":\"<user e-mail>"}},
> \"attributes\":[{\"Application Id"\":\"value\"}],\"status\":\"BEGIN\",
> \"category\":\"audit.configuration\",\"tenant\":\"tenantid\",\"customDetails\":{}}
> 
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Subscription

</td>
<td valign="top">

Update Subscription

</td>
<td valign="top">

-   action: update

-   objectType: SUBSCRIPTION


Audit Log

Example:

> ### Output Code:  
> ```
> "message": "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-07-13T05:58:25.864Z\",\"id\":\"<msg GUID>\",
> \"object\":{\"type\":\"user\",\"id\":{\"class\":\"com.sap.it.spc.apimgmt.entityhandlers.DomainHook\",
> \"objectId\":\"Subscription\",\"action\":\"aboutToUpdate\",
> \"message\":\"application.update\",\"user\":\"<user e-mail>"}},
> \"attributes\":[{\"Application Id"\":\"value\",\"isSubscribed\":\"false\")}],\"status\":\"BEGIN\",
> \"category\":\"audit.configuration\",\"tenant\":\"tenantid\",\"customDetails\":{}}
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Key Map Entry

</td>
<td valign="top">

Create Key Map Entry

</td>
<td valign="top">

-   action: create

-   objectType: KEY MAP ENTRY


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"KEY MAP ENTRY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.KeyMapEntryProcessor\",
> \"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Key Value Map](../50-Development/key-value-map-3722a39.md) 

</td>
</tr>
<tr>
<td valign="top">

Key Map Entry

</td>
<td valign="top">

Update Key Map Entry

</td>
<td valign="top">

-   action: update

-   objectType: KEY MAP ENTRY


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"KEY MAP ENTRY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.KeyMapEntryProcessor\",
> \"objectId\":\"KeyMapEntry\",\"action\":\"update\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Key Map Entry

</td>
<td valign="top">

Delete Key Map Entry

</td>
<td valign="top">

-   action: delete

-   objectType: KEY MAP ENTRY


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"KEY MAP ENTRY\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.KeyMapEntryProcessor\",
> \"objectId\":\"KeyMapEntry\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Key Map Value

</td>
<td valign="top">

Create Key Map Value

</td>
<td valign="top">

-   action: create

-   objectType: KEY MAP VALUE


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"KEY MAP VALUE\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.KeyMapValueProcessor\",
> \"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Create a Key Value Map](../50-Development/create-a-key-value-map-90d8d41.md) 

</td>
</tr>
<tr>
<td valign="top">

Key Map Value

</td>
<td valign="top">

Update Key Map Value

</td>
<td valign="top">

-   action: update

-   objectType: KEY MAP VALUE


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"KEY MAP VALUE\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.KeyMapValueProcessor\",
> \"objectId\":\"KeyMapEntry\",\"action\":\"update\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Update a Key Value Map](../50-Development/update-a-key-value-map-4961431.md) 

</td>
</tr>
<tr>
<td valign="top">

Key Map Value

</td>
<td valign="top">

Delete Key Map Value

</td>
<td valign="top">

-   action: delete

-   objectType: KEY MAP VALUE


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"KEY MAP VALUE\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.KeyMapValueProcessor\",
> \"objectId\":\"KeyMapEntry\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

[Delete a Key Value Map](../50-Development/delete-a-key-value-map-24fbb01.md) 

</td>
</tr>
<tr>
<td valign="top">

Certificate Store

</td>
<td valign="top">

Create Certificate Store

</td>
<td valign="top">

-   action: create

-   objectType: CERTIFICATE STORE


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"CERTIFICATE STORE\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.CertificateStoreProcessor\",
> \"action\":\"create\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Certificate Store

</td>
<td valign="top">

Update Certificate Store

</td>
<td valign="top">

-   action: update

-   objectType: CERTIFICATE STORE


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"CERTIFICATE STORE\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.CertificateStoreProcessor\",
> \"objectId\":\"CertificateStore\",\"action\":\"update\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Certificate Store

</td>
<td valign="top">

Delete Certificate Store

</td>
<td valign="top">

-   action: delete

-   objectType: CERTIFICATE STORE


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"CERTIFICATE STORE\",
> \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.CertificateStoreProcessor\",
> \"objectId\":\"CertificateStore\",\"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Certificate

</td>
<td valign="top">

Create Certificate

</td>
<td valign="top">

-   action: create

-   objectType: CERTIFICATE


Audit Log

Example:

> ### Output Code:  
> > ### Output Code:  
> > ```
> > "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> > \"time\":\"2021-06-09T10:34:32.369Z\",
> > \"id\":\"<ID>\",
> > \"success\":true,\"object\":{\"type\":\"CERTIFICATE\",
> > \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.CertificateProcessor\",
> > \"action\":\"create\",
> > \"message\":\"<based on the event the corresponding meassage will be logged>}"
> > ```



</td>
<td valign="top">

[Manage Certificates](../50-Development/manage-certificates-c665875.md) 

</td>
</tr>
<tr>
<td valign="top">

Certificate

</td>
<td valign="top">

Update Certificate

</td>
<td valign="top">

-   action: update

-   objectType: CERTIFICATE


Audit Log

Example:

> ### Output Code:  
> > ### Output Code:  
> > ```
> > "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> > \"time\":\"2021-06-09T10:34:32.369Z\",
> > \"id\":\"<ID>\",
> > \"success\":true,\"object\":{\"type\":\"CERTIFICATE\",
> > \"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.CertificateProcessor\",
> > \"objectId\":\"Certificate\",\"action\":\"update\",
> > \"message\":\"<based on the event the corresponding meassage will be logged>}"
> > ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Certificate

</td>
<td valign="top">

Delete Certificate

</td>
<td valign="top">

-   action: delete

-   objectType: CERTIFICATE


Audit Log

Example:

> ### Output Code:  
> ```
> "{\"uuid\":\"<msg GUID>\",\"user\":\"<user e-mail>\",
> \"time\":\"2021-06-09T10:34:32.369Z\",
> \"id\":\"<ID>\",
> \"success\":true,\"object\":{\"type\":\"CERTIFICATE\",
> \"objectId\":\"Certificate\",\"id\":{\"class\":\"com.sap.apimgmt.asmprov.core.processor.CertificateProcessor\",
> \"action\":\"delete\",
> \"message\":\"<based on the event the corresponding meassage will be logged>}"
> ```



</td>
<td valign="top">

 

</td>
</tr>
</table>

**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

[Audit Logging in the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/02c39712c1064c96b37c1ea5bc9420dc.html)

