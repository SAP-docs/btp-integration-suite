<!-- loioc98c87e2882c43d49cc70abfd943a90d -->

# Authorization Options \(Inbound\)

For inbound HTTPS requests, two different ways to check the authorization of the caller can be configured.

We use **inbound** to refer to the communication direction when a sender system sends a message to the integration platform.

-   **Role-based authorization**

    The permissions of the calling entity \(user\) are checked based on a user-to-role assignments configured in the associated identity provider.

    In the related sender adapter, you can assign the role based on which the inbound authorization is to be checked for the integration flow.

-   **Subject/Issuer DN authorization check**

    The distinguished name \(DN\) of a certificate \(associated with the calling entity\) is checked.

    Subject/Issuer DN authorization check can be defined for individual integration flows.


**Related Information**  


[Role-Based Authorization](role-based-authorization-62a0336.md "This option allows you to define permissions for users in the connected identity provider (by default, SAP Identity Service) and to perform an authorization check based on these settings.")

[Subject/Issuer DN authorization check](subject-issuer-dn-authorization-check-3c0fdde.md "It is checked (for a specific integration flow) if the subject/issuer distinguished name (DN) of the assigned certificate matches the incoming certificate.")

