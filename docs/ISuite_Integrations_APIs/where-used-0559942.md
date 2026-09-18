<!-- loio05599423e42f4c1c86500edb5cac449c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Where Used

This feature lets you identify all integration flows that reference a specific security material.

In large organizations, a single credential or certificate can be referenced across multiple integration flows. This feature eliminates the need to manually inspect each one by giving you an immediate, accurate view of all impacted flows where the security material is used.



## Key Benefits

1.  **Avoid Disruptions**: Before updating or rotating a security material, instantly identify all integration flows that will be affected; reducing the risk of unexpected integration failures.

2.  **Direct navigation**: From the where-used results, navigate directly to any integration flow that references the security material, without manually searching your tenant.

3.  **Security material lifecycle management**: Quickly locate and clean up security materials that are no longer referenced in any integration flow.




## Scope and Static References

Where Used identifies security materials that are statically referenced in the design-time integration flow configuration. Security materials referenced dynamically, for example, through message headers or exchange properties at runtime are not detected.



## How the where-used data is updated

The where-used information is updated automatically in two ways:

-   *On User Action*: When an integration flow is saved, deleted or modified, its security material references are immediately updated in the database. For recently edited flows, the where-used data is always current and accurate.
-   *By Background Job*: Integration flows that have not been recently modified are processed by a scheduled job, which scans flows in small batches with the oldest created flows first. The database is then updated progressively.

Until the background job has completed a full scan of all integration flows in your tenant, the where-used data may be incomplete. Integration flows that have not yet been processed may not appear in the results, or their security material references may not reflect the latest state.

> ### Note:  
> If you are planning a security material update, allow time for the background job to complete its scan to ensure the where-used results are fully accurate before proceeding.



## Context

This is useful when a security material needs to be updated and the requirement is to analyze the usage in various integration flows. Instead of manually checking each integration flow, you can instantly see all the places where the security material it is used. Supported security material types are:

-   User Credentials
-   OAuth2 Client Credentials
-   OAuth2 Password Credentials
-   OAuth2 SAML Bearer Assertion
-   OAuth2 Authorization Code
-   Secure Parameter



## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.
2.  Choose the *Runtime* for which you wish to view the security material.
3.  Select the **Security Material** tile in the **Manage Security** section.
4.  For the respective security material, from the **Actions** column, choose <span class="SAP-icons-V5"></span>.
5.  Choose the where-used icon <span class="BusinessSuiteInAppSymbols-V2"></span>.

    The where-used dialog appears and it displays the following details about the artifact, which uses this security material:

    **Where-used**


    <table>
    <tr>
    <th valign="top">

    Columns
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Name of the artifact where this security material is used.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    The artifact type like integration flow, adapter etc.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Package
    
    </td>
    <td valign="top">
    
    The package where the artifact resides.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Component
    
    </td>
    <td valign="top">
    
    The flow component within the artifact, which utilizes this security material.
    
    </td>
    </tr>
    </table>
    

