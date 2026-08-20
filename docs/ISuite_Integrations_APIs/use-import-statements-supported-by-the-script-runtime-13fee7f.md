<!-- loio13fee7f6786444bdbfa0a84172510e7b -->

# Use Import Statements Supported by the Script Runtime

This design guideline ensures that groovy scripts use import statements compatible with its runtime version. Incompatible import statements can lead to compilation failures and upgrade readiness issues when scripts are executed on the runtimes.

The guideline identifies imports that are not supported by the target runtime and recommends the appropriate runtime-compatible alternatives.

This guideline scans version 2 of the script only. See [Upgrading Script](upgrading-script-917e014.md)

> ### Example:  
> The import `import groovy.util.XmlSlurper`is incompatible with the Groovy 4 runtime. It should be replaced with `import groovy.xml.XmlSlurper`.

For more details about the unsupported classes and available alternative classes, see [0003645155](https://me.sap.com/notes/0003645155)



## How to Fix?

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for above design guideline checks, and select *Fix* from the *Actions* column to understand the details and then automatically fix the issue. The incompatibilities \(like few libraries and classes\) for which an automatic fix is not provided, should be removed from the script manually. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Scripts](scripts-fa29f02.md "A Groovy or Java script step can be used in an integration flow for script operations on the message content.")

