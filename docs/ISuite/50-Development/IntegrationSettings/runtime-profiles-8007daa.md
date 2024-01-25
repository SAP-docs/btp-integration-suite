<!-- loio8007daa7b193409580ba151b1df77fa4 -->

# Runtime Profiles

Cloud Integration allows you to use integration content for different target integration platforms. Accordingly, different runtime profiles are available to adapt the user interface of the integration content designer to the specifications and capabilities of the target integration platform.

A **runtime profile** defines a set of capabilities for Cloud Integration content design supported by a specific target integration platform. In particular, a specific runtime profile supports the configuration of a specific set of adapter types and integration flow steps.

The following runtime profiles are available:

-   **Cloud Integration**

    Cloud-based integration runtime of Cloud Integration

-   **SAP Process Orchestration \(for specific Process Orchestration release\)** 

    For example: **SAP Process Orchestration 7.5, SP05**

    On-premise integration runtime of SAP Process Integration \(for the available release\)

-   Edge Integration Cell

    Hybrid integration runtime offered as part of SAP Integration Suite.


Before working with and designing integration content, you must know on which target runtime you want to deploy the integration content.

All the profiles appear in the *Runtime Profiles* tab. You can enable or disable a runtime profile based on your requirements. Only the enabled runtime profiles appear in the *Runtime Configuration* tab of the integration flow editor.

> ### Note:  
> -   At any point of time, there's only one Cloud Integration runtime profile and you can’t disable it. The option to disable this profile is grayed out.
> 
> -   The Edge Integration Cell runtime profiles can’t be disabled. The *Current Version* column displays the version on which the runtime profile is currently running.
> 
> -   The Edge Integration Cell runtime profiles are updated at cloud speed, which means you must upgrade them monthly. If your runtime is outdated, content deployment and undeployment get blocked. For more information, see [Upgrade Edge Integration Cell](../../upgrade-edge-integration-cell-27c3926.md).
> 
> -   Tenant administrator can decide to enable or disable the *SAP Process Orchestration* supported packages \(SPs\). They can take the decision based on the availability of SPs in the on-premise integration platform.
> 
> -   If you make an *SAP Process Orchestration* runtime as the default profile and disable it, Cloud Integration automatically becomes the default profile.
> 
> -   If you disable a runtime profile that is already used in an integration flow, the integration flow editor sends an alert message indicating that the runtime profile isn’t available. The default runtime profile is automatically used for validations.



When you’ve decided on the runtime profile in question, follow the steps mentioned in [Set Default Runtime Profile](set-default-runtime-profile-efebd50.md).

You have the option to configure a runtime profile also for an individual integration flow \(under *Runtime Configuration*\). See: [Configure Runtime Profile for an Integration Flow](configure-runtime-profile-for-an-integration-flow-65cc0bc.md)



