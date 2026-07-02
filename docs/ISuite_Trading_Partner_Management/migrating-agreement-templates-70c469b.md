<!-- loio70c469b1975041e1863aab759f8bdfbc -->

# Migrating Agreement Templates

Migrate an outdated agreement template to the latest format.



## Context

The agreement templates that are outdated can't be edited and have to be migrated to the latest format to enable editing.

> ### Caution:  
> The support for the outdated agreement template format ends **by 31 August 2026**. Please migrate to the latest format as soon as possible to avoid maintenance issues.

> ### Note:  
> This template update is only a design-time optimization of the format structure. It doesn't have any impact on the status of the existing agreements and runtime scenarios.
> 
> Also, migrating the outdated template doesn't impact the agreements created from that template.
> 
> Only the outdated template is non-editable. You can still edit and work with the agreements created out of the outdated templates.

The following features are available with the latest format:

-   The agreement template now enables you to configure the trading partner configuration options in a partner-independent way using *alias* concept. An alias is a user-defined key for the different artifacts that are referenced inside the agreement \(Identifier, System, and other artifacts\). If you defined an alias for a trading partner profile and use the same alias in the agreement template, when an agreement is created, the alias picks up the corresponding trading partner configuration and fills up the fields automatically.

-   The older format allowed you to configure only the company profile information. With the update, you can also configure the trading partner details by providing an alias for the field values. You can also create multiple agreements without having to configure the trading partner details individually for each agreement.



## Procedure

1.  Log in to your application and navigate to the *Agreement Templates* tab.

2.  The templates with outdated format have the label *Outdated Format* below their names under this tab. Choose the template that you want to migrate and choose *Migrate*.

3.  A confirmation dialog opens, prompting you to confirm the migration. Choose *Confirm*.

    You have now migrated your agreement template. You can now start working with the template. To learn more, see [Creating an Agreement Template](creating-an-agreement-template-9692cb1.md) .


