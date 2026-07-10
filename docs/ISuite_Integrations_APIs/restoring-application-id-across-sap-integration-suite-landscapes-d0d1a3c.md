<!-- loiod0d1a3c491db49adb60cda4e9ef15d74 -->

# Restoring Application ID across SAP Integration Suite Landscapes

Maintaining the same application ID across SAP Integration Suite landscapes.



<a name="loiod0d1a3c491db49adb60cda4e9ef15d74__section_ymd_r5j_mjb"/>

## Prerequisites

-   You have the `AuthGroup.API.Admin` role assigned to you.
-   You have the application ID for the application you want to port or recreate.

    > ### Note:  
    > The application ID only contains alphanumeric characters, underscores\(\_\), and hyphens\(-\).




<a name="loiod0d1a3c491db49adb60cda4e9ef15d74__section_dkr_v5j_mjb"/>

## Context

Each application created in a particular SAP Integration Suite landscape is associated with an application ID. When you are migrating to a new SAP Integration Suite landscape, you can recreate the application there, but this will be associated with a new application ID. To ensure that identical applications are available across SAP Integration Suite landscapes, the original application ID is used via an API provided in this document.



<a name="loiod0d1a3c491db49adb60cda4e9ef15d74__section_vrg_z5j_mjb"/>

## Procedure

-   Use the POST operation on the following service URL to create an application. The request body to be used for the POST operation is provided in the sample code.

    **URL**:

    > ### Code Syntax:  
    > ```
    > <dev-portal-host>/odata/1.0/data.svc/APIMgmt.Applications
    > 
    > - The host changes in the above URL depending on what is used.
    > ```

    > ### Sample Code:  
    > ```
    > {
    >   "id": "<application_id>",
    >   "version": "1",
    >   "title": "<application_title>",
    >   "description": "<application_description>",
    >   "callbackurl": null,
    >   "developer_id": "<developer_id>",
    >   "ToSubscriptions": [
    >     {
    >       "ToAPIProduct": [
    >         {
    >           "__metadata": {
    >             "uri": "APIMgmt.APIProducts('<product_name>')"
    >           }
    >         }
    >       ],
    >       "id": "00000000000000000000000000000000"
    >     }
    >   ]
    > }
    > 
    > - Mention the application_title, application_description, developer_id and product_name in the above code along with application id.
    > ```


Using this API will ensure that applications are recreated or ported to the new SAP Integration Suite landscape with the same application ID and are identical.

