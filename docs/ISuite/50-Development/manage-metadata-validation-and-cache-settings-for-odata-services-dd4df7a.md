<!-- loiodd4df7aa89174b539a9f35ac81de4c14 -->

# Manage Metadata Validation and Cache Settings for OData Services

Enable or disable metadata validation for a registered OData service. You can also allow caching of metadata, which significantly improves performance of the OData service calls. Additionally, you can view the list of services which has cached metadata. You can clear the metadata cache of the selected service or all the services.



<a name="loiodd4df7aa89174b539a9f35ac81de4c14__prereq_v4v_zzp_tjb"/>

## Prerequisites

-   You’ve activated the OData Provisioning capability, and have completed the steps for runtime access and role assignment. See [Activating and Managing Capabilities](../activating-and-managing-capabilities-2ffb343.md) and [Runtime Access and Role Assignment for OData Provisioning](../runtime-access-and-role-assignment-for-odata-provisioning-b46816c.md).
-   You have the*ODPAPIAccess* and *ODPManage* roles assigned. See [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).



## Procedure

1.  In the Integration Suite, navigate to *Settings* \> *OData Services*.

2.  Use any of the following options based on your requirements:


    <table>
    <tr>
    <th valign="top">

    User Interface Element
    
    </th>
    <th valign="top">

    Action
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Metadata Validation**
    
    </td>
    <td valign="top">
    
    Use the toggle button to activate or deactivate metadata validation.

    Metadata validation is inactive for registered services by default. If you choose to enable this option, we recommend having the same length for the edm properties and the corresponding back-end \(ABAP\) properties.

    > ### Example:  
    > Consider a scenario where you've activated metadata validation. If the ABAP type defined in the back end for a property supports a length greater than the length of the edm type defined in the metadata for the same property, then modify requests like PUT or POST result in a metadata validation error. To avoid such errors, you can deactivate metadata validation. In this scenario, if metadata validation is inactive, but the back end validates the input, a modifying request can still result in an error.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Cache Metadata**
    
    </td>
    <td valign="top">
    
    Use the toggle button to activate or deactivate the metadata cache. When you deactivate the metadata cache, exisiting metadata is cleared from the runtime cache and the metadata is always retrieved from the back-end system for every service document or metadata call of the registered OData services.

    By default, the metadata cache and destination-based metadata caching are activated. Enabling these cache options fetches and caches the service metadata from a default or specific destination on the first request. All subsequent calls to the service for this destination use the cached metadata.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Destination-Based Metadata Caching**
    
    </td>
    <td valign="top">
    
    Use the toggle button to activate or deactivate destination-based metadata caching .

    Destination-based metadata caching is enabled automatically when you choose to enable metadata caching. Disable destination-based caching only if the metadata for a registered service is the same across all the destinations. This rule applies to all registered services.

    When this setting is disabled, the service metadata is fetched and cached from any available destination on the first request. All subsequent calls to the service use the cached metadata. Disabling this setting becomes useful when you have users who can't access all destinations, especially those destinations that are set as the default or the metadata default. Enabling or disabling this setting clears any existing cache.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Clear Cache \(Table Header\)**
    
    </td>
    <td valign="top">
    
    Clears the metadata cache for the corresponding service.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Clear All**
    
    </td>
    <td valign="top">
    
    Clears the metadata cache for all services with metadata cache listed in the table.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Refresh**
    
    </td>
    <td valign="top">
    
    Refreshes the list of services with metadata cache.
    
    </td>
    </tr>
    </table>
    

**Related Information**  


[Register OData Services](register-odata-services-9dfa56a.md "You can register OData services in the SAP Integration Suite to access back-end services from SAP Business Suite .")

[Monitor Errors from OData Provisioning](monitor-errors-from-odata-provisioning-e0aeecf.md "Analyze the root cause for errors and where they originated.")

