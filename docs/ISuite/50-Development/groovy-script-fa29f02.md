<!-- loiofa29f02c19e744528b50fd721959f337 -->

# Groovy Script

A Groovy script step can be used in an integration flow for script operations on the message content.

As an integration developer, you often use custom logic and dependencies to extend functionality. While this offers flexibility, inconsistent practices and reliance on internal or unsupported features can create hidden dependencies that make systems fragile. Even minor software changes may cause failures, outages, or complex troubleshooting during major runtime version upgrades.

These upgrade readiness guidelines for groovy script step promotes clean, consistent, and upgrade-ready design to ensure your integrations remain stable, maintainable, and ready for future enhancements.



<a name="loiofa29f02c19e744528b50fd721959f337__proxy-usecase"/>

## Use recommended libraries and classes

This guideline aims to discourage the use of internal and unsupported classes and libraries and highlight the risks associated with them. Using such elements can cause script incompatibilities, runtime errors, maintenance, and upgrade readiness issues.

-   Use recommended libraries: Always use libraries and APIs provided or approved by SAP. This ensures smooth updates and avoids dependency issues.
-   Bundle custom libraries carefully: If a required library isn’t available from SAP, you can include it with your integration flow. Keep in mind this may increase flow size and startup time.
-   Avoid restricted access: Don’t access the operating system, file system, or network directly. Instead, use SAP-provided alternate APIs for secure and supported operations.
-   Avoid using system classes or methods: Using only supported APIs and methods helps you build integrations that are stable, easier to maintain, and resilient to software version changes.

    Examples of unsupported classes include:

    -   System.exit\(\) or TimeZone.setDefault\(\) – these can disrupt the runtime environment and lead to unexpected failures.

    -   Direct access to environment variables using System.getenv\(\) or System.getProperty\(\). Instead, use the provided API com.sap.it.scripts.system. Properties to safely retrieve environment-specific information.

    -   Output methods like System.out.println\(\) or print\(\) – these add unnecessary logs and do not contribute to the integration flow.


-   Replace internal classes: Avoid direct use of internal classes \(such as Camel\). Use SAP API extensions or alternate classes for message handling and system interactions.


For more details about the unsupported classes and suggested standard classes for these unsupported classes, see [KBA](https://itsm.services.sap/now/cwf/agent/kb_view/kb_template_kcs_article/18f1e1f33b5b6610c4e7939e53e45ac8/sub/record/kb_template_kcs_article/18f1e1f33b5b6610c4e7939e53e45ac8) 

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for incompatible libraries and classes, and select *Fix* from the *Actions* column to automatically replace with recommended libraries and classes. The incompaibilities for which an automatic *Fix* is not provided, should be removed from the groovy script manually. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

> ### Note:  
> Upgrade your Groovy script step to benefit from more automatic fixes and help better resolution support for violations.See [Upgrading Groovy Script](upgrading-groovy-script-917e014.md).



<a name="loiofa29f02c19e744528b50fd721959f337__section_fkb_qwl_zfc"/>

## Include only used import statements

Import statements are used to consume Groovy native APIs. Unused import statements in scripts should be avoided as they can cause unnecessary complications during maintenance, software or runtime upgrades.

Even if an import is not actively used in the script, the runtime may attempt to resolve the referenced library or class. If the library is deprecated, removed, or modified in a future runtime version upgrade, this can result in compilation errors or runtime failures.

Additionally, as a best practice unused imports shouldn't be used as they create visual clutter and may mislead into thinking certain dependencies are required.

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for unused import statements, and select *Fix* from the *Actions* column to automatically remove the unused imports. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Use Scripting Appropriately](use-scripting-appropriately-d4dc13c.md "You can use the script step to apply script operations on the message content.")

[Define a Local Script Step](define-a-local-script-step-03b32eb.md "Learn how to use a script step that’s specific to an integration artifact to create custom scripts (JavaScript or Groovy Script).")

