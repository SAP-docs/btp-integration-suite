<!-- loio8b79ee8389e84c92befaf96f22c31549 -->

# Managing the Access Request of the Users

As an API administrator, you can approve or reject the access request made by an application developer to use Developer Hub.



<a name="loio8b79ee8389e84c92befaf96f22c31549__prereq_zkn_2wq_l5b"/>

## Prerequisites

You’re assigned the *AuthGroup.API.Admin* role.



<a name="loio8b79ee8389e84c92befaf96f22c31549__steps_bln_2wq_l5b"/>

## Procedure

1.  Log on to **Developer Hub**.

    Use the *Manage Users* page to approve or reject the developer's registration requests and manage the roles of the registered users. For assigning roles to the users, use the SAP BTP Cockpit.

2.  Choose *Admin Center* \> *Manage Users* \> *E-mail Configuration* and add the administrator’s email in the *E-mail Configuration* textbox.

    The administrator receives email notification of the pending developer registration requests on this email id. Also, the e-mail notifications to the developers or users are sent from this e-mail id.

    > ### Note:  
    > Only one administrator’s email address can be entered in the *E-mail Configuration* textbox.

3.  To view the pending requests, navigate to *Manage Users* \> *New Requests*.

4.  Look for the request and choose *Accept Request* from the *Actions* coulmn. The application developer can now access Developer Hub.

    > ### Note:  
    > The user will be added to all the IDPs configured in the sub-account, along with the *ApplicationDeveloper* role.

    If you don't wish to provide access to the user, choose *Decline Request* from the *Actions* coulmn.

    On accepting the request, an approval email is sent to the requester. On rejecting a request, you need to provide a reason for rejection; an email notification is sent to the requester.

    You can also view the registered users by choosing *Manage Connections* \> *Registered Users*.

    On the *Registered Users* page, you can:

    -   <sub>Register a new user by choosing *Add User*</sub>.

        > ### Note:  
        > A user must be onboarded to Developer Hub only via Self-registration or **Add User** flow.

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
            
            Manages user registration. Creates and deletes applications on behalf of application developers. In addition, creates custom attributes and imports the app key.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Developer
            
            </td>
            <td valign="top">
            
            Creates applications and checks billing and metering data, tests APIs, and views analytics data.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Site Administrator
            
            </td>
            <td valign="top">
            
            Configures, updates, and performs portal changes such as uploading the logo, changing the name and description, and modifying the footer links for the site.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Content Administrator
            
            </td>
            <td valign="top">
            
            Creates products that include APIs from different business systems and manages the content that application developers can view in the catalog.
            
            </td>
            </tr>
            </table>
            

    -   Edit an existing user to add or remove the *Assigned Roles*.


