<!-- loioe79810fc92d64c60981cef394c219fb8 -->

# Invoke an API Artifact by Obtaining Credentials via Developer Hub

To invoke an API artifact, you need to obtain the credentials from the subscription for application you created when subscribing to a product in Developer Hub.



<a name="loioe79810fc92d64c60981cef394c219fb8__prereq_nls_54p_42c"/>

## Prerequisites

The *AuthGroup.API.ApplicationDeveloper* role collection must be assigned to you.

The content administrator has already added the API artifact to a product and have published the product. For more information, see [Discover and Publish APIs from SAP Integration Suite on Developer Hub](discover-and-publish-apis-from-sap-integration-suite-on-developer-hub-81b3323.md).



## Context

To obtain the necessary credentials:



## Procedure

1.  Log on to Developer Hub.

2.  Subscribe to the product that contains the API artifact you want to invoke using a REST client. For more information see, [Subscribe to Consume APIs from an Application](subscribe-to-consume-apis-from-an-application-f74f47d.md).

3.  Once the subscription is created, go to the *Overview* tab of your application.

    You will find the *Key*, *Secret*, and *Token URL*, which are used to generate the JWT token required to invoke the API artifact.

    ![](images/Invoke_API_Dev_Hub_a802966.png)




<a name="loioe79810fc92d64c60981cef394c219fb8__postreq_obg_zsp_hgc"/>

## Next Steps

1.  Copy the *Key*, *Secret* and *Token URL*.

2.  Open your REST client.

3.  Use the credentials to invoke the API artifact by including them in the appropriate headers or authentication fields.


