<!-- loio7abd887d54604e699543ef57c618c8d7 -->

# Clone API Management Content

Clone the API Management content using the Tenant Cloning tool.

Once you have your source and target system ready, you can clone your API Management content to the target system by running the Tenant Cloning Tool that you downloaded from [here](https://repo1.maven.org/maven2/com/sap/apimgmt/apim-tct-sdk/1.9.4/apim-tct-sdk-1.9.4.zip).



<a name="loio7abd887d54604e699543ef57c618c8d7__section_fm2_zpd_4mb"/>

## Prerequisites

-   You must have downloaded the Tenant Cloning Tool \(``\) from the link provided above.APIM-TCT-<version\>.zip
-   APIM-TCT-You must have extracted the contents of the `APIM-TCT-<version>.zip` file into a folder \(example name `apim-tct`\).

    This extracted folder must contain:

    -   a java `apim-tct-client-<version>.jar` file
    -   a sample `apim-tct-input.json` file
    -   a `lib` folder \(this folder and it contents must not be modified\)
    -   a `README.md` file
    -   Script files to download open-source libraries that are required to run the `apim-tct-client-<version>.jar` file:
        -   `download_dependencies.ps1` for Windows systems
        -   `download_dependencies.sh` for Mac and Linux systems


    > ### Note:  
    > Download the dependencies as described in the **Downloading the Dependencies** section.

    > ### Note:  
    > If you are using the version of the Tenant Cloning Tool prior to 1.5.2, make sure that you update to the latest version 1.5.2 or above. This is done to handle the critical vulnerability CVE-2021-44228 and CVE-2021-45046, which was detected in the open-source library log4j2.

-   The system running the API Management Tenant Cloning Tool must have Java Runtime Environment 8 or above supported.
-   Microsoft Excel File Reader



### Downloading the Dependencies

**For Windows Systems**:

-   Open the PowerShell terminal.
-   Go to the `apim-tct` folder in the terminal.
-   Run the `.\download_dependencies.ps1` command.

    The required libraries are downloaded to the `lib` folder.


**For Mac and Linux Systems**:

-   Open the default terminal from your system.
-   Go to the `apim-tct` folder in the terminal.
-   Run the `chmod +x download_dependencies.sh` command to make the file executable.
-   Run the `.\download_dependencies.sh` command.

    The required libraries are downloaded to the `lib` folder.


> ### Note:  
> If you encounter an error while running these commands, then you can download the dependencies manually from the link provided in the script file and place them into the `lib` folder.



<a name="loio7abd887d54604e699543ef57c618c8d7__section_ibv_hf2_2bc"/>

## Context

To migrate all API Management entities, you need to complete the apim-tct-input.json file in the tenant cloning tool by providing all the necessary details.

In case you want to migrate selected API proxies from the source API Management tenant to the target API Management tenant, make the following configurations in the `apim-tct-input.json` file:

-   Set `selectiveEntityMigration` to `true`

-   Provide the names of the API proxies in `selectiveEntities`, separated by commas.


For more information, see [selectiveEntityMigration](clone-api-management-content-7abd887.md#loio7abd887d54604e699543ef57c618c8d7__selective_entity_migration) and [selectiveEntities](clone-api-management-content-7abd887.md#loio7abd887d54604e699543ef57c618c8d7__selective_entities).

By enabling this feature, you can explicitly clone the API proxies mentioned in the configuration file from the source to the target tenant. The cloning process will occur in the following sequence:

-   Certificate stores

-   Key value maps entries

-   API providers

-   API proxies


> ### Note:  
> If `selectiveEntityMigration` is set to `true`, only the certificate stores, key-value maps, API providers, and API proxies will be migrated. Other entities such as products and applications will not be migrated. If it is set to `false` or not available in the `apim-tct-input.json` file, all entities will be considered for migration.
> 
> The `selectiveEntityMigration` parameter is optional.

> ### Note:  
> We recommend migrating all API artifacts during the migration activity. While it is possible to selectively migrate API proxies, this should not be the preferred method for migrating API artifacts. It should only be used with careful consideration of dependencies.
> 
> If you need to regularly move or migrate API Management artifacts between SAP Integration Suite tenants, it is recommended to use the transport capability instead. For more information, see [Transport APIs and Its Related Artifacts](../50-Development/transport-apis-and-its-related-artifacts-eb83118.md).



## Procedure

1.  Fill in the `apim-tct-input.json`

    Ensure that you don’t modify the name of the `apim-tct-input.json` file.

    For more information on how to create the service key, refer the [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md) and [Accessing Developer Hub APIs Programmatically](../accessing-developer-hub-apis-programmatically-dabee6e.md).

    **Structure of the apim-tct-input.json file:**


    <table>
    <tr>
    <th valign="top" colspan="3">

    Input Field
    
    </th>
    <th valign="top">

    Credentials Type
    
    </th>
    <th valign="top">

    Data Type
    
    </th>
    <th valign="top">

    Supported Values
    
    </th>
    <th valign="top">

    Required/Optional
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="7">
    
    source
    
    </td>
    <td valign="top" rowspan="3">
    
    apiportal
    
    </td>
    <td valign="top">
    
    `url`
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    URL of the source API management, API portal in the Neo environment

    `https://<application_name><provider_subaccount>-<consumer_subaccount>.<domain>`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `username`
    
    </td>
    <td valign="top" rowspan="2">
    
    Basic
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    User ID having the `APIPortal.Administrator` role in the above subscription

    You’re prompted to enter these values while running the command in Step 3 if you have not already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `password`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Password of the above user

    You’re prompted to enter these values while running the command in Step 3 if you haven’t already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    devportal
    
    </td>
    <td valign="top">
    
    `url`
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    URL of the source API Management, Developer Portal in the Neo environment

    Example: `https://<application_name><provider_subaccount>-<consumer_subaccount>.<domain>`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `username`
    
    </td>
    <td valign="top" rowspan="2">
    
    Basic
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    User ID having the `AuthGroup.API.Admin` role in the above subscription

    You’re prompted to enter these values while running the command in Step 3 if you haven’t already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `password`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Password of the above user

    You’re prompted to enter these values while running the command in Step 3 if you haven’t already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    cfSubaccountTenantID
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
    Supported values: "guid"
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    This is the Tenant ID for your multi-cloud foundation sub account where starter plan serivce instance is enabled.

    > ### Note:  
    > If you are migrating within the same subaccount, you are not required to add this parameter.
    > 
    > This parameter is mandatory if you are migrating to a multi-cloud foundation subaccount, which is different from your existing starter plan subaccount.

    > ### Note:  
    > Navigate to the cockpit to fetch the multi-cloud foundation Tenant ID for the subaccount where the starter plan service instance exists.![](images/Tenant_ID_293b582.png)


    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="24">
    
    target
    
    </td>
    <td valign="top" rowspan="8">
    
    apiportal

    > ### Note:  
    > Choose the relevant fields based on the credential type you've configured for the API access plan. For example, if you've used Client Secret as the credential type, do not select the fields from X509 mTLS.


    
    </td>
    <td valign="top">
    
    `Url`
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    URL received during creation of the service key for API portal API access for the `APIPortal.Administrator` role
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `tokenUrl`
    
    </td>
    <td valign="top" rowspan="3">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    Token URL received during creation of the service key for API portal API access for the `APIPortal.Administrator` role
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `clientId`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The client ID received during creation of the service key for API portal API access for the `APIPortal.Administrator` role

    You’re prompted to enter these values while running the command in Step 3 if you haven’t already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `clientSecret`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The client secret received during creation of the service key for API portal API access for the `APIPortal.Administrator` role

    You’re prompted to enter these values while running the command in Step 3 if you haven’t already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `certurl`
    
    </td>
    <td valign="top" rowspan="4">
    
    X509 mTLS
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Cert URL received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `certificate`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The content of the certificate received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `clientid`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Client ID received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `privatekey`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Private Key received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="8">
    
    apiportalSelfServiceAdmin

    > ### Note:  
    > Choose the relevant fields based on the credential type you've configured for the API access plan. For example, if you've used Client Secret as the credential type, do not select the fields from X509 mTLS.


    
    </td>
    <td valign="top">
    
    `Url`
    
    </td>
    <td valign="top" rowspan="4">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    URL received during creation of the service key for API portal API access for the `APIManagement.SelfService.Administrator` role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `tokenUrl`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    Token URL received during creation of the service key for API portal API access for the `APIManagement.SelfService.Administrator` role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `clientId`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The client ID received during creation of the service key for API portal API access for the `APIManagement.SelfService.Administrator` role.

    You’re prompted to enter these values while running the command in Step 3 if you haven’t already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `clientSecret`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The client secret received during creation of the service key for API portal API access for the `APIManagement.SelfService.Administrator` role.

    You’re prompted to enter these values while running the command in Step 3 if you haven’t already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `certurl`
    
    </td>
    <td valign="top" rowspan="4">
    
    X509 mTLS
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Cert URL received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `certificate`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The content of the certificate received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `clientid`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Client ID received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `privatekey`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Private Key received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="8">
    
    devportal

    > ### Note:  
    > Choose the relevant fields based on the credential type you've configured for the API access plan. For example, if you've used Client Secret as the credential type, do not select the fields from X509 mTLS.


    
    </td>
    <td valign="top">
    
    `url`
    
    </td>
    <td valign="top" rowspan="4">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    URL received during creation of the service key for developer portal API access for the `AuthGroup.API.Admin` role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `tokenUrl`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    Token url received during creation of the service key for Developer Hub API access for the `AuthGroup.API.Admin` role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `clientId`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The client ID received during creation of the service key for developer portal API access for the `AuthGroup.API.Admin` role.

    You’re prompted to enter these values while running the command in Step 3 if you haven’t already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `clientSecret`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The client secret received during creation of the service key for developer portal API access for the `AuthGroup.API.Admin` role.

    You’re prompted to enter these values while running the command in Step 3 if you haven’t already provided these details in the `apim-tct-input.json` file.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `certurl`
    
    </td>
    <td valign="top" rowspan="4">
    
    X509 mTLS
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Cert URL received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `certificate`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The content of the certificate received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `clientid`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Client ID received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `privatekey`
    
    </td>
    <td valign="top">
    
    String
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Private Key received during creation of the service key for API portal API access for the APIPortal.Administrator role.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    skipApplicationKeySecretCloning
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Boolean
    
    </td>
    <td valign="top">
    
    Supported values: `true/false`
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    -   The default value for skipApplicationKeySecretCloning is false.

        > ### Note:  
        > If you want to skip the cloning of Application Key and Secret in side by side migration, then set the `“skipApplicationKeySecretCloning”` flag to true.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    targetDestinationRefreshOnSwitchOver
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Boolean
    
    </td>
    <td valign="top">
    
    Supported values: `true/false`
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The default value for targetDestinationRefreshOnSwitchOver is false.

    > ### Note:  
    > Add this parameter to ensure that during the switchover stage the Tenant Cloning Tool waits for five minutes for the design time to connect to the runtime on the target API portal. If this parameter is not configured, the Tenant Cloning Tool will continue to execute the switchover without any delay.


    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="2">
    
    clone
    
    </td>
    <td valign="top">
    
    skip-apiportal
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Boolean
    
    </td>
    <td valign="top">
    
    Supported values: `true/false`
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    -   The default value for skip-apiportal is false, and API portal entities are cloned
    -   If you set the value for skip-apiportal to true, no cloning of the API portal entities takes place.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    skip-devportal
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Boolean
    
    </td>
    <td valign="top">
    
    Supported values: `true/false`
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    -   The default value for skip-devportal is false, and Developer Portal entities are cloned.
    -   If you set the value for skip-devportal to true, no cloning of the Developer Portal entities takes place.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    stage
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    string
    
    </td>
    <td valign="top">
    
    Supported values: `"DEFAULT" | "SWITCHOVER`
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    The supported values for this parameter is either default or switchover.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    selectiveEntityMigration
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Boolean
    
    </td>
    <td valign="top">
    
    Supported values: true/false
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    If you want to migrate API proxies selectively, please set this flag to 'true'.

    > ### Note:  
    > Once this flag is set to 'true', please ensure that the *selectiveEntities* parameter is not left empty.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    selectiveEntities
    
    </td>
    <td valign="top">
    
    API proxies
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Enter the list of API proxy names in a comma-separated manner as shown below.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Optional
    
    </td>
    <td valign="top">
    
    Enter the API proxies that you want to migrate.

    > ### Sample Code:  
    > ```
    > "selectiveEntityMigration": true, 
    >     "selectiveEntities": { 
    >         "APIProxies": [ 
    >             "SCpayload", "SetTLSPropertiesAsPayload", "newproxy" 
    >         ] 
    >       }
    > ```


    
    </td>
    </tr>
    </table>
    
    \*\*\* apiportalSelfServiceAdmin This input field is mandatory for Starter Plan migration.

    \*\*\* API portal credentials for source and target for all scenarios are mandatory.

    > ### Remember:  
    > For the clone input attribute:
    > 
    > -   Both skip-apiportal and skip-devportal are set to false by default, so, API portal entities are cloned first, followed by Developer Portal entities.
    > -   If both skip-apiportal and skip-devportal are set to true, no cloning takes place.
    > -   If skip-apiportal is set to false, but skip-devportal is set to true, then only the API portal entities are cloned.
    > -   If skip-apiportal is set to true, but skip-devportal to false, then only Developer Portal entities are cloned and cloning for entities \(like applications\) may fail, pertaining to nonavailability of dependent entity \(like API Product\) in Developer Portal.

    Sample configuration:

    ```
    {
        "source": {
            "apiportal": {
                "url": "<URL of Source (Neo based) API Portal>",
                "username": "<user id having APIPortal.Administrator role in above subscription>",
                "password": "<password of the above user>"
            },
            "devportal": {
                "url": "<URL of Source (Neo based) Developer Portal>",
                "username": "<user id having AuthGroup.API.Admin role in above subscription>",
                "password": "<password of the above user>"
            }
            
        },
       
        "target": {
            "apiportal": {
                "url": "<url received during service key creation for API Portal's API Access for APIPortal.Administrator role>",
                "tokenUrl": "<token url received during service key creation for API Portal's API Access for APIPortal.Administrator role>",
                "clientId": "<clientId received during service key creation for API Portal's API Access for APIPortal.Administrator role>",
                "clientSecret": "<clientSecret received during service key creation for API Portal's API Access for APIPortal.Administrator role>"
            },
            "apiportalSelfServiceAdmin": {
                "url": "<url received during service key creation for API Portal's API Access for APIManagement.SelfService.Administrator role>",
                "tokenUrl": "<token url received during service key creation for API Portal's API Access for APIManagement.SelfService.Administrator role>",
                "clientId": "<clientId received during service key creation for API Portal's API Access for APIManagement.SelfService.Administrator role>",
                "clientSecret": "<clientSecret received during service key creation for API Portal's API Access for APIManagement.SelfService.Administrator role>"
            },
     
            "devportal": {
                "url": "<url received during service key creation for Developer Portal's API Access for AuthGroup.API.Admin role>",
                "tokenUrl": "<token url received during service key creation for Developer Portal's API Access for AuthGroup.API.Admin role>",
                "clientId": "<clientId received during service key creation for Developer Portal's API Access for AuthGroup.API.Admin role>",
                "clientSecret": "<clientSecret received during service key creation for  Developer Portal's API Access for AuthGroup.API.Admin role>"
            }
        },
    
       "skipApplicationKeySecretCloning" : <false|true>,
               
       "clone": {
                "skip-apiportal": <false|true> ,
                "skip-devportal": <false|true> 
            },
       "stage": <"DEFAULT" | "SWITCHOVER">
       "selectiveEntityMigration": <false|true>, //If you are setting the 'selectiveEntityMigration' parameter to true, please make sure to enter the names of the API proxies in the 'selectiveEntities' field using a comma-separated format.
       "selectiveEntities": { 
            "APIProxies": ["Proxy1", "Proxy2", "Proxy3"] 
          }
    
    }
    ```

2.  Run the following commands from your Java command-line interface to verify the setup and check the version of the tool. This is an optional step.
    -   To verify the setup:

        `java -jar apim-tct-client-<version>.jar verifyExample:`

    -   To check the version of the tenant cloning tool you’re using:

        `java -jar apim-tct-client-<version>.jar version`


3.  To begin the cloning process, run the following command from your Java command-line interface:

    `java -jar apim-tct-client-<version>.jar`

    **Result**

    Your API Management entities are now cloned to your target system.

    Example:An excel file named `apimtct-output.xlsx` and a log file named `apimtct-logs.log` are generated in the same folder where the .jar file is present.

    The status of each cloned entity is stored in a separate worksheet within the output excel file.

    **Structure of a Worksheet Within apimtct-output.xlsx File**


    <table>
    <tr>
    <th valign="top">

    Column
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    ID
    
    </td>
    <td valign="top">
    
    Entity ID
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Entity name
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Entity type
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Script Execution Timestamp \(UTC\)
    
    </td>
    <td valign="top">
    
    Script execution time in UTC
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Artifact’s Last Modified Timestamp \(UTC\)
    
    </td>
    <td valign="top">
    
    Last modified time of the entity in the source API Management system \(UTC\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    STATUS
    
    </td>
    <td valign="top">
    
    Migration Status:

    -   SUCCESS \(Entity successfully cloned\)
    -   FAILURE \(Entity failed to clone\)
    -   SKIPPED \(Cloning of Entity skipped\)


    
    </td>
    </tr>
    </table>
    
    You can view the status of the cloned content in the `apimtct-output.xlsx` file or in the `apimtct-logs.log` file.

    > ### Note:  
    > -   Ensure that the `apimtct-output.xlsx` file isn’t open while you run the script.
    > -   It’s recommended that you don’t modify the `apimtct-output.xlsx` file.

    **Troubleshooting During Cloning**:

    -   If the Tenant Cloning Tool shuts down unexpectedly, restart and try again.

        If the tool throws an error repeatedly while running, you can report the incident or error on the component OPU-API-OD-DT through the [SAP Support Portal](https://support.sap.com/en/index.html).





<a name="loio7abd887d54604e699543ef57c618c8d7__section_db1_4td_4mb"/>

## Next Steps

After the cloning process completes, you must perform the tasks mentioned in the `User Actions` worksheet within the output excel file `apimtct-output.xlsx`.

To know more about what actions you must take, see the **User Actions** section in [Post Cloning Tasks](post-cloning-tasks-116d82c.md).

To know more about the entities that are cloned and the entities that aren’t cloned, see [Cloned and Uncloned Entities](cloned-and-uncloned-entities-8973ca0.md).

