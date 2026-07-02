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

[Different Methods of Creating an API Proxy](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/4ac0431ddc80469ca31dcd938edc9076.html "An API proxy is the data object that contains all the functionality to be executed when an external user wants to access the backend service.") :arrow_upper_right: 

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

[Edit an API Proxy](https://help.sap.com/viewer/38c3df3f8da44a809f937220b3579607/Cloud/en-US/a64b952578f84161829439c3ee6e967b.html "Once you’ve created an API proxy you can further change the proxy, either on the API portal, or by using the embedded API designer.") :arrow_upper_right: 

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

[Create a Product](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/d7696221f36947a481b154335b89010d.html "Create products to publish a bundle of API proxies together.") :arrow_upper_right: 

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

[Create New Product Subscription for Application](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/a501a6d6c5ee466d99de270b07771126.html "To manage API consumption, create a new product subscription for application. This will provide you with the credentials needed for secure access and allow you to catogorize and analyze data for APIs used by applications.") :arrow_upper_right: 

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

[Create an API Provider](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/6b263e2c1b2d4d9ba20bcd7872eedd9e.html "Define the details of the host you want an application to reach by creating an API provider.") :arrow_upper_right: 

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

[Onboarding an Application Developer](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/786d107e1dbf414ca15ae9ddb2cb49e6.html "As API administrators, you can onboard application developers, enabling them to access Developer Hub.") :arrow_upper_right: 

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

[Key Value Map](https://help.sap.com/viewer/38c3df3f8da44a809f937220b3579607/Cloud/en-US/3722a394e4364711b2b176f6f5b976ed.html "A key value map lets you create and manage collections of arbitrary key value pairs for any number of API proxies. Each key value pair is stored in a map as an entry.") :arrow_upper_right: 

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

[Create a Key Value Map](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/90d8d4186c28475b9fec2f4cf2f45113.html "Create a key value map using the create and manage collections of arbitrary key value pairs for any number of API proxies.") :arrow_upper_right: 

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

[Update a Key Value Map](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/4961431b0cbf4e18bbc037d9c6e9f5f5.html "Update a key value map.") :arrow_upper_right: 

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

[Delete a Key Value Map](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/24fbb01bcc61480ea21962900aaecb04.html "Delete a key value map which is not in use.") :arrow_upper_right: 

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

[Manage Certificates](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/c6658758fa1a4d29a4140a247f5505bb.html "By using certificates, you can ensure that whenever a call is made to your API, there’s a certificate attached to it that confirms the identity of the caller and only if you recognize this identity the API can be processed and return data can be provided.") :arrow_upper_right: 

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

