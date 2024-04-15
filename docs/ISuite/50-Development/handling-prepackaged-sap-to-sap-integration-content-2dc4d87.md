<!-- loio2dc4d8736eec4a6089ea81bdfcf311ff -->

# Handling Prepackaged SAP-to-SAP Integration Content

Learn the SAP recommendations for reusing SAP-to-SAP prepackaged content within and across tenants.

If you deploy and process an integration flow from a predefined content package, it's metered. You can edit such prepackaged content or use them as is. For more information on the metering metrics, see SAP Note [2942344](https://launchpad.support.sap.com/#/notes/2942344).



<a name="loio2dc4d8736eec4a6089ea81bdfcf311ff__section_jf2_dgj_gyb"/>

## Prepackaged Content with SAP-to-SAP Metadata

Some prepackaged integration content connects two SAP systems. Such artifacts are marked with an additional metadata value *Integration: SAP-to-SAP*. In the *Artifacts* tab, select any artifact. Under *Actions*, choose *View Metadata*. In the dialog that comes up, if applicable, along with Name, Description, Sender, and Receiver information, you see an additional metadata *Integration: SAP-to-SAP*.

**If you use such prepackaged artifacts without modifications, the messages that are processed are metered but not billed**. If you choose to modify such prepackaged artifacts, the messages that are processed from such artifacts are metered and billed.

There are use cases where you want to reuse such unmodified prepackaged SAP-to-SAP content within and across your tenants. In such scenarios, we recommend you to follow one of the mentioned approaches so that you're not billed for the messages that are processed.



### Reusing SAP-to-SAP Content On Your Tenant

If you've requirements to reuse the same prepackaged artifact exceptionally on your tenant, you can follow one of these approaches:

-   In the *Discover* view, open the package and choose *Copy*. You see an error that states copying isn't possible as the package is already copied to your *Design* workspace.

    Choose *Create Copy* and provide a suffix. The entire package is now copied to your *Design* workspace with the suffix added to the name of the package .

    > ### Remember:  
    > Along with the existing copy, another copy of the package and all its artifacts is created in your *Design* workspace.

-   In the *Design* view, open the already copied package and choose the artifact that you want to reuse. Under *Actions*, choose *Copy*.

    Provide a name and select a package from your *Design* workspace. Choose *Copy*. A new copy of a particular artifact is created in a package of your choice in the *Design* workspace.




### Reusing SAP-to-SAP Content Across Tenants

If you've requirements to reuse the same prepackaged artifact on a different tenant, you can follow one of these approaches:

-   Download the artifact from the source tenant and import the same in the target tenant.

-   Manually export and import the content. See: [Content Transport using Manual Export and Import](content-transport-using-manual-export-and-import-fd23e14.md).

-   Use one of the transport mechanisms and reuse content across multiple tenants. See: [Content Transport](content-transport-e3c79d6.md).


