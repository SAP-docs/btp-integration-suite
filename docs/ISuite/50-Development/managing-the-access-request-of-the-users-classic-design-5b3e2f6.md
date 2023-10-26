<!-- loio5b3e2f607046447c867db43e9b7859c7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing the Access Request of the Users \[Classic Design\]

Procedure to provide or reject access to an Application developer for using the API business hub enterprise.



<a name="loio5b3e2f607046447c867db43e9b7859c7__prereq_edg_5fq_l5b"/>

## Prerequisites

You’re assigned the *AuthGroup.API.Admin* role.

> ### Note:  
> This document describes the classic design of the API business hub enterprise. To view the documentation for the new design, see [Managing the Access Request of the Users \[New Design\]](managing-the-access-request-of-the-users-new-design-8b79ee8.md).



<a name="loio5b3e2f607046447c867db43e9b7859c7__steps_gdg_5fq_l5b"/>

## Procedure

1.  Log on to the API business hub enterprise.

2.  Choose *Manage* \> *Manage Users*.

    Use the *Manage Users* page to onboard the application developers. For assigning roles to other users, use the SAP BTP Cockpit.

3.  Add the email id in the textbox.

    This email id is used to receive email notification of the pending requests and send approvals.

4.  To view the pending requests, navigate to *Pending* section .

5.  In the pending section, **Approve** or **Reject** the request by choosing the corresponding action item in the *Actions* column.

    On accepting the request, an approval email is sent to the requester. On rejecting a request, you need to provide a reason and an email notification is sent to the requester with the mentioned reason.

    To view registered users, navigate to *Registered Users* section.

    In the *Registered Users*section, you can perform the following:

    -   Edit an existing user to add or remove user roles.
    -   Register a new user by selecting the :heavy_plus_sign: icon.
        -   In the *Add User* dialog:

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
                




**Related Information**  


[Configure the API business hub enterprise \[Classic Design\]](configure-the-api-business-hub-enterprise-classic-design-7b71b16.md "You can configure the API business hub enterprise to personalize it for your organization.")

[Revoke Access \[Classic Design\]](revoke-access-classic-design-147fb9d.md "Revoke the access of an application developer.")

