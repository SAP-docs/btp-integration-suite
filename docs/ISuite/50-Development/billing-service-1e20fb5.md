<!-- loio1e20fb575ad644399a7af8e1c4f423d0 -->

# Billing Service

Billing service is available in both SAP Integration Suite and API business hub enterprise.

Using billing service, you can view the bill details and download bill details for a specific developer and for a specific month.

Service to view bills :

-   URL: https://<consumer API-Portal host\>:<port\>//api/1.0/apimgmt/monetize/bills

-   The following table describes the query parameters required to view the bill details.

    **Query parameters**


    <table>
    <tr>
    <th valign="top">

    Parameter name
    
    </th>
    <th valign="top">

    Required in API portal
    
    </th>
    <th valign="top">

    Required in API business hub enterprise 
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Example
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Month
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Month in MM format
    
    </td>
    <td valign="top">
    
    Month = 03
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Year
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Year in YYYY format
    
    </td>
    <td valign="top">
    
    Year = 2017
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    developer\_id
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Developer e-mail Id
    
    </td>
    <td valign="top">
    
    developer\_id = jon.doe@sap.com
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    application\_id
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Id of a specific application for which bill has to be generated
    
    </td>
    <td valign="top">
    
    application\_id = 6C7F88BB-74BE-4CCC-A49A-6A8F2BF1EAC1
    
    </td>
    </tr>
    </table>
    
-   You can also view the bill details in the SAP Integration Suite and API business hub enterprise. For more information see,

    -   [View Bill Details in the SAP Integration Suite](view-bill-details-in-the-sap-integration-suite-2378110.md)
    -   [View Bill Details in the API business hub enterprise](view-bill-details-in-the-api-business-hub-enterprise-4ddac67.md)


