<!-- loiobd809db2b63841bab0bc7a3b7159735c -->

# Deleting the References

Use the CertificateStoreReference API to delete the certificate store reference via service calls.



<a name="loiobd809db2b63841bab0bc7a3b7159735c__prereq_lmj_lkg_rz"/>

## Prerequisites

-   You must have a service key for the `APIPortal.Administrator` role.

    To know more about creating a service key for accessing APIs in the API portal, see the **Creating a Service Key** section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).

-   You have fetched a valid bearer token. To know more about obtaining a bearer token, see the **Obtaining a Bearer Token** section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).



<a name="loiobd809db2b63841bab0bc7a3b7159735c__steps_xzq_hr4_dmb"/>

## Procedure

1.  Run the services using a standard REST console.

2.  Delete the certificate store reference using the below API:

    -   Service URL: https://<url-from-service-key\>/apiportal/api/1.0/Management.svc/CertificateStoreReferences\('<reference-name\>'\)
    -   Method: DELETE
    -   Request Header: Authorization: Bearer <token\>
    -   Accept:: application/json
    -   CertificateStoreReference deleted successfully.

        Response: 204: No Content

    -   When no CertificateStoreReference entity exists with the given name

        Response: 400 Bad request

        > ### Sample Code:  
        > ```
        >  
        > {
        > 	"error": {
        > 		"code": "NO_SUCH_CERTIFICATE_STORE_REFERENCE_EXISTS",
        > 		"message": {
        > 			"lang": "en",
        > 			"value": "No such certificate store reference exists. Please check the certificate store reference name and try again."
        > 		}
        > 	}
        > }		
        > ```



