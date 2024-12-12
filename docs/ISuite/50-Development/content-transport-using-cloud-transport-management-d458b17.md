<!-- loiod458b172b98d4112a08499541fddfc54 -->

# Content Transport Using Cloud Transport Management



<a name="loiod458b172b98d4112a08499541fddfc54__prereq_exq_kxw_rcb"/>

## Prerequisites

-   You've set the *Transport Mode* as *Transport Management Service* in the tenant *Transport* settings. For more information, see [Enabling Content Transport, Cloud Foundry Environment](enabling-content-transport-cloud-foundry-environment-452c677.md).
-   You've created necessary HTTP destinations and transport routes. For more information, see [Creating HTTP Destinations and Transport Route](creating-http-destinations-and-transport-route-94057be.md).
-   You've the role *WorkspacePackagesTransport* for CF or *IntegrationContent.Transport* for Neo assigned.




<a name="loiod458b172b98d4112a08499541fddfc54__context_uzq_c2x_ddb"/>

## Context

Cloud Integration provides an option to transport integration content to Cloud Transport Management system. You can then transport this content from the Cloud Transport Management system to your target Cloud Integration tenant.

Here's how you can transport content to Cloud Transport Management:



<a name="loiod458b172b98d4112a08499541fddfc54__steps_o4y_qdx_ddb"/>

## Procedure

1.  Select the integration package or artifact that you want to transport.

    If you want to use the Content Agent Service's web UI to trigger the transport, see: [Export Content Wizard](https://help.sap.com/docs/CONTENT_AGENT_SERVICE/ae1a4f2d150d468d9ff56e13f9898e07/b23677cfafeb47afad66530ff6a8c35d.html).

2.  Choose *Transport*.

    If you don't see the *Transport* button, contact your tenant administrator to enable transport option in the tenant settings. For more information on the roles, see [Configuring User Access to Cloud Integration](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/ed6033b2eabe4a64a20cce1e6076bacf.html "Create and modify application roles and assign users to these roles.") :arrow_upper_right: and [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

3.  In the *Transport Comments* prompt, you can see the type of transport under the *Mode* field configured by the tenant administrator. Provide comments under the *Comments* field and choose *Transport*.

    > ### Remember:  
    > The field has a limit of 512 characters. You can use alphabets, numbers, whitespaces, and the following characters: *' - . \_ ~ : \\ / ? \# \[ \] @ ! $ & \( \) \* + , ; = % '* in your comment.
    > 
    > You can use only English text in a single line. You cannot create a new line in the comment.

    You see a prompt with the *Transport ID*. The content gets transported to the Cloud Transport Management system.

4.  Enable the *Propagate logged-in user as transport owner* checkbox to send the logged-in user's ID to Cloud Transport Management system so that you can easily identify the artifacts triggered for transport by a particular user. The user ID depends on the attributes configured in the Identity Provider system.

5.  To import the content in the target system, follow the steps mentioned in the [official documentation](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/d2005d5d2fc346b98eff7146107243fc.html) for Cloud Transport Management service.


