<!-- loio9af2f05c7eb04457aee5906fd8553e00 -->

# Overview of the SAP Cloud Integration Web UI

The SAP Cloud Integration Web UI is your one-stop shop for integration development.

Note that the URL to access the Web UI ends with `/itspaces`.

The Web UI comprises the following sections:

-   Discover

    Here, you can find predefined integration content provided by SAP that you can use out of the box and adapt to your requirements. As the Getting Started documentation focuses on how to design your own integration content, we do not go into any more detail on this section.

-   Design

    This is where you design your integration content. As you progress through the exercise in the Getting Started documentation, you will spend most of your time in this section. It contains the graphical integration flow modeling environment.

-   Monitor

    This is where you can monitor your integration flow. You also use this section to manage additional artifacts that you need to deploy on your tenant to complement your integration flows \(for example, User Credential artifacts to configure connections using basic authentication\).




<a name="loio9af2f05c7eb04457aee5906fd8553e00__section_mqt_nbm_s2b"/>

## Design Section

When you go to the *Design* section, you find a list of integration packages defined for the tenant.

When you select an integration package, you can find the integration flows \(and other artifacts\) defined for the package \(on the *Artifacts* tab\).

In this Getting Started documentation, we assume that you have not yet defined an integration package for your integration content. Therefore, the first step is to define an integration package.



<a name="loio9af2f05c7eb04457aee5906fd8553e00__section_fkw_xbm_s2b"/>

## Monitor Section

The *Monitor* section \(also referred to as *Operations view*\) has several subsections, each one containing several tiles. These subsections allow you to perform various tasks that are required for an integration project in addition to integration content design.

-   *Monitor Message Processing*

    When you select a tile in this section, you find all messages that have been processed by all integration flows deployed on the tenant. You can find out whether messages have been processed successfully for your integration flow and analyze the situation if not.

-   *Manage Integration Content*

    When you select a tile in this section, you find all deployed integration flows and can check whether deployment was successful. You can also find the endpoint address for your integration flow \(which you need if you want to configure the endpoint in the connected sender system\).

-   *Manage Security*

    -   The *Security Material* tile contains security-related artifacts that are required on the tenant in addition to the security-relevant settings in your integration flow. In the course of the following exercise, you will create and deploy a *User Credentials* artifact to define the user name and password for the mail account that is addressed by the Mail receiver adapter of the integration flow.

    -   The *Keystore* tile shows the content of the tenant keystore, which contains key pairs and certificates required to set up connections that are protected using certificate-based authentication. In the exercise, we need to add certificates when setting up the connection to the e-mail receiver.

    -   The *Connectivity Tests* \(only available in the Neo environment\) tile allows you to test outbound connections \(from SAP Cloud Integration to a receiver system\). We use the connectivity test tool to retrieve the certificates of the e-mail receiver that need to be imported into the tenant keystore.



There are other sections and tiles that are required for additional tasks, but these are not required in the Getting Started exercise, so we will not look at them in any more detail here.

**Related Information**  


[Developing Integration Content with SAP Cloud Integration](developing-integration-content-with-sap-cloud-integration-e6b43b4.md "You can use SAP Cloud Integration to access and design integration content.")

[Monitor](../Operations/monitor-05446d0.md "Check the status of messages and integration content artifacts for a tenant cluster.")

