<!-- loiob2b393d3582344dc80004944b393d227 -->

# Cloned and Uncloned Entities

Refer this section for the entities that are cloned and entities that aren’t cloned during the migration process.



<a name="loiob2b393d3582344dc80004944b393d227__section_svf_jld_2mb"/>

## Entities That Are Cloned

> ### Note:  
> Currently, when a custom role is assigned to a product, the application creation using the tenant cloning tool is not supported.
> 
> As a work-around, before initiating the cloning process, remove the custom role assigned to the product in the source system and proceed with the cloning process.
> 
> After the cloning process is completed, reassign the custom roles to the product in the source system. Also, ensure that the custom roles are assigned to the product in the target system.
> 
> In case the custom roles aren’t appearing in the *Permission* tab, as mentioned in the prerequisite section, ensure that the custom roles are created and assigned to the developers in the target Cloud Foundry environment.

> ### Note:  
> If you have made any customizations to the `HelloWorld` sample proxy, and you want to migrate this proxy to the target, while cloning you might get the following error: `"Unable to import API Proxy from zip file; xml content invalid"`. To address this, execute the following steps:
> 
> 1.  Export the `HelloWorld` API.
> 
> 2.  Open the zip file and edit the metadata.xml file to add the `created_by` field as shown below:
> 
>     > ### Sample Code:  
>     > ```
>     >  <life_cycle>
>     >         <changed_by>yourUserId</changed_by>
>     >         <created_by>yourUserID</created_by>
>     >         
>     >     </life_cycle>
>     > 
>     > ```
> 
>     Please note that your userId is as per your Identity Service configuration. You can find your userId when you open any proxies in the API portal.
> 
> 3.  Save the zip file.
> 
> 4.  Delete the existing `HelloWorld` proxy from SAP Integration Suite.
> 
> 5.  Import this edited zip file.
> 
> 
> With this the `created_by` will reflect in the API proxy.

The following list displays the API Management entities that can be cloned:

-   Certificates and Certificate Store
-   Rate Plans
-   Key Value Maps
-   API Providers
-   Policy Templates
-   API Proxies
-   API Products
-   Application
-   Application Developer
-   Access Control Permissions for API Product
-   Cache Resources
-   CertificateStoreReferences



<a name="loiob2b393d3582344dc80004944b393d227__section_bdp_cmd_2mb"/>

## Content That Are Not Cloned

The following list displays the API Management content that aren’t cloned, including sensitive data like your certificates and credentials.

-   **Analytics Data**
    -   Measure Codes for Custom Measures

    -   Dimension Codes for Custom Dimensions

    -   Custom Metrics and Charts

        > ### Note:  
        > These entities are not cloned via the cloning tool. You have to create them manually in SAP Integration Suite target system under *Analytics*. For more information, see [Advanced API Analytics](../50-Development/advanced-api-analytics-5973d4a.md).


-   **Sensitive Data**

    -   Certificates
    -   Encrypted Key Value Maps
    -   API Provider Passwords
    -   Monetization Bills

    To know about the actions that you must perform for the uncloned certificates, encrypted key value maps, and API provider passwords, see the **User Actions** section in [Post Cloning Tasks](post-cloning-tasks-49e9716.md).

-   **Runtime data**
    -   Quota Counters
    -   OAuth Tokens for API Proxy runtime calls
    -   Runtime states of any API Management entity

-   **Configurations**

    -   Cloud Connector Setup
    -   Custom Role creation and its assignments
    -   Default role assignment to users
    -   Principal Propagation setup for OpProxy
    -   Any configurations created at the subaccount level
    -   Any integrations with other systems \(like SAP Web IDE\)
    -   Custom IDP Setup \(if any\)
    -   Existing Route Bindings \(if any\)

    To know about the actions that you must perform for these uncloned content, see the **Actions required on Configurations** section in [Post Cloning Tasks](post-cloning-tasks-116d82c.md).


