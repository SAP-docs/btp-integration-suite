<!-- copya4e2fb8e104240d7a4d95b08616c84ea -->

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

    -   [View Bill Details in the API portal](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/2378110c9b23422aa9c7b56afa5c8515.html "View bill details in theAPI portalfor all the applications and products assigned to a particular developer.") :arrow_upper_right:
    -   [View Bill Details in the API business hub enterprise](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/4ddac6740f344f8d8260bbf2db97d950.html "View the bill details in the API business hub enterprise for all the applications subscribed by a developer.") :arrow_upper_right:


