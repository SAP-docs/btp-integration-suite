<!-- loio54b4607902a446e39d8a6ba45ce63d6b -->

# User Roles and Responsibilities in Developer Hub 

After activating Developer Hub in SAP Integration Suite, you need to assign users the necessary roles and role collections to access the various features and functionalities of .

Once the appropriate roles have been assigned, you can configure and customize Developer Hub to align with your organization's needs.

Your access to various features on Developer Hub will depend on the service plan you have subscribed to.



The roles and features offered in the Standard and Premium service plans include:

-   Key Actions for Admins in Developer Hub


    <table>
    <tr>
    <th valign="top">

    As...
    
    </th>
    <th valign="top">

    You can use…
    
    </th>
    <th valign="top">

    For more information, see…
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="6">
    
    An *API Admin*, you already have the *AuthGroup.API.Admin* role collection assigned to you.
    
    </td>
    <td valign="top">
    
    *Home Page* to browse and search through the various categories, APIs, and products available on the .
    
    </td>
    <td valign="top">
    
    [Register on Developer Hub](register-on-developer-hub-c85fafe.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *My Workspace* to perform the following actions on behalf of an application developer:

    -   Create, update, and delete applications

    -   Create custom attributes for applications

    -   Provide app key and secret, while creating or updating an application

    -   View and access all the applications created in Developer Hub
    -   Monitor costs

    -   Analyze reports



    
    </td>
    <td valign="top">
    
    [Creating an Application with Developer Hub Administrator Role](creating-an-application-with-developer-hub-administrator-role-df4f777.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admin Center* \> *Manage Content* \> *Configurations* to adjust the visibility of the Graph navigator on the Developer Hub.
    
    </td>
    <td valign="top">
    
    [Configure the Visibility of Graph Navigator](https://help.sap.com/docs/integration-suite/sap-integration-suite/manage-external-content-new-design?version=CLOUD&q=Exyternal%20Content) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admin Center* \> *Manage Access* to control the level of access for your users, allowing them to search, discover, and access the content available on Developer Hub.
    
    </td>
    <td valign="top">
    
    [Manage Developer Access](manage-developer-access-9df3ece.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admin Center* \> *Manage Users* to add and revoke user access to Developer Hub.
    
    </td>
    <td valign="top">
    
    [Managing the Access Request of the Users](managing-the-access-request-of-the-users-8b79ee8.md)

    [Revoke Access](revoke-access-ce609bb.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admin Center* \> *Manage API Management Connections* to approve and reject the pending connection requests and update the API portal access credentials.

    > ### Note:  
    > Additinally, the *AuthGroup.APIPortalRegistration* role must be assigned to you to perform the above actions.


    
    </td>
    <td valign="top">
    
    [Approve the Pending Connection Requests](approve-the-pending-connection-requests-e296f80.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="2">
    
    A *Site Admin* you already have the *AuthGroup.Site.Admin* role collection assigned to you.
    
    </td>
    <td valign="top">
    
    *Site Editor* to customize the visual layout of the Developer Hub.
    
    </td>
    <td valign="top">
    
    [Customize the Visual Format of Developer Hub](customize-the-visual-format-of-developer-hub-2eacd52.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admin Center* \> *Manage Notifications* to configure notifications to keep the end users of Developer Hub informed about website updates and news items.
    
    </td>
    <td valign="top">
    
    [Manage Notifications](manage-notifications-df32457.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    A *Content Admin* you already have the *AuthGroup.Content.Admin* role collection assigned to you.
    
    </td>
    <td valign="top">
    
    *Admin Center* \> *Manage Domain Categories* to create domain categories and add the related products into relevant categories.

    > ### Note:  
    > Additinally, the *AuthGroup.API.Admin*


    
    </td>
    <td valign="top">
    
    [Manage Domain Categories](manage-domain-categories-bd9691d.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admin Center* \> *Manage Content* to create products that includes APIs from different business systems and manage the content that application developers can view on the catalog.
    
    </td>
    <td valign="top">
    
     <?sap-ot O2O class="- topic/xref " href="cdf0fabfc91a4cdab97643e7b6e5069a.xml" text="" desc="" xtrc="xref:11" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/54b4607902a446e39d8a6ba45ce63d6b.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?>  
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admin Center* \> *Manage Content* to monitor and manage all requests for product creation and updates.
    
    </td>
    <td valign="top">
    
    [Manage Scheduled Requests](manage-scheduled-requests-7236981.md) 
    
    </td>
    </tr>
    </table>
    
-   Key Actions for Application Developers in Developer Hub


    <table>
    <tr>
    <th valign="top">

    As...
    
    </th>
    <th valign="top">

    You can use…
    
    </th>
    <th valign="top">

    For more information, see…
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    An *Application Developer* you already have the *AuthGroup.API.ApplicationDeveloper* role collection assigned to you.

    > ### Note:  
    > The *AuthGroup.API.ApplicationDeveloper* role collection is assigned by default to a user who onboards to Developer Hub using the Self-registration process or via *Add User* flow.


    
    </td>
    <td valign="top">
    
    The *Home page* to explore the product created on Developer Hub and view the APIs within the products, but you can't subscribe to them.
    
    </td>
    <td valign="top">
    

    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *My Workspace* to create applications, view your applications, monitor costs, and analyze reports.
    
    </td>
    <td valign="top">
    
    [Creating an Application with Application Developer Role](creating-an-application-with-application-developer-role-99515fc.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Test Environment* to test the runtime behaviour of APIs.
    
    </td>
    <td valign="top">
    
    [Test Runtime Behavior of APIs](test-runtime-behavior-of-apis-15c7d52.md) 
    
    </td>
    </tr>
    </table>
    
