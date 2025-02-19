<!-- loioe2645b5658e64fdfae97aa952756dd01 -->

# Create or Update or Read an Application using Subscription key

Creating, updating, and reading an application using the Subscription key.

You can use the following metadata for Subscription entity.

> ### Note:  
> To use the monetization feature, it is recommended to use Subscription entity and not the Application entity to create or update or read an application.

> ### Sample Code:  
> ```
> <EntityType Name="SubscriptionsType">
> <Key>
> <PropertyRef Name="id"/>
> </Key>
> <Property Name="id" Type="Edm.String" Nullable="false" MaxLength="256"/>
> <Property Name="reg_id" Type="Edm.String" MaxLength="256"/>
> <Property Name="app_id" Type="Edm.String" MaxLength="256"/>
> <Property Name="product_id" Type="Edm.String" MaxLength="256"/>
> <Property Name="developer_id" Type="Edm.String" MaxLength="256"/>
> <Property Name="ratePlan_id" Type="Edm.String" MaxLength="256"/>
> <Property Name="validFrom" Type="Edm.DateTime"/>
> <Property Name="validTo" Type="Edm.DateTime"/>
> <Property Name="app_name" Type="Edm.String" MaxLength="255"/>
> <Property Name="isSubscribed" Type="Edm.Boolean"/>
> <Property Name="status" Type="Edm.String" MaxLength="255"/>
> <Property Name="comment" Type="Edm.String" MaxLength="2048"/>
> <Property Name="created_by" Type="Edm.String" MaxLength="255"/>
> <Property Name="created_at" Type="Edm.DateTime"/>
> <Property Name="modified_by" Type="Edm.String" MaxLength="255"/>
> <Property Name="modified_at" Type="Edm.DateTime"/>
> <NavigationProperty Name="ToApplication" Relationship="developer.Subscriptions_ApplicationsType" FromRole="SubscriptionsDependent" ToRole="ApplicationsDependent"/>
> <NavigationProperty Name="ToRatePlan" Relationship="developer.Subscriptions_RatePlansType" FromRole="SubscriptionsDependent" ToRole="RatePlansDependent"/>
> <NavigationProperty Name="ToAPIProduct" Relationship="developer.Subscriptions_APIProductsType" FromRole="SubscriptionsDependent" ToRole="APIProductsPrincipal"/>
> </EntityType>
> 
> ```

URL of Subscription Entity: <developer portal base url\>/odata/1.0/data.svc/APIMgmt.Subscriptions

Use the below mentioned payload to create an application using Subscription entity :

URL: <developer portal base url\>/odata/1.0/data.svc//APIMgmt.Applications

Request Method: POST

Content-Type: application/json

> ### Code Syntax:  
> Payload
> 
> ```
> {
>     "id": "00000000000000000000000000000000",
>     "version": "1",
>     "title": "App_Title",
>     "description": "Description",
>     "callbackurl": "http://www.callbackurl.com",
>     "ToSubscriptions": [
>         {
>             "id": "00000000000000000000000000000000",
>             "ToAPIProduct": [
>                 {
>                     "__metadata": {
>                         "uri": "APIMgmt.APIProducts('Product_Catalog')"
>                     }
>                 }
>             ],
>             "ToRatePlan": [
>                 {
>                     "__metadata": {
>                         "uri": "APIMgmt.RatePlans('E8BF82AA-F7B0-427F-881A-D246A047BBD0')"
>                     }
>                 }
>             ]
>         }
>     ]
> }
> 
> ```

Use the below mentioned payload to update fields like title or callback url or description in the application using Subscription entity :

URL: <developer portal base url\>/odata/1.0/data.svc/$batch

Method: POST

Content-Type: multipart/mixed; boundary=batch\_349d851f-79ed-44bc-b67a-3159f7cfcc17

Content-Length: <length of the content\>

> ### Code Syntax:  
> Payload
> 
> ```
> --batch_b72a-e938-270d
> Content-Type: multipart/mixed; boundary=changeset_319c-d23e-258e
> 
> --changeset_319c-d23e-258e
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 	
> PUT APIMgmt.Applications('238D7CA1-3F61-470B-BC73-37FF311739E2') HTTP/1.1
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> Content-Type: application/json
> Content-Length: 355
> 
> {"id":"238D7CA1-3F61-470B-BC73-37FF311739E2","title":"App_Title_Updated","callbackurl":"http://www.callbackurl_updated.com","description":"Description Updated.","app_key":"FuoGpWnZR0SJJedimgRpACH6XaiJc1XR","reg_id":"5f1007f1cd5c47ea8a209ce1056798f8","version":"1","app_secret":"rpZAJyTgwFGDLyeh","valid_from":null,"valid_to":null,"developer_id":"I305297"}
> --changeset_319c-d23e-258e--
> 
> --batch_b72a-e938-270d--
> 
> ```

Use the below mentioned payload to update the application to add and remove a product using Subscription entity :

URL: <developer portal base url\>/odata/1.0/data.svc/$batch

Method: POST

Content-Type: multipart/mixed; boundary=batch\_349d851f-79ed-44bc-b67a-3159f7cfcc17

Content-Length: <length of the content\>

