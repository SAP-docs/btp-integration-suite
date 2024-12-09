<!-- loioc111710329174ab69127eb76b18d7c2c -->

# Content Transport using MTAR Download



<a name="loioc111710329174ab69127eb76b18d7c2c__prereq_wnj_stw_rcb"/>

## Prerequisites

-   You have selected *MTAR Download* as your *Transport Mode*. For more information, see [Enabling Content Transport, Cloud Foundry Environment](enabling-content-transport-cloud-foundry-environment-452c677.md).

-   You've the role *WorkspacePackagesTransport* for CF or assigned.




## Context

You can use the *MTAR Download* option to download a MTAR file/s of the integration content to be transported



<a name="loioc111710329174ab69127eb76b18d7c2c__steps_rm3_3qm_1bb"/>

## Procedure

1.  Select the integration package that you want to transport.

2.  Choose *Transport*.

    If you don't see the *Transport* button, contact your tenant administrator to enable transport option in the tenant settings. For more information on the roles, see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

3.  In the *Transport Comments* prompt, you can see the type of transport under the *Mode* field configured by the tenant administrator. Provide comments under the *Comments* section and choose *Transport*.

    > ### Remember:  
    > The field has a limit of 512 characters. You can use alphabets, numbers, whitespaces, and the following characters: *' - . \_ ~ : \\ / ? \# \[ \] @ ! $ & \( \) \* + , ; = % '* in your comment.
    > 
    > You can use only English text in a single line. You cannot create a new line in the comment.

    A file with extension *mtar* is downloaded to your local file system in the download path configured in your browser.

4.  To import the content in the target system, follow the steps mentioned [here](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f598f69a9be347029b7e5e7205fc7d1f.html).


