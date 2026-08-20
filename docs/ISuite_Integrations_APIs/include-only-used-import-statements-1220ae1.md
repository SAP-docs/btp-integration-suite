<!-- loio1220ae1e937e4d5a84c0c2c7abbab9e7 -->

# Include Only Used Import Statements

Import statements are used to consume Groovy and Java native APIs. Unused import statements in scripts should be avoided as they can cause unnecessary complications during maintenance, software or runtime upgrades.

Even if an import is not actively used in the script, the runtime may attempt to resolve the referenced library or class. If the library is deprecated, removed, or modified in a future runtime version upgrade, this can result in compilation errors or runtime failures.

Additionally, as a best practice unused imports shouldn't be used as they create visual clutter and may mislead into thinking certain dependencies are required.

For more details about the unsupported classes and available alternative classes, see [0003645155](https://me.sap.com/notes/0003645155)



## How to Fix?

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for above design guideline checks, and select *Fix* from the *Actions* column to understand the details and then automatically fix the issue. The incompatibilities \(like few libraries and classes\) for which an automatic fix is not provided, should be removed from the script manually. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Scripts](scripts-fa29f02.md "A Groovy or Java script step can be used in an integration flow for script operations on the message content.")

