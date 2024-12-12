<!-- loio47439ac3bb134d809291dbd52aca7657 -->

# Review Integration Technology

Review and adjust related integration technologies and add technology instances.

You can use SAP standard integration technologies \(for example, SAP Integration Suite, Cloud Integration\), or you can adjust the configuration to use your own integration technologies.



<a name="loio47439ac3bb134d809291dbd52aca7657__section_syc_zkc_nsb"/>

## Defining Integration Technology

1.  Go to *Configure* \> *Integration Technologies*. In the Technology Profile tab, you will be able to see the list of existing technology profiles. You can either choose from the existing SAP standard content or create and customise your own technology profile.

    > ### Note:  
    > SAP defined integration technology is visible for all the users whereas, custom technology is displayed only for specific users.

2.  Choose \(*Create*\) to add a new integration technology.

3.  Under *Create Technology Profile*, specify the following attributes:

    ****


    <table>
    <tr>
    <th valign="top">

    Attribute
    
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
    
    Specify the name of the technology.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Vendor
    
    </td>
    <td valign="top">
    
    Specify a vendor.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Domains
    
    </td>
    <td valign="top">
    
    Select one or multiple domains.

    > ### Example:  
    > If you want to use the integration technology to connect cloud applications with each other as well as with on-premise applications, select the following domains:
    > 
    > -   *Cloud to Cloud*
    > 
    > -   *On-Premise to Cloud*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Styles
    
    </td>
    <td valign="top">
    
    Select one or multiple integration styles.

    > ### Example:  
    > If you want to use the integration technology to integrate processes, select *Process Integration*.


    
    </td>
    </tr>
    </table>
    
4.  Select *Create*.

5.  Select the integration technology from the list.

6.  To specify more details about the technology, choose *Edit*.

    You can specify different attributes in the following tabs.

    ****


    <table>
    <tr>
    <th valign="top">

    Tab
    
    </th>
    <th valign="top">

    Settings
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    General
    
    </td>
    <td valign="top">
    
    Use this tab to specify the following attributes:

    -   Technology instances: specify an instance name and a deployment model.

    -   Attachments: specify a name and a URL.


    > ### Note:  
    > The technology name and vendor name for SAP delivered content cannot be edited. You can edit these in custom content.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Domains and Styles
    
    </td>
    <td valign="top">
    
    Use this tab to specify domains and styles.

    These settings are predefined when creating the technology.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key Characteristics
    
    </td>
    <td valign="top">
    
    Use this tab to maintain information about the extent to which the relevant key characteristic and their values are covered by the technology.

    > ### Note:  
    > The available options for the key characteristics and the displayed information depends on the content provided for the key characteristics. You can see this content in the *Settings* section.

    Select a key characteristic group, for example *Connectivity*.

    A table shows the defined key characteristic values \(vertical axis\) for each key characteristic \(horizontal axis\) in the selected group.

    While defining the key characteristic for a technology, you can choose the table cells highlighted as *Not Defined* to define a recommendation degree for the technology selected. Choose *Create Recommendation Degree* and select the relevant recommendation degree from the list.

    You can also change or delete the existing recommendation degree by selecting the relevant option for a technology.

    > ### Note:  
    > For SAP delivered technologies, for the first time you have to delete the existing recommendation degree and then continue creating the recommendation degrees. Subsequently, you will be able to update it as it is considered as custom key charcteristic technology.

    *Defining Recommendation Degree*

    You can select from the following pre-defined recommendation degrees:

    -   Recommended
    -   Partially Possible
    -   Not Recommended
    -   Not Supported/Not Relevant

    You can provide an optional description which you can see when you select the table cell.
    
    </td>
    </tr>
    </table>
    

