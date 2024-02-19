<!-- loio155164dc8f074ea2a47bd3dba4bf8544 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Editing an Integration Package

Edit your integration package to revise the header and overview sections, add or remove content to the artifacts, and delete the package.



## Procedure

1.  Choose *Design* \> *Integrations and APIs* to view the list of integration packages.

2.  Select the required integration package.

3.  In the integration package editor, choose *Edit*.

    You can edit the existing information in the following tabs:

    -   Header

    -   Overview

    -   Artifacts

    -   Documents

    -   Tags


4.  In the *Header* tab, you can maintain the name of the package, a short description, a version, and the vendor of the package.

    All this data is displayed on top of the integration package. Furthermore, in the list of integration packages within your design workspace, the name, the short description, and the version are displayed.

    > ### Note:  
    > Although the technical name of the integration package is displayed in the *Header* tab, you can't change it. The technical name can only be defined either when creating a new package or when copying it from the *Discover* area.

5.  In the *Overview* tab, you can maintain a more detailed description of your integration package.

    You can also add hyperlinks.

    Furthermore, you've the option to upload a package image. The image is placed on top of the overview page.

6.  In the *Artifacts* tab, choose <span class="SAP-icons-V5"></span>.

    You get the following functions. The list of functions varies for different artifact types.

    -   Delete

    -   Copy

    -   View metadata

    -   Download

    -   Configure \(only for integration flows\)

    -   Deploy \(only for data flows and integration flows\)


7.  To edit the metadata of an artifact, perform the following steps:

    1.  Choose *View metadata*.

        The *<Artifact Type\> Details* dialog box comes up with the metadata of the artifact. For certain prepackaged, standard SAP artifacts you see an additional metadata *Integration: SAP-to-SAP*. This metadata identifies the standard SAP integration artifacts that connect two SAP systems.

    2.  In the *<Artifact Type\> Details* dialog box, choose *Edit*.

        > ### Note:  
        > The name of integration flow must begin with an underscore '\_' or alphabets. It can contain numbers '0–9', space ' ', dot '.', and hyphen '-'.

    3.  Choose *Save* to keep the changes.

    4.  Choose *Save as version* to retain a copy of the current artifact. For more information, see [Versioning of Artifacts](versioning-of-artifacts-cb536a3.md).

        You can view the version history of an artifact by choosing the current version mentioned along with it. You can save versions of a single or multiple artifacts, or an integration package. You can also view the list of existing versions of the required artifacts or integration packages. You can choose to make an existing version as the latest one with or without saving a draft of it.

    5.  Choose *Cancel* to revert the changes.


8.  In the *Documents* tab, you can upload files, such as configuration guides, and add URLs.

9.  In the *Tags* tab, you can maintain standard tags such as Product, Country/Region, Lines of Business and Industry.

    Furthermore, you can add custom tags to identify and track your packages based on your custom-defined attributes. For more information, see [Creating Custom Tags](IntegrationSettings/creating-custom-tags-71c0448.md).

10. Choose *Save* to keep the changes made to the integration package.

11. Choose *Cancel* to discard the changes.

12. Choose *Delete Package* to permanently delete the integration package.

    Provide your consent to delete the package.

    > ### Remember:  
    > You can’t recover the package and its content after you delete them.


