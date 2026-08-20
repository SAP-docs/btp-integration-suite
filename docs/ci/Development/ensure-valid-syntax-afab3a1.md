<!-- loioafab3a1f24594d2fb6badf5014e19f9f -->

# Ensure Valid Syntax



When writing JavaScript within an integration flow, always ensure that the script follows correct and valid syntax. Proper syntax is essential for successful validation and enables further guideline checks to be executed without interruptions.

Scripts that contain syntax errors or invalid constructs cannot be properly validated. This prevents additional checks such as identifying unsupported classes from being performed and may lead to issues during runtime.

Avoid using incomplete statements, incorrect declarations, or unsupported language constructs. For more information, see KBA [3757007](https://me.sap.com/notes/3757007)



### Benefits

-   Scripts can be validated successfully, enabling subsequent quality and compliance checks.
-   Runtime failures are minimized, improving overall reliability and stability.
-   Integration flows become easier to maintain and more future‑ready, as validated scripts are less likely to break with platform updates.

For more details about the unsupported classes and available alternative classes, see [0003645155](https://me.sap.com/notes/0003645155)



## How to Fix?

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for above design guideline checks, and select *Fix* from the *Actions* column to understand the details and then automatically fix the issue. The incompatibilities \(like few libraries and classes\) for which an automatic fix is not provided, should be removed from the script manually. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Scripts](scripts-fa29f02.md "A Groovy or Java script step can be used in an integration flow for script operations on the message content.")

