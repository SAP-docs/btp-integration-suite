<!-- loiofa29f02c19e744528b50fd721959f337 -->

# Groovy Script

A Groovy script step can be used in an integration flow for script operations on the message content.

As an integration developer, you often use custom logic and dependencies to extend functionality. While this offers flexibility, inconsistent practices and reliance on internal or unsupported features can create hidden dependencies that make systems fragile. Even minor software changes may cause failures, outages, or complex troubleshooting during major runtime version upgrades.

These upgrade readiness guidelines for groovy script step promotes clean, consistent, and upgrade-ready design to ensure your integrations remain stable, maintainable, and ready for future enhancements.



<a name="loiofa29f02c19e744528b50fd721959f337__section_fkb_qwl_zfc"/>

## Include only used import statements

Import statements are used to consume Groovy native APIs. Unused import statements in scripts should be avoided as they can cause unnecessary complications during maintenance, software or runtime upgrades.

Even if an import is not actively used in the script, the runtime may attempt to resolve the referenced library or class. If the library is deprecated, removed, or modified in a future runtime version upgrade, this can result in compilation errors or runtime failures.

Additionally, as a best practice unused imports shouldn't be used as they create visual clutter and may mislead into thinking certain dependencies are required.

**How to Fix?**: In the script editor’s *Problems* View, navigate to the *Upgrade Readiness Check*, locate the problem description for unused import statements, and select *Fix* from the *Actions* column to automatically remove the unused imports. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)



<a name="loiofa29f02c19e744528b50fd721959f337__section_jf1_f2m_zfc"/>

## Use supported classes

System classes or methods that are not supported by SAP Integration Suite must not be used. For deatiled information on supported and unsupported calsses, see SAP Note [0003645155](https://me.sap.com/notes/0003645155).

Examples of unsupported classes include:

-   System.exit\(\) or TimeZone.setDefault\(\) – these can disrupt the runtime environment and lead to unexpected failures.
-   Direct access to environment variables using System.getenv\(\) or System.getProperty\(\). Instead, use the provided API com.sap.it.scripts.system.Properties to safely retrieve environment-specific information.
-   Output methods like System.out.println\(\) or print\(\) – these add unnecessary logs and do not contribute to the integration flow.

Using only supported APIs and methods helps you build integrations that are stable, easier to maintain, and resilient to runtime version changes.

**How to Fix?**: There is no automated fix for these issues. You must manually remove unsupported classes and methods from your scripts. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Use Scripting Appropriately](use-scripting-appropriately-d4dc13c.md "You can use the Script step to apply script operations on the message content.")

[Define a Local Script Step](define-a-local-script-step-03b32eb.md "Learn how to use a script step that’s specific to an integration artifact to create custom scripts (JavaScript or Groovy Script).")

