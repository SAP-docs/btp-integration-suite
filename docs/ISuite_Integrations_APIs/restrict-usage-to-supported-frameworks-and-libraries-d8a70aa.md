<!-- loiod8a70aaf140a4d28acad39b827abbad1 -->

# Restrict Usage to Supported Frameworks and Libraries

This guideline helps identify the use of internal, unsupported, or restricted classes and libraries in groovy scripts. Using unsupported frameworks can result in runtime failures, upgrade incompatibilities, maintenance challenges, and unexpected behavior after software updates.

No automatic fix is provided for this; you must manually replace or remove unsupported implementations.

> ### Note:  
> The guideline scans both versions of groovy scripts version 1 and version 2. See [Upgrading Script](upgrading-script-917e014.md)

To ensure long-term stability and upgrade readiness:

-   **Use Supported Libraries**: Always use libraries and APIs provided or approved by SAP. This helps maintain compatibility across upgrades and reduces dependency-related issues.

-   **Bundle External Libraries Carefully**: If a required library is not available in SAP Integration Suite, it can be bundled with the integration flow. However, additional libraries may increase artifact size and startup time.

-   **Avoid Restricted System Access**: Do not directly access the operating system, file system, network resources, or runtime environment. Use SAP-provided APIs for secure and supported operations.

-   **Avoid Unsupported System Classes**: Using internal or unsupported classes can lead to runtime instability and upgrade issues. Prefer supported SAP APIs and extensions.


The guideline detects usage of unsupported class groups, including:

-   `org.bouncycastle.`

-   `org.opensaml.xmlsec.signature.`

-   `org.jasypt.`

-   `iaik.`

-   `org.apache.sshd.`

-   `com.jcraft.jsch.`


For more details about the unsupported classes and available alternative classes, see [0003645155](https://me.sap.com/notes/0003645155)



## How to Fix?

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for above design guideline checks, and select *Fix* from the *Actions* column to understand the details and then automatically fix the issue. The incompatibilities \(like few libraries and classes\) for which an automatic fix is not provided, should be removed from the script manually. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Scripts](scripts-fa29f02.md "A Groovy or Java script step can be used in an integration flow for script operations on the message content.")