> ### Code Syntax:  
> Payload
> 
> ```
> --batch_ce8f-d810-b289
> Content-Type: multipart/mixed; boundary=changeset_0750-94e8-367a
> 
> --changeset_0750-94e8-367a
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> PUT APIMgmt.Applications('238D7CA1-3F61-470B-BC73-37FF311739E2') HTTP/1.1
> RequestId: cf1da741-bd68-401e-95d7-9bcf0475112b
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> x-csrf-token: CF4601D494334B00239A025C270BDBF1
> Content-Type: application/json
> Content-Length: 355
> 
> {"id":"238D7CA1-3F61-470B-BC73-37FF311739E2","title":"App_Title_Updated","callbackurl":"http://www.callbackurl_updated.com","description":"Description Updated.","app_key":"FuoGpWnZR0SJJedimgRpACH6XaiJc1XR","reg_id":"5f1007f1cd5c47ea8a209ce1056798f8","version":"1","app_secret":"rpZAJyTgwFGDLyeh","valid_from":null,"valid_to":null,"developer_id":"I305297"}
> --changeset_0750-94e8-367a
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> POST APIMgmt.Subscriptions HTTP/1.1
> RequestId: cf1da741-bd68-401e-95d7-9bcf0475112b
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> x-csrf-token: CF4601D494334B00239A025C270BDBF1
> Content-Type: application/json
> Content-Length: 322
> 
> {"id":"00000000000000000000000000000000","ToAPIProduct":[{"__metadata":{"uri":"APIMgmt.APIProducts('NorthwindProd')"}}],"ToApplication":[{"__metadata":{"uri":"APIMgmt.Applications('238D7CA1-3F61-470B-BC73-37FF311739E2')"}}],"ToRatePlan":[{"__metadata":{"uri":"APIMgmt.RatePlans('1D8F672C-DFDF-4A73-8BB7-63E649C6BB57')"}}]}
> --changeset_0750-94e8-367a
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> PUT APIMgmt.Subscriptions('3651b33d5fc34f3aa72df7fc0c529450') HTTP/1.1
> RequestId: cf1da741-bd68-401e-95d7-9bcf0475112b
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> x-csrf-token: CF4601D494334B00239A025C270BDBF1
> Content-Type: application/json
> Content-Length: 449
> 
> {"id":"3651b33d5fc34f3aa72df7fc0c529450","isSubscribed":false,"app_id":"238D7CA1-3F61-470B-BC73-37FF311739E2","product_id":"Product_Catalog","developer_id":"I305297","ToAPIProduct":[{"__metadata":{"uri":"APIMgmt.APIProducts('Product_Catalog')"}}],"ToRatePlan":[{"__metadata":{"uri":"APIMgmt.RatePlans('E8BF82AA-F7B0-427F-881A-D246A047BBD0')"}}],"ToApplication":[{"__metadata":{"uri":"APIMgmt.Applications('238D7CA1-3F61-470B-BC73-37FF311739E2')"}}]}
> --changeset_0750-94e8-367a--
> 
> --batch_ce8f-d810-b289--
> 
> ```

Use the below mentioned url and method to delete an application :

URL: <developer portal base url\>/odata/1.0/data.svc/APIMgmt.Applications\('<app\_id\>'\)

Method: DELETE

Use the below mentioned url and method to read all applications using Subscription entity :

URL:<developer portal base url\> /odata/1.0/data.svc/APIMgmt.Applications

Method: GET

Response : It will fetch only application attributes like title, call back url, description.

-   It will not fetch app key and secret.
-   If the application is created using Subscription Entity, then the attached products will not be shown here.
-   Although, if an application is created using older APIs \(only using Application Entity and Application to Product linkage\), then the attached product details will be shown in the navigation “ToAPIProductsDetails”.

Use the below mentioned url and method to read a specific applications using Subscription entity :

URL: <developer portal base url\>/odata/1.0/data.svc/APIMgmt.Applications\('<app\_id\>'\)?$expand=ToAPIProductsDetails,ToSubscriptions/ToAPIProduct,ToSubscriptions/ToRatePlan&$format=json

Method: GET

Response : This API will fetch all the application related details.

-   If the application is created using Subscription entity, the associated products will be found in the navigation “ToSubscriptions/ToAPIProduct”.
-   If the application is created using older API \(only using Application Entity and Application to Product linkage\), the attached product details will be found in the navigation property “ToAPIProductsDetails”.

> ### Note:  
> -   If a user is not willing to use the Monetization feature, then he or she may continue using Application’s service.
> -   If a user is willing to use Monetization feature, then he or she must switch to Subscription entity.
> -   In order to use Monetization, the user needs to create a new rate plan and a new product. Attach the rate plan to the product, publish the product, and let the application developer consume the product via a new application created using Subscription entity.
> -   It is not recommended to use mix and match of Application entity services and Subscription Entity.
> -   It is not recommended to use the application created using Application Entity’s service for Monetization purpose.
> -   It is not recommended to use the application created using Application Entity Service to add a product having rate plan.
> -   If a user has applications created using Application’s entity service and applications created using Subscriptions entity, then user must make two calls while reading the applications:
>     -   One read call on Application's entity.
>     -   One read call on Subscription's entity.

