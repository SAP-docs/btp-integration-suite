<!-- loiobbba19d1468d4353ba309eb8a5b4d886 -->

# Use Recommended Libraries and Classes

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

-   The guideline detects usage of unsupported class groups, including:

    -   OSGi \(`org.osgi.framework.*`, `org.osgi.service.event.*`\)

    -   Quartz \(`org.quartz.*`\)

    -   Spring \(`org.springframework*`\)

    -   HikariCP \(`com.zaxxer.hikari.*`\)

    -   Groovy SQL \(`groovy.sql.*`\)

    -   Saxon \(`net.sf.saxon.*`\)

    -   Selected Apache Camel internal classes \(`org.apache.camel.*`\)



For more details about the unsupported classes and available alternative classes, see [0003645155](https://me.sap.com/notes/0003645155)



## How to Fix?

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for above design guideline checks, and select *Fix* from the *Actions* column to understand the details and then automatically fix the issue. The incompatibilities \(like few libraries and classes\) for which an automatic fix is not provided, should be removed from the script manually. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Scripts](scripts-fa29f02.md "A Groovy or Java script step can be used in an integration flow for script operations on the message content.")

