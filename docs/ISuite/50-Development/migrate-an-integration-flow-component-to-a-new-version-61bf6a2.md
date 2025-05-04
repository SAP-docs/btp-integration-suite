<!-- loio61bf6a258f054175b128ab70250473ba -->

# Migrate an Integration Flow Component to a New Version

New features are introduced through new versions of integration flow components. To consume



## Context

Once you migrate, old fields will be retained with same values and new fields are populated with default values. If default value is not present for the mandatory field, then you must add the value.

> ### Note:  
> If you want to view the older version, then you must save the integration flow as a version before migrating to new version.

Migration feature is available for the following components:

-   Integration flow configuration
-   Integration process
-   Local integration process

> ### Note:  
> Components with incompatible features won't be migrated. You need to remove and add the component while maintaining its properties manually.

> ### Caution:  
> The integration flow configuration version 1.1 and above supports HTTP session handling and if your original integration flow \(to be migrated\) contains an earlier version of a receiver adapter that doesn’t support HTTP session handling yet, you might run into a version conflict. In that case, the following error is displayed:
> 
> `Version <adapter component version> is not supported with integration flow version <target version of integration flow>, remodel the adapter with new version.`
> 
> The following adapter types can be affected by this problem: HTTP, SOAP, or IDoc receiver adapter.
> 
> What you can do:
> 
> -   Re-model the adapter in the integration flow migrated to the new version \(as proposed in the error message\).This means that you need to re-create the related communication channel.
> 
> -   Revert back to the earlier integration flow version. To do that, you need to make sure that you save the original integration flow as version prior to migrating it to the new version.

A validation check has been added to the 1.2 version of the integration flow configuration in the *Allowed Headers* field that checks for the whitespaces used while entering the header names. If yes, the validation throws an error. To know more, see [Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md).

For additional information on version migration of integration flow components, you can check this SAP community blog: [Versioning & Migration of Components of an Integration Flow in SAP Cloud Integration’s Web Application](https://blogs.sap.com/2017/12/07/versioning-migration-of-components-of-an-integration-flow-in-sap-cloud-platform-integrations-web-application/).



## Procedure

1.  Select an integration flow component.

2.  Choose *Migrate*.

    > ### Note:  
    > -   Migration option will be available only if the selected component has the latest version in your selected runtime profile.

3.  Choose *OK*.

    > ### Note:  
    > You can revert to previous version after migrating also, by executing the following steps:
    > 
    > 1.  Go to package view.
    > 2.  Choose *Draft* version.
    > 3.  From the Version History, select the version you wish to revert to.


