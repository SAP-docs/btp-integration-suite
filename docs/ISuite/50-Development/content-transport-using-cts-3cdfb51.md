<!-- loio3cdfb512a75941d187b6f5a86e418983 -->

# Content Transport Using CTS+



<a name="loio3cdfb512a75941d187b6f5a86e418983__prereq_exq_kxw_rcb"/>

## Prerequisites

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Cloud Foundry environment.

-   You've set the *Transport Mode* as *CTS+* in the tenant *Transport* settings. For more information, see [Enabling Content Transport, Cloud Foundry Environment](enabling-content-transport-cloud-foundry-environment-452c677.md).

-   You've created two HTTP destinations on *Solutions Lifecycle Management*. One for the tenant management node. For more information, see [Creating HTTP Destinations and Transport Route](creating-http-destinations-and-transport-route-94057be.md). The other one is for CTS+ system via cloud connector. For more information, see [Integration with Transport Management Tools](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/905baea4d6c7404290bff6c042184b4e.html?q=Integration%20with%20Transport%20Management%20Tools).

-   You've the role *WorkspacePackagesTransport* for CF or *IntegrationContent.Transport* for Neo assigned.




## Context

SAP Cloud Integration provides an option to transport integration content directly to *CTS+* system. You can then transport this content from the CTS+ system to your target SAP Cloud Integration tenant. Here's how you can transport content to CTS+.



## Procedure

1.  Select the integration package that you want to transport.

2.  Choose *Transport*.

    If you don't see the *Transport* button, contact your tenant administrator to enable transport option in the tenant settings. For more information on the roles, see [Configuring User Access to Cloud Integration](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/ed6033b2eabe4a64a20cce1e6076bacf.html "Create and modify application roles and assign users to these roles.") :arrow_upper_right: and [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

3.  In the *Transport Comments* prompt, you can see the type of transport under the *Mode* field configured by the tenant administrator. Provide comments under the *Comments* section and choose *Transport*.

    > ### Remember:  
    > The field has a limit of 512 characters. You can use alphabets, numbers, whitespaces, and the following characters: *' - . \_ ~ : \\ / ? \# \[ \] @ ! $ & \( \) \* + , ; = % '* in your comment.
    > 
    > You can use only English text in a single line. You cannot create a new line in the comment.

    You see a prompt with the *Transport ID*. The integration package is transported to the CTS+ system.

4.  Import the content in the target system. For more information, see [Importing transport requests](https://help.sap.com/viewer/62938f21156047718cae23da55f2b443/4.2.9/en-US/408aefc68c754cd0b4941ba508760178.html).


