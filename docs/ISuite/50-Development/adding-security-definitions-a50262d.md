<!-- loioa50262dfc4b546d4aaf4bf81c887da0f -->

# Adding Security Definitions

Security definitions allow you to define various authentication types \(security schemes\) supported by an API. If you want to implement any authentication mechanism for your API, then we recommended you to define and apply the associated authentication types in your API.

OpenAPI specification lets you define the following authentication types for an API:

-   **`basic`**

    Used in situations where simple userid/password based authentication is sufficient

-   **`apiKey`**

    Used in situations where the application must authenticate itself by presenting an API Key value as part of every request. This type of authentication is independent of any user authentication.

-   **`oauth2`**

    Used when the Oauth2 based authentication is required.


Authentication types are described using the `securityDefinitions` and `security` properties of the OpenAPI specification. Use the `securityDefinitions` property to define all authentication types supported by the API, and then use the `security` property to apply specific authentication types to the whole API.

In the API below, it supports three security schemes named `basicAuthentication`, `apikeyAuth`, and `OAuth2`. These names are used to refer to these security schemes from elsewhere within the API.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> info:
>   title: >-
>     This sample is a reference service, showcases the e-commerce APIs for products, and suppliers.
> securityDefinitions:
>   basicAuthentication:
>     type: basic
>   apikeyAuth:
>     type: apiKey
>     in: header
>     name: X-API-Key
>   OAuth2:
>     type: oauth2
>     description: >
>       To use this REST API, you need to get OAuth client credentials (client ID
>       and secret) using the SAP BTP Cockpit. After that,
>       you need to pass the obtained client credentials to the SAP BTP token endpoint to obtain an access token. 
>     tokenUrl: >-
>       https://api.hana.ondemand.com/oauth2/apitoken/v1?grant_type=client_credentials
>     flow: application
>     scopes:
>       product_view: Read Product entities
>       product_manage: Manage Product entities
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
> 	"info": {
> 		"title": "This sample is a reference service, showcases the e-commerce APIs for products, and suppliers."
> 	},
> 	"securityDefinitions": {
> 		"basicAuthentication": {
> 			"type": "basic"
> 		},
> 		"apikeyAuth": {
> 			"type": "apiKey",
> 			"in": "header",
> 			"name": "X-API-Key"
> 		},
> 		"OAuth2": {
> 			"type": "oauth2",
> 			"description": "To use this REST API, you need to get OAuth client credentials (client ID and secret) using the SAP BTP cockpit. After that, you need to pass the obtained client credentials to the SAP BTP token endpoint to obtain an access token. \n",
> 			"tokenUrl": "https://api.hana.ondemand.com/oauth2/apitoken/v1?grant_type=client_credentials",
> 			"flow": "application",
> 			"scopes": {
> 				"product_view": "Read Product entities",
> 				"product_manage": "Manage Product entities"
> 			}
> 		}
> 	}
> }
> ```

After you have defined the security schemes in the `securityDefinitions` property, you can apply them to the whole API using the `security` property on the root level. When used on the root level, `security` applies the defined security definitions globally to all the operations within the API. In the following example, the API calls can be authenticated using either basic authentication \(username and password\) or API key.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> info:
>   title: >-
>     This sample is a reference service that showcases the e-commerce APIs for products, and suppliers.
> securityDefinitions:
>   basicAuthentication:
>     type: basic
>   apikeyAuth:
>     type: apiKey
>     in: header
>     name: X-API-Key
>   OAuth2:
>     type: oauth2
>     description: >
>       To use this REST API, you need to get OAuth client credentials (client ID
>       and secret) using the SAP BTP cockpit. After that,
>       you need to pass the obtained client credentials to the SAP BTP token endpoint to obtain an access token. 
>     tokenUrl: >-
>       https://api.hana.ondemand.com/oauth2/apitoken/v1?grant_type=client_credentials
>     flow: application
>     scopes:
>       product_view: Read Product entities
>       product_manage: Manage Product entities
> security:
>   - basicAuthentication: []
>   - apikeyAuth: []
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
> 	"info": {
> 		"title": "This sample is a reference service, which showcases the e-commerce APIs for products, and suppliers."
> 	},
> 	"securityDefinitions": {
> 		"basicAuthentication": {
> 			"type": "basic"
> 		},
> 		"apikeyAuth": {
> 			"type": "apiKey",
> 			"in": "header",
> 			"name": "X-API-Key"
> 		},
> 		"OAuth2": {
> 			"type": "oauth2",
> 			"description": "To use this REST API, you need to get OAuth client credentials (client ID and secret) using the SAP BTP cockpit. After that, you need to pass the obtained client credentials to the SAP BTP token endpoint to obtain an access token. \n",
> 			"tokenUrl": "https://api.hana.ondemand.com/oauth2/apitoken/v1?grant_type=client_credentials",
> 			"flow": "application",
> 			"scopes": {
> 				"product_view": "Read Product entities",
> 				"product_manage": "Manage Product entities"
> 			}
> 		}
> 	},
> 	"security": [
> 		{
> 			"basicAuthentication": []
> 		},
> 		{
> 			"apikeyAuth": []
> 		}
> 	]
> }
> ```

The security scheme applied at the root level can be overridden in individual operations. In the following example, `basic` is defined and applied as security scheme at the root level. Whereas, for /products, the security scheme defined at the root level is overridden by having no security scheme .

> ### Sample Code:  
> API specification in YAML
> 
> ```
> securityDefinitions:
>   basicAuthentication:
>     type: basic
> 
> # To apply Basic auth to the whole API:
> security:
>   - basicAuthentication: []
> 
> paths:
>   /something:
>     get:
>       summary: Get entities from entity set Products
>       description: Get entities from entity set Products
> 
>       # To apply Basic auth to an individual operation:
>       security: [] #No security
>  
>       responses:
>         200:
>           description: OK (successfully authenticated)
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
> 	"securityDefinitions": {
> 		"basicAuthentication": {
> 			"type": "basic"
> 		}
> 	},
> 	"security": [
> 		{
> 			"basicAuthentication": []
> 		}
> 	],
> 	"paths": {
> 		"/something": {
> 			"get": {
> 				"summary": "Get entities from entity set Products",
> 				"description": "Get entities from entity set Products",
> 				"security": [],
> 				"responses": {
> 					"200": {
> 						"description": "OK (successfully authenticated)"
> 					}
> 				}
> 			}
> 		}
> 	}
> }
> ```

