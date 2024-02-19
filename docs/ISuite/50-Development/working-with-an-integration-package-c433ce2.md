<!-- loioc433ce2a2bff4d9a9b69257583d1b2fe -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with an Integration Package

Perform various tasks with the artifacts and the integration package.



## Procedure

1.  Choose *Design* \> *Integrations and APIs* to view the list of integration packages.

2.  If you want to view the details of an integration package, choose *<integration package name\>*.

3.  Navigate to the *Artifacts* tab, to work with the available artifacts in the package.

    1.  Choose <span class="SAP-icons-V5"></span>** \> *View metadata* to view the metadata of the artifact.

    2.  Choose <span class="SAP-icons-V5"></span>** \> *Deploy* to deploy the artifact.

        You can only deploy data flows, integration flows, and value mappings. You can deploy multiple value mappings at a time.

    3.  Choose <span class="SAP-icons-V5"></span>** \> *Configure* to configure the artifact.

        You can configure only integration flows. For more information, see [Configure Externalized Parameters of an Integration Flow](configure-externalized-parameters-of-an-integration-flow-462a478.md).

    4.  Choose <span class="SAP-icons-V5"></span>** \> *Download* to download an artifact. The download feature allows users to download the integration flow artifact with two options:

        -   **Default Values Only:** Downloads the integration flow with default values only.

            > ### Note:  
            > When the downloaded integration flow imported into the system with default values, these values are seen to the user under externalized parameter view.

        -   **Merged Configured and Default Values:** Downloads the integration flow with values that consists of configured and default values. This option would replace the default value with the configured value and accept it as a new default value.

            > ### Note:  
            > When you import the integration flow in the tenant, the configured values become the default value. For more information, see [Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md)


        You can only download integration flows, files, and value mappings. Your local file system stores the downloaded artifacts with name as <artifact name\>.zip file. If you want to use the artifact in Eclipse, you need to import it in eclipse after extracting it from the zip file.



