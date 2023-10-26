<!-- loio54b4607902a446e39d8a6ba45ce63d6b -->

# Configure the API business hub enterprise \[New Design\]

You can configure the API business hub enterprise to personalize it for your organization.

> ### Note:  
> This document describes the new design of the API business hub enterprise. To view the documentation for the classic design, see [Configure the API business hub enterprise \[Classic Design\]](configure-the-api-business-hub-enterprise-classic-design-7b71b16.md).

Modify the following to personalize the API business hub enterprise:


<table>
<tr>
<th valign="top">

You can use the…

</th>
<th valign="top">

To…

</th>
<th valign="top">

Role that you must be assigned to…

</th>
<th valign="top">

For more information, see…

</th>
</tr>
<tr>
<td valign="top">

*Home Page* 

</td>
<td valign="top">

View and search the categories, APIs, and products

</td>
<td valign="top">

AuthGroup.API.Admin

AuthGroup.API.ApplicationDeveloper

> ### Note:  
> The *AuthGroup.API.ApplicationDeveloper* role is assigned by default to a user who onboards to the API business hub enterprise using the Self-registration process or via *Add User* flow.



</td>
<td valign="top">

[Register on API business hub enterprise](register-on-api-business-hub-enterprise-c85fafe.md) 

</td>
</tr>
<tr>
<td valign="top">

*Site Editor* 

</td>
<td valign="top">

Customize the visual layout of the API business hub enterprise

</td>
<td valign="top">

-   AuthGroup.Site.Admin

-   AuthGroup.API.Admin




</td>
<td valign="top">

[Customize the Visual Format of the API business hub enterprise](customize-the-visual-format-of-the-api-business-hub-enterprise-2eacd52.md) 

</td>
</tr>
<tr>
<td valign="top">

*Enterprise Manager* \> *Manage API Management Connections* 

</td>
<td valign="top">

Approve and reject the pending connection requests and update the API portal access credentials

</td>
<td valign="top">

-   AuthGroup.APIPortalRegistration




</td>
<td valign="top">

[Approve the Pending Connection Requests \[New Design\]](../APIM-Initial-Setup/approve-the-pending-connection-requests-new-design-e296f80.md) 

</td>
</tr>
<tr>
<td valign="top">

*Enterprise Manager* \> *Manage Users* 

</td>
<td valign="top">

Add and Revoke user access to the API Business Hub Enterprise

</td>
<td valign="top">

AuthGroup.API.Admin

</td>
<td valign="top">

[Managing the Access Request of the Users \[New Design\]](managing-the-access-request-of-the-users-new-design-8b79ee8.md)

[Revoke Access \[New Design\]](revoke-access-new-design-ce609bb.md)

</td>
</tr>
<tr>
<td valign="top">

*Enterprise Manager* \> *Manage Domain Categories* 

</td>
<td valign="top">

Create and edit domain specific categories.

</td>
<td valign="top">

-   AuthGroup.Content.Admin

-   AuthGroup.API.Admin




</td>
<td valign="top">

[Manage Domain Categories \[New Design\]](manage-domain-categories-new-design-bd9691d.md)

Also, to add the *AuthGroup.Content.Admin* role, see the table in [Manage Domain Categories \[New Design\]](manage-domain-categories-new-design-bd9691d.md).

</td>
</tr>
<tr>
<td valign="top">

*Enterprise Manager* \> *Manage Notifications* 

</td>
<td valign="top">

Configure notifications for providing information to the API business hub enterprise end users on any website updates or news items.

</td>
<td valign="top">

-   AuthGroup.Site.Admin




</td>
<td valign="top">

[Manage Notifications \[New Design\]](manage-notifications-new-design-df32457.md) 

</td>
</tr>
<tr>
<td valign="top">

*My Workspace* 

</td>
<td valign="top">

Create applications and view your applications, costs and analyze reports.

</td>
<td valign="top">

AuthGroup.API.Admin

> ### Note:  
> Administrators can create applications on behalf of a developer and can see all the applications across developers.

> ### Note:  
> AuthGroup.API.ApplicationDeveloper
> 
> > ### Note:  
> > Application developers can create applications and see only the applications created by him.



</td>
<td valign="top">

[Create an Application \[New Design\]](create-an-application-new-design-a501a6d.md) 

</td>
</tr>
<tr>
<td valign="top">

*Test Environment* 

</td>
<td valign="top">

Test the runtime behaviour of APIs

</td>
<td valign="top">

AuthGroup.API.ApplicationDeveloper

> ### Note:  
> Application developers can test the runtime behaviour of APIs.



</td>
<td valign="top">

[Test Runtime Behavior of APIs \[New Design\]](test-runtime-behavior-of-apis-new-design-15c7d52.md) 

</td>
</tr>
</table>

