<!-- loiof805b2275dd84dfca0e6e57c91d95e91 -->

# Identity and Access Management for Cloud Integration

Identity and access management features are used during the lifecycle of an integration scenario.



<a name="loiof805b2275dd84dfca0e6e57c91d95e91__section_xfg_5ww_vgb"/>

## Access Management

Dialog users who access the platform are authenticated against an identity provider. SAP Identity Service \(ID Service\) is used by default. SAP ID Service is the central service for the process of managing identities and their lifecycles.



<a name="loiof805b2275dd84dfca0e6e57c91d95e91__section_d2g_5ww_vgb"/>

## User Management and Authorizations

Access to dedicated functions of the platform is controlled and protected by authorization checks. A number of authorization groups are available to manage the authorizations of dialog users. An authorization group is based on a persona and defines a set of dedicated permissions relating to the tasks that come into play during the lifecycle of an integration project.

> ### Note:  
> Example:
> 
> If the logged-in user has to perform tasks such as designing and deploying integration flows, the user must be assigned the authorization group `AuthGroup.IntegrationDeveloper`.



## Authorization for the Integration Developer

The tasks of persons with integration developer permissions \(short: integration developers\) constitute a key part of the SAP Integration Suite lifecycle. Permissions for the integration developer \(who is in charge of modeling integration flows\) are contained in the authorization group `AuthGroup.IntegrationDeveloper`.

Note that the roles contained in this authorization group give an integration developer full control over message processing during runtime.

During integration flow modeling, the integration developer defines how messages are mapped, which credentials are used, and to which recipients messages are sent. The set of roles provides very powerful permissions and in some cases allows the integration developer to access sensitive data.

> ### Note:  
> The integration developer can control which credentials are to be used in connections with basic authentication by deploying the associated *User Credentials* artifacts on the tenant. These artifacts contain user names and passwords. Note that, however, a password specified in a *User Credentials* is never displayed. Furthermore, passwords cannot be downloaded \(by either using the user interface or the application programming interface\). The integration developer, although having full control over the integration flow, does not have access to credentials of another tenant of the same customer.

Therefore, apply the following measures when designing integration flows for security-sensitive areas:

-   Don't give the integration developer access to productive systems.

-   Consider applying a four-eyes principle and implement a review process before deploying integration flows to production.

-   An integration developer has the option to develop integration flows on a separate development or test tenant. These integration flows can then be transported to the productive tenant by another person.

-   Don’t share the same secret credentials between tenants with different security levels \(for example, between test tenant and productive tenant\).

-   If you suspect a security violation, check the audit log to find out which user deployed the integration flow in question.

-   If read-only access is required to analyze issues in the productive system, use the authorization group `AuthGroup.ReadOnly`.


> ### Tip:  
> Instead of using the predefined authorization groups, you can tailor the permissions to your own requirements by applying elementary roles that are defined for individual tasks.
> 
> More information: [Tasks and Permissions for Cloud Integration](tasks-and-permissions-for-cloud-integration-556d557.md)



<a name="loiof805b2275dd84dfca0e6e57c91d95e91__section_icg_5ww_vgb"/>

## Authentication and Authorization Options for Inbound Calls

When a sender system calls the integration platform using HTTPS-based \(inbound\) requests, there are different ways for the calling sender to authenticate itself against the integration platform. The options are basic authentication, OAuth, and SAML.

> ### Note:  
> -   Authentication
> 
>     Verifies the identity of the calling entity.
> 
> -   Authorization
> 
>     Checks what a user or other entity is authorized to do \(for example, as defined by roles assigned to it\). In other words, the authorization check evaluates the access rights of a user or other entity.

**Related Information**  


[Load Balancer Root Certificates Supported by SAP](../40-RemoteSystems/load-balancer-root-certificates-supported-by-sap-4509f60.md "The load balancer supports a certain list of root certificates.")

[Authentication and Authorization Options \(Inbound\)](../40-RemoteSystems/authentication-and-authorization-options-inbound-983f2a5.md "When a client calls a server using a secure communication channel, two different kinds of checks are performed subsequently.")

[Personas](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/4b4ba1c553474259b5be661f4ef0702c.html "When you perform user management tasks using SAP BTP cockpit, you find a set of predefined roles that you can assign to users of the account. According to the main tasks associated with integration projects, these roles are associated to certain persona relevant for an integration project.") :arrow_upper_right:

