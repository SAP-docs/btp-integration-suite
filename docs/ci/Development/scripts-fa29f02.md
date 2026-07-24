<!-- loiofa29f02c19e744528b50fd721959f337 -->

# Scripts

A Groovy or Java script step can be used in an integration flow for script operations on the message content.

As an integration developer, you often use custom logic and dependencies to extend functionality. While this offers flexibility, inconsistent practices and reliance on internal or unsupported features can create hidden dependencies that make systems fragile. Even minor software changes may cause failures, outages, or complex troubleshooting during major runtime version upgrades.

These upgrade readiness guidelines for script step promotes clean, consistent, and upgrade-ready design to ensure your integrations remain stable, maintainable, and ready for future enhancements.



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


For more details about the unsupported classes and suggested standard classes for these unsupported classes, see [0003645155](https://me.sap.com/notes/0003645155) 



<a name="loiofa29f02c19e744528b50fd721959f337__section_fkb_qwl_zfc"/>

## Include only used import statements

Import statements are used to consume Groovy and Java native APIs. Unused import statements in scripts should be avoided as they can cause unnecessary complications during maintenance, software or runtime upgrades.

Even if an import is not actively used in the script, the runtime may attempt to resolve the referenced library or class. If the library is deprecated, removed, or modified in a future runtime version upgrade, this can result in compilation errors or runtime failures.

Additionally, as a best practice unused imports shouldn't be used as they create visual clutter and may mislead into thinking certain dependencies are required.



<a name="loiofa29f02c19e744528b50fd721959f337__section_fcm_tdp_hhc"/>

## Access resources appropriately

When writing scripts in an integration flow, always reference design‑time resources \(such as XML, XSD, WSDL, or script files\) using their relative root path. This ensures that your scripts remain future‑ready and continue to work reliably as the underlying packaging structure of the integration flow evolves.

You should access the resources from their relative root path, not from folders like `src/main/resources`. For example, instead of `src/main/resources/xsd/customer.xsd` reference the resource as `/xsd/customer.xsd`.

**Benefits:**

-   Your scripts become future‑proof, ensuring optimal performance while still having full access to the assets required at runtime.
-   Resource loading becomes consistent and predictable across environments.
-   Integration flows remain simpler to maintain, since scripts always refer to a clear, stable location.



## Ensure valid syntax

When writing JavaScript within an integration flow, always ensure that the script follows correct and valid syntax. Proper syntax is essential for successful validation and enables further guideline checks to be executed without interruptions.

Scripts that contain syntax errors or invalid constructs cannot be properly validated. This prevents additional checks such as identifying unsupported classes from being performed and may lead to issues during runtime.

Avoid using incomplete statements, incorrect declarations, or unsupported language constructs. For more information, see KBA [3757007](https://me.sap.com/notes/3757007)



### Benefits

-   Scripts can be validated successfully, enabling subsequent quality and compliance checks.
-   Runtime failures are minimized, improving overall reliability and stability.
-   Integration flows become easier to maintain and more future‑ready, as validated scripts are less likely to break with platform updates.



## Use import statements supported by the script runtime

This design guideline ensures that groovy scripts use import statements compatible with its runtime version. Incompatible import statements can lead to compilation failures and upgrade readiness issues when scripts are executed on the runtimes.

The guideline identifies imports that are not supported by the target runtime and recommends the appropriate runtime-compatible alternatives.

This guideline scans version 2 of the script only. See  <?sap-ot O2O class="- topic/xref " href="917e014b47094620b2616c125e1a86f3.xml" text="" desc="" xtrc="xref:2" xtrf="file:/home/builder/src/dita-all/zpk1713331951414/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/fa29f02c19e744528b50fd721959f337.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

> ### Example:  

The import `import groovy.util.XmlSlurper`is incompatible with the Groovy 4 runtime. It should be replaced with `import groovy.xml.XmlSlurper`.



## Restrict usage to supported frameworks and libraries

This guideline helps identify the use of internal, unsupported, or restricted classes and libraries in groovy scripts. Using unsupported frameworks can result in runtime failures, upgrade incompatibilities, maintenance challenges, and unexpected behavior after software updates.

No automatic fix is provided for this; you must manually replace or remove unsupported implementations.

> ### Note:  
> The guideline scans both versions of groovy scripts version 1 and version 2. See  <?sap-ot O2O class="- topic/xref " href="917e014b47094620b2616c125e1a86f3.xml" text="" desc="" xtrc="xref:3" xtrf="file:/home/builder/src/dita-all/zpk1713331951414/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/fa29f02c19e744528b50fd721959f337.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

To ensure long-term stability and upgrade readiness:

-   **Use Supported Libraries**: Always use libraries and APIs provided or approved by SAP. This helps maintain compatibility across upgrades and reduces dependency-related issues.

-   **Bundle External Libraries Carefully**: If a required library is not available in SAP Integration Suite, it can be bundled with the integration flow. However, additional libraries may increase artifact size and startup time.

-   **Avoid Restricted System Access**: Do not directly access the operating system, file system, network resources, or runtime environment. Use SAP-provided APIs for secure and supported operations.

-   **Avoid Unsupported System Classes**: Using internal or unsupported classes can lead to runtime instability and upgrade issues. Prefer supported SAP APIs and extensions.


The guideline detects usage of unsupported class groups, including:

-   OSGi \(`org.osgi.framework.*`, `org.osgi.service.event.*`\)

-   Quartz \(`org.quartz.*`\)

-   Spring \(`org.springframework*`\)

-   HikariCP \(`com.zaxxer.hikari.*`\)

-   Groovy SQL \(`groovy.sql.*`\)

-   Saxon \(`net.sf.saxon.*`\)

-   Selected Apache Camel internal classes \(`org.apache.camel.*`\)




## How to Fix?

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for above design guideline checks, and select *Fix* from the *Actions* column to understand the details and then automatically fix the issue. The incompatibilities \(like few libraries and classes\) for which an automatic Fix is not provided, should be removed from the script manually. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Use Scripting Appropriately](use-scripting-appropriately-d4dc13c.md "You can use the script step to apply script operations on the message content.")

[Define a Local Script Step](define-a-local-script-step-03b32eb.md "Learn how to use a script step that’s specific to an integration artifact to create custom scripts (JavaScript or Groovy Script).")

