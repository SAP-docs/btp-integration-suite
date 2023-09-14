<!-- loioeaa8779d05f0479681cad8a09e39d354 -->

# Permissions



<a name="loioeaa8779d05f0479681cad8a09e39d354__section_yh2_xl5_y4b"/>

## Permissions, Cloud Foundry Environment

The the role template `AuthGroup_TenantPartnerDirectoryConfigurator` grants permissions to access \(read and write\) the Partner Directory.

More information:

[Persona](../SecurityNeo/persona-2937e5c.md)

[Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md)



<a name="loioeaa8779d05f0479681cad8a09e39d354__section_h2n_yl5_y4b"/>

## Permissions, Neo Environment

The authorization group `AuthGroup.TenantPartnerDirectoryConfigurator` provides permissions to read and write Partner Directory content \(StringParameter, BinaryParameter, AuthorizedUser, AlternativePartnerId\). You can assign this authorization group to the technical user that uses the Partner Directory remote API.

Read access is protected by the role `TenantPartnerDirectory.read`. This role is assigned to the following authorization groups:

-   AuthGroup.Administrator \(Tenant Administrator\)

-   AuthGroup.IntegrationDeveloper

-   AuthGroup.ReadOnly \(Supporter\)

-   AuthGroup.SystemDeveloper

-   AuthGroup.TenantPartnerDirectoryConfigurator


Write access is protected by the role `TenantPartnerDirectory.write`. This role is assigned to the following authorization groups:

-   AuthGroup.Administrator \(Tenant Administrator\)

-   AuthGroup.TenantPartnerDirectoryConfigurator


Additionally; the authorization group `AuthGroup.TenantPartnerDirectoryConfigurator` contains the roles `NodeManager.deploycredentials` and `NodeManager.readcredentials` for deploying and reading UserCredentialParameters via the Partner Directory OData API.

More information:

[Persona](../SecurityNeo/persona-2937e5c.md)

[Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md)

