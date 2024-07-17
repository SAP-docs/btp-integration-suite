<!-- loioddc5fdf0027f4089a5078d93f61eeac7 -->

# Creating the References

You can use the CertificateStoreReferences API to create a new certificate store reference.



<a name="loioddc5fdf0027f4089a5078d93f61eeac7__prereq_lmj_lkg_rz"/>

## Prerequisites

-   You must have a service key for the `APIPortal.Administrator` role.

    To know more about creating a service key for accessing APIs in the API portal, see the **Creating a Service Key** section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).

-   You have fetched a valid bearer token. To know more about obtaining a bearer token, see the **Obtaining a Bearer Token** section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).



<a name="loioddc5fdf0027f4089a5078d93f61eeac7__steps_xzq_hr4_dmb"/>

## Procedure

1.  Run the services using a standard REST console.

2.  Create a new certificate store reference using the below API:

    -   Service URL: https://<url-from-service-key\>/apiportal/api/1.0/Management.svc/CertificateStoreReferences
    -   Method: POST
    -   Request Header: Authorization: Bearer <token\>
    -   Content Type: application/json
    -   Accept: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {
        > "name": "reference-name",
        > "certificateStoreName": "store-name"
        > }								
        > 							
        > ```

        > ### Note:  
        > -   name - This is the name of the certificate store reference
        > 
        > -   certificateStoreName - This is the name of the certificate store to which this certificate store reference is pointing to


    -   CertificateStoreReference created successfully

        Response: 201

        > ### Sample Code:  
        > ```
        > {
        > 	"d": {
        > 		"__metadata": {
        > 			"id": "https://<API portal URL>/apiportal/api/1.0/Management.svc/CertificateStoreReferences('reference_ts_1')",
        > 			"uri": "https://<API portal URL>/apiportal/api/1.0/Management.svc/CertificateStoreReferences('reference_ts_1')",
        > 			"type": "apiportal.CertificateStoreReference"
        > 		},
        > 		"certificateStoreName": "ts",
        > 		"life_cycle": {
        > 			"__metadata": {
        > 				"type": "apiportal.History"
        > 			},
        > 			"changed_at": "\/Date(1709793613017)\/",
        > 			"changed_by": "sb-apiaccess1689070958781!b6077|api-portal-xsuaa!b2160",
        > 			"created_at": "\/Date(1709793612858)\/",
        > 			"created_by": "sb-apiaccess1689070958781!b6077|api-portal-xsuaa!b2160"
        > 		},
        > 		"name": "reference_ts_1",
        > 		"storeType": "TRUSTSTORE"
        > 	}
        > }					
        > ```

    -   When a CertificateStoreReference with the same name already exists

        Response: 400 Bad request:

        > ### Sample Code:  
        > ```
        >  
        > {
        > 	"error": {
        > 		"code": "CERTIFICATE_STORE_REFERENCE_NAME_DUPLICATION_ERROR",
        > 		"message": {
        > 			"lang": "en",
        > 			"value": "A certificate store reference already exists with the same name. Please provide a different name and try creating again."
        > 		}
        > 	}
        > }		
        > ```

    -   When no such certificate store exists with the given name

        Response: 400 Bad request

        > ### Sample Code:  
        > ```
        >  
        > {
        > 	"error": {
        > 		"code": "CERTIFICATE_STORE_REFERENCE_CREATE_FAILED_LINKED_CERTIFICATE_STORE_VALIDATION_ERROR",
        > 		"message": {
        > 			"lang": "en",
        > 			"value": "The certificate store reference cannot be created as the certificate store name provided is invalid. Provide a correct certificate store name and try creating again."
        > 		}
        > 	}
        > }					
        > ```



