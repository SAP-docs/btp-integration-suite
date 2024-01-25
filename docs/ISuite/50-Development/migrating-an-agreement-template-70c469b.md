<!-- loio70c469b1975041e1863aab759f8bdfbc -->

# Migrating an Agreement Template

Migrate an outdated agreement template to the latest format.



## Context

The Agreement Templates that are outdated cannot be edited and have to be migrated to the latest format for edit access.

> ### Note:  
> This template update is only a design-time optimization of the format structure. This does not have any impact on the status of the existing agreements and runtime scenarios.
> 
> Also, migrating the outdated template will not impact the agreements created out of that template.
> 
> Only the outdated template is non-editable. You can still edit and work with the agreements created out of the outdated templates.

The following features are available with the latest format:

-   The agreement template now enables you to configure the trading partner configuration options in a partner independent way using *alias* concept.An alias is a user defined key for the different artifacts that are referenced inside the agreement \(Identifier, System, and other artifacts\). When you define an alias for a trading partner profile and use the same alias in the agreement template, then when an Agreement gets created, the alias will pick up the corresponding trading partner configuration and fill up the fields automatically.

-   The older format allowed you to configure only the Company Profile information. With this new update, you can also configure the Trading Partner details by providing an Alias for the field values. With this update, you can create multiple agreements without having to configure the trading partner details individually for each agreement.



## Procedure

1.  Login to your application and navigate to the *Agreement Templates* tab.

2.  The templates with outdated format will have the label *Outdated Format* below their names under this tab. Choose the template that you want to migrate and choose *Migrate*.

3.  This will open a confirmation dialog prompting you to confirm the migration. Choose *Confirm*.

4.  You have now migrated your agreement template successfully. You can now start working with the template. To know more, see [Creating an Agreement Template](creating-an-agreement-template-9692cb1.md) .


