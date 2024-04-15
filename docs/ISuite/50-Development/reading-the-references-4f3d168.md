<!-- loio4f3d168df1d64ca5a888c05dea7543cc -->

# Reading the References

Use the CertificateStoreReference API to get the list of certificate store references.



<a name="loio4f3d168df1d64ca5a888c05dea7543cc__prereq_lmj_lkg_rz"/>

## Prerequisites

-   You must have a service key for the `APIPortal.Administrator` role.

    To know more about creating a service key for accessing APIs in the API portal, see the **Creating a Service Key** section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).

-   You have fetched a valid bearer token. To know more about obtaining a bearer token, see the **Obtaining a Bearer Token** section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).



<a name="loio4f3d168df1d64ca5a888c05dea7543cc__steps_xzq_hr4_dmb"/>

## Procedure

1.  Run the services using a standard REST console.

2.  Get the list of all the certificate store references using the below API:

    -   Service URL: https://<url-from-service-key\>/apiportal/api/1.0/Management.svc/CertificateStoreReferences
    -   Method: GET
    -   Request Header: Authorization: Bearer <token\>
    -   Accept: application/json

    -   Fetches the list of all the certificate store references

        Response: 200

        > ### Sample Code:  
        > ```
        > {
        > 	"d": {
        > 		"results": [
        > 			{
        > 				"__metadata": {
        > 					"id": "https://<application-url>/apiportal/api/1.0/Management.svc/CertificateStoreReferences('reference_ts_1')",
        > 					"uri": "https://<application-url>/apiportal/api/1.0/Management.svc/CertificateStoreReferences('reference_ts_1')",
        > 					"type": "apiportal.CertificateStoreReference"
        > 				},
        > 				"certificateStoreName": "ts_1",
        > 				"life_cycle": {
        > 					"__metadata": {
        > 						"type": "apiportal.History"
        > 					},
        > 					"changed_at": "\/Date(1709810822439)\/",
        > 					"changed_by": "sb-apiaccess1689070958781!b6077|api-portal-xsuaa!b2160",
        > 					"created_at": "\/Date(1709793612858)\/",
        > 					"created_by": "sb-apiaccess1689070958781!b6077|api-portal-xsuaa!b2160"
        > 				},
        > 				"name": "reference_ts_1",
        > 				"storeType": "TRUSTSTORE"
        > 			},
        > 			...............
        > 		]
        > 	}
        > }					
        > ```



