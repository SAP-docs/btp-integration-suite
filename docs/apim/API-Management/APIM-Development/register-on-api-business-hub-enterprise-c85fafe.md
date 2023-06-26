<!-- loioc85fafe4ff5b4463924e0ccf5b4e0e41 -->

# Register on API business hub enterprise

Procedure to register as an Application developer on the API business hub enterprise to view the products available in the Catalog store. The API business hub enterprise also enables you to explore the APIs, read the associated API Documentation, and view resources.



## Prerequisites

-   As a Developer you’re trying to self-register:

    -   You’re already a valid Application IDP user.

    -   The admin has already added your email ID in the subaccount.


-   As an Admin you're trying to onboard multiple users:

    -   The admin has already added the email IDs of the users in the subaccount.

    -   The admin has assigned the *AuthGroup.API.Admin* role to all the users.

        > ### Note:  
        > While onboarding multiple users, it is recommended that you don't assign the *AuthGroup.API.Admin* role to all the users as this will enable the developers to take on the admin role. Instead you can automate the process of onboarding multiple users by using the API "[API Business Hub Enterprise - Registering Users\(CF\)](https://api.sap.com/api/DevPortal_RegisteringUsers_CF/resource)".


    In this case, admin approval is not required. When the user logs in and chooses the *Register* button, they get auto registered as developers.


> ### Note:  
> The *AuthGroup.API.ApplicationDeveloper* role must not be assigned manually to a user form the SAP BTP Cockpit and this role must not be a part of any user group assignment. This role is assigned by default to a user who onboards to the API business hub enterprise using the Self-registration process or via Add User flow. See [Assign User Roles](../APIM-Initial-Setup/assign-user-roles-911ca5a.md), for more information.



<a name="loioc85fafe4ff5b4463924e0ccf5b4e0e41__context_cfq_41p_qpb"/>

## Context

The procedure below describes the sequence of steps when as a developer you're trying to self-register:



## Procedure

1.  Log on to the API business hub enterprise application with your IDP user credentials.

2.  To register to the API business hub enterprise as an Application developer, choose *Register*.

    A dialog box with the prepopulated data such as, your first name, last name, and e-mail address appears.

3.  Enter the country/region and reason for requesting access to the API business hub enterprise.

4.  Choose *OK*.

    The request is sent to the administrator with the AuthGroup.API.Admin role.

    -   If the administrator approves your request, you’ll receive an e-mail notification. You can log in to the API business hub enterprise via the link provided in the e-mail.

    -   If the administrator rejects the request, you’ll receive an e-mail notification with the reason for the rejection. When you log on to the application, you’ll see the reason for request rejection on the display page.


    > ### Note:  
    > Application Developers can now email to the administrator by replying to the email notification they receive for any queries regarding their access request to the API business hub enterprise application.


