<!-- loio8b79ee8389e84c92befaf96f22c31549 -->

# Managing the Access Request of the Users \[New Design\]

As an API administrator, you can approve or reject the access request made by an application developer to use the API business hub enterprise.



<a name="loio8b79ee8389e84c92befaf96f22c31549__prereq_zkn_2wq_l5b"/>

## Prerequisites

You’re assigned the *AuthGroup.API.Admin* role.

> ### Note:  
> This document describes the new design of the API business hub enterprise. To view the documentation for the classic design, see [Managing the Access Request of the Users \[Classic Design\]](managing-the-access-request-of-the-users-classic-design-5b3e2f6.md).



<a name="loio8b79ee8389e84c92befaf96f22c31549__steps_bln_2wq_l5b"/>

## Procedure

1.  Log on to the API business hub enterprise.

    Use the *Manage Users* page to approve or reject the developer's registration requests and manage the roles of the registered users. For assigning roles to the users, use the SAP BTP Cockpit.

2.  Choose *Enterprise Manager* \> *Manage Users* \> *E-mail Configuration* and add the administrator’s email in the *E-mail Configuration* textbox.

    The administrator receives email notification of the pending developer registration requests on this email id. Also, the e-mail notifications to the developers or users are sent from this e-mail id.

    > ### Note:  
    > Only one administrator’s email address can be entered in the *E-mail Configuration* textbox.

3.  To view the pending requests, navigate to *Manage Users* \> *New Requests*.

4.  Look for the request and choose *Accept Request* from the *Actions* coulmn. The application developer can now access the API business hub enterprise.

    If you don't wish to provide access to the user, choose *Decline Request* from the *Actions* coulmn.

    On accepting the request, an approval email is sent to the requester. On rejecting a request, you need to provide a reason for rejection; an email notification is sent to the requester.

    You can also view the registered users by choosing *Manage Connections* \> *Registered Users*.

    On the *Registered Users* page, you can:

    -   Register a new user by choosing *Add User*.

        > ### Note:  
        > A user must be onboarded to API business hub enterprise only via Self-registration or **Add User** flow.

        In the *Add User* dialog:

        1.  Enter the *User ID* and the user details like *First Name*, *Last Name* and *Email ID*.

        2.  Under *Assigned Roles*, identify the needed scope and select the roles accordingly:


            <table>
            <tr>
            <th valign="top">

            Roles
            
            </th>
            <th valign="top">

            Descrition
            
            </th>
            </tr>
            <tr>
            <td valign="top">
            
            Administrator
            
            </td>
            <td valign="top">
            
            Manages user registration. Create and delete applications on behalf of application developers. In addition, create custom attributes and import the app key.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Developer
            
            </td>
            <td valign="top">
            
            Create applications and check billing and metering data. Test APIs and view analytics data.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Site Administrator
            
            </td>
            <td valign="top">
            
            Configure updates, and perform portal changes like uploading the logo, changing the name and the description, and changing the footer links for the site.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Content Administrator
            
            </td>
            <td valign="top">
            
            Manages content categories.
            
            </td>
            </tr>
            </table>
            

    -   Edit an existing user to add or remove the *Assigned Roles*.


