<!-- loioc85fafe4ff5b4463924e0ccf5b4e0e41 -->

# Register on API business hub enterprise

Procedure to register as an application developer on the API business hub enterprise to view the products available in the catalog store. The API business hub enterprise also enables you to explore the APIs, read the associated API documentation, and view resources.



## Prerequisites

-   As a developer you’re trying to self-register:

    -   You’re already a valid Application IDP user.

    -   The admin has already added your email ID in the subaccount.


    > ### Note:  
    > If the *AuthGroup.API.ApplicationDeveloper* role is already assigned to you by the SAP BTP admin or via the IDP Role Collection mapping, you will get automatically registered as an application developer in API business hub enterprise when you logon for the first time.
    > 
    > If you don't have the *AuthGroup.API.ApplicationDeveloper* role assigned to you in SAP BTP cockpit, complete the self-registration process to access all the funtionalities and features of API business hub enterprise.
    > 
    > Please note that the *AuthGroup.API.ApplicationDeveloper* role that has been assigned to you will only take effect if you login to API business hub enterprise. Only relevant for New Design of the API business hub enterprise.

-   As an Admin you're trying to onboard multiple users:

    -   The admin has already added the email IDs of the users in the subaccount.

    -   The admin has assigned the *AuthGroup.API.Admin* role to all the users.

        > ### Note:  
        > While onboarding multiple users, it is recommended that you don't assign the *AuthGroup.API.Admin* role to all the users as this will enable the developers to take on the admin role. Instead you can automate the process of onboarding multiple users by using the API "[Developer Hub - Registering Users\(CF\)](https://api.sap.com/api/DevPortal_RegisteringUsers_CF/resource)".


    In this case, admin approval is not required. When the user logs in and chooses the *Register* button, they get auto registered as developers.

    > ### Note:  
    > Consider the following behavior for auto-registration:
    > 
    > -   **Use Case 1: User is no longer in the organization:**
    > 
    >     If the *AuthGroup.API.ApplicationDeveloper* role is removed from either the SAP BTP cockpit or the IDP Role Collection mapping, as an admin, you should also ensure that the *AuthGroup.API.ApplicationDeveloper* role is removed from the API business hub enterprise, or vice versa. Failing to do so may lead to confusion and discrepancies.
    > 
    > -   **Use Case 2: User is still in the organization:**
    > 
    >     If a user is still part of the organization, the role removal in BTP will take effect in the API business hub enterprise once the user logs in. If this user wishes to access the API business hub enterprise, they must either follow the self-registration process or have this role assigned to them from the SAP BTP Cockpit.




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


