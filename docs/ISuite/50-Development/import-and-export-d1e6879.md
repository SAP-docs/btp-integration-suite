<!-- loiod1e68792493540b2892119e80a32e8ae -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Import and Export

SAP Integration Suite allows you to export Message Implementation Guidelines \(MIG\), Mapping Guidelines \(MAG\), documentation and runtime artifacts. The application also allows you to import MIGs and MAGs.



<a name="loiod1e68792493540b2892119e80a32e8ae__section_exq_x2b_stb"/>

## Export and Import MIG/MAG

There can be situations where you want to bring few of your Message Implementation Guidelines and Mapping Guidelines from one tenant to another tenant or you might have to migrate all of your MIGs and MAGs when you are shifting to a new tenant. This feature helps you achieve a seamless migration of your MIGs and MAGs.

There are few things to be considered when using these two features.

-   While exporting and importing MIGs/MAGs, their dependent resources such as the custom message for a MIG \(if the MIG is created based on a custom message\), the dependent MIGs for a MAG and the Global Code Value mapping for a MAG, Pretransformation of a MAG are included as well.
-   The following overwrite scenarios are supported:

    -   *Draft to Draft*: If you have made any changes to a MIG/MAG that is in draft state in one tenant and need to import that to another tenant that contains a previous state of that MIG/MAG, you can overwrite that MIG/MAG using the *Import* option. You can also overwrite a current draft state of a MIG/MAG with its previous state. The import dialog would display a warning stating that there will be a potential data loss with the overwrite

    -   *Draft to Active*: If you have draft version of a MIG/MAG in one tenant and you have an active version of that MIG/MAG in another tenant, you can overwrite the draft MIG/MAG with the active MIG/MAG.

        > ### Note:  
        > For custom messages, the application only supports overwriting
        > 
        > -   Draft to Active
        > 
        > -   Draft to Draft

    -   *Active to Deprecated*: You can overwrite a active MIG/MAG with its deprecated version.
    -   *Draft to Deprecated*: You can also overwrite a draft MIG/MAG with its deprecated version. But it is recommended to import the active version before importing the deprecated version to maintain the overall consistency.
    -   *Active to Active*: You can now overwrite an active MIG/MAG again with its active version.
    -   *Deprecated to Deprecated*: You can overwrite a deprecated MIG/MAG with its deprecated version again. Say for example, you have a deprecated MIG of version 1.0 in the tenant and you have manually changed the status of that active 1.0 version of the MIG to Deprecated. Now this local file will have a different timestamp and you can overwrite the existing MIG with this updated MIG.

    > ### Note:  
    > The following overwrite scenarios are not supported:
    > 
    > -   Active to Draft
    > 
    > -   Deprecated to Draft
    > -   Deprecated to Active

-   If you are migrating all of your MIGs/MAGs from one tenant to another tenant, it is recommended to adhere to the following steps to avoid any complications:

    -   Stop editing the MIGs/MAGs in the old tenant

    -   Complete the migration of all MIGs/MAGs to the new tenant
    -   Continue editing the MIGs/MAGs in the new tenant once the import is done

    > ### Note:  
    > You can import new versions of MIG/MAG into the same tenant where you exported the previous versions from. You can also export a MIG/MAG, make some changes and import to overwrite the existing MIG/MAG in the same tenant.

-   • Export/Import feature is optimized for:

    -   Linear transport paths such as exporting from Tenant A to Tenant B and then from Tenant B to Tenant C \(Tenant A :arrow_right: Tenant B :arrow_right: Tenant C\).

    -   Natural sequence of import where if ZIP1 was exported before ZIP2 from Tenant A, then ZIP1 shall be imported before ZIP2 into Tenant B.

    Import might not fully work for other situations such as:

    -   Cyclic transport paths where for example, you export from Tenant A to Tenant B to Tenant C and then again from Tenant C to Tenant A \(Tenant A :arrow_right: Tenant B :arrow_right: Tenant C :arrow_right: Tenant A\)

    -   Mixed sequence of import such as importing ZIP1 after ZIP2 into Tenant B.


Refer the chapters [Exporting MIG/MAG](exporting-mig-mag-c8bba26.md) and [Importing MIG/MAG](importing-mig-mag-7139aad.md) to learn how to import and export MIGs/MAGs.



<a name="loiod1e68792493540b2892119e80a32e8ae__section_dyn_3kp_stb"/>

## Exporting Documentation

You can export your MIG or MAG in the following supported documentation format:

-   PDF

-   RTF
-   Excel

You can use the document file as a reference to implement the messages and mappings in the integration solution also as reference documentation for bookkeeping purposes.

See [Exporting Documentation](exporting-documentation-f7dbd2d.md) to learn how to export documentation.



<a name="loiod1e68792493540b2892119e80a32e8ae__section_d25_kpp_stb"/>

## Export Runtime Artifacts

Once you have created the Message Implementation Guidelines \(MIG\) and Mapping Guidelines \(MAG\), the next step is to use these artifacts in the integration solution to enable integrations with your business partner/s. SAP Integration Suite helps you export these runtime artifacts by automatically generating a number of schemes, scripts, and examples from a mapping guideline. This automatic generation is a particularly enormous time saver, because without the application, all these schemes, scripts, or payloads must be created separately and manually.

You can then import these runtime artifacts in either of these integration solutions and use them to implement your A2A/B2B integration scenario.

See [Exporting Runtime Artifacts](exporting-runtime-artifacts-5ab4cfe.md) to know how to export the runtime artifacts.



