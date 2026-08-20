<!-- loiofa29f02c19e744528b50fd721959f337 -->

# Scripts

A Groovy or Java script step can be used in an integration flow for script operations on the message content.

As an integration developer, you often use custom logic and dependencies to extend functionality. While this offers flexibility, inconsistent practices and reliance on internal or unsupported features can create hidden dependencies that make systems fragile. Even minor software changes may cause failures, outages, or complex troubleshooting during major runtime version upgrades.

These upgrade readiness guidelines for script step promotes clean, consistent, and upgrade-ready design to ensure your integrations remain stable, maintainable, and ready for future enhancements.

For more details about the unsupported classes and available alternative classes, see [0003645155](https://me.sap.com/notes/0003645155)



<a name="loiofa29f02c19e744528b50fd721959f337__section_HowtoFix"/>

## How to Fix?

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for above design guideline checks, and select *Fix* from the *Actions* column to understand the details and then automatically fix the issue. The incompatibilities \(like few libraries and classes\) for which an automatic fix is not provided, should be removed from the script manually. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Use Scripting Appropriately](use-scripting-appropriately-d4dc13c.md "You can use the script step to apply script operations on the message content.")

[Define a Local Script Step](define-a-local-script-step-03b32eb.md "Learn how to use a script step that’s specific to an integration artifact to create custom scripts (JavaScript or Groovy Script).")

