<!-- loioe2a9ec49afdc4087b5fdcd768550a7ed -->

# Updating the References

You can use the CertificateStoreReferences API to update a certificate store reference via service calls.



<a name="loioe2a9ec49afdc4087b5fdcd768550a7ed__prereq_lmj_lkg_rz"/>

## Prerequisites

-   You must have a service key for the `APIPortal.Administrator` role.

    To know more about creating a service key for accessing APIs in the API portal, see the **Creating a Service Key** section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).

-   You have fetched a valid bearer token. To know more about obtaining a bearer token, see the **Obtaining a Bearer Token** section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).



<a name="loioe2a9ec49afdc4087b5fdcd768550a7ed__steps_xzq_hr4_dmb"/>

## Procedure

1.  Run the services using a standard REST console.

2.  Create a new certificate store reference using the below API:

    -   Service URL: https://<url-from-service-key\>/apiportal/api/1.0/Management.svc/CertificateStoreReferences\('<reference-name\>'\)
    -   Method: PUT
    -   Request Header: Authorization: Bearer <token\>
    -   Content Type: application/json
    -   Accept: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {
        > "certificateStoreName": "updated-store-name"
        > }								
        > 							
        > ```

        > ### Note:  
        > certificateStoreName - This is the name of the new certificate store to which this certificate store reference will point to.


    -   CertificateStoreReference updated successfully

        Response: 204 No Content

    -   When no such CertificateStoreReference entity exists with the given name

        Response: 400 Bad request:

        > ### Sample Code:  
        > ```
        >  {
        > 	"error": {
        > 		"code": "NO_SUCH_CERTIFICATE_STORE_REFERENCE_EXISTS",
        > 		"message": {
        > 			"lang": "en",
        > 			"value": "No such certificate store reference exists. Please check the certificate store reference name and try again."
        > 		}
        > 	}
        > }
        > 	
        > ```

    -   When no such certificate store store exists with the given name

        Response: 400 Bad request:

        > ### Sample Code:  
        > ```
        >  {
        > 
        > 	"error": {
        > 		"code": "CERTIFICATE_STORE_REFERENCE_UPDATE_FAILED_LINKED_CERTIFICATE_STORE_VALIDATION_ERROR",
        > 		"message": {
        > 			"lang": "en",
        > 			"value": "The certificate store reference cannot be updated as the certificate store name provided is invalid. Please provide a correct certificate store name and try creating again."
        > 		}
        > 	}
        > }
        > ```



