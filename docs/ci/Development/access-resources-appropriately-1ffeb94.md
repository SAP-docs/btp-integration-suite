<!-- loio1ffeb948220f41808484634ed039f25e -->

# Access Resources Appropriately

When writing scripts in an integration flow, always reference design‑time resources \(such as XML, XSD, WSDL, or script files\) using their relative root path. This ensures that your scripts remain future‑ready and continue to work reliably as the underlying packaging structure of the integration flow evolves.

You should access the resources from their relative root path, not from folders like `src/main/resources`. For example, instead of `src/main/resources/xsd/customer.xsd` reference the resource as `/xsd/customer.xsd`.

**Benefits:**

-   Your scripts become future‑proof, ensuring optimal performance while still having full access to the assets required at runtime.
-   Resource loading becomes consistent and predictable across environments.
-   Integration flows remain simpler to maintain, since scripts always refer to a clear, stable location.



For more details about the unsupported classes and available alternative classes, see [0003645155](https://me.sap.com/notes/0003645155)



## How to Fix?

**How to Fix?**: In the script editor’s *Problems* view, navigate to the *Upgrade Readiness Check* tab, locate the problem description for above design guideline checks, and select *Fix* from the *Actions* column to understand the details and then automatically fix the issue. The incompatibilities \(like few libraries and classes\) for which an automatic fix is not provided, should be removed from the script manually. See [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md)

**Related Information**  


[Scripts](scripts-fa29f02.md "A Groovy or Java script step can be used in an integration flow for script operations on the message content.")

