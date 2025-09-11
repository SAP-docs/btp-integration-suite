<!-- loio024b8fd70c364979b8ae63ccba3bee3b -->

# Configure Externalized Parameters

Configure the attributes that you've already externalized.



<a name="loio024b8fd70c364979b8ae63ccba3bee3b__prereq_qxj_gcc_r2c"/>

## Prerequisites

-   You have externalized the parameters for an API artifact and have download the .zip file of the API artifact. See [Create New Parameters in Externalization Editor](create-new-parameters-in-externalization-editor-417e4e8.md).



## Procedure

1.  Log on to SAP Integration Suite 

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

    The *Create API* dialog opens.

5.  Select the *Runtime Profile* and choose *Next*. This profile determines the runtime on which you will create and process your API artifact.

6.  Select *Import* from the given options and choose *Next*.

7.  In the *Import API* window *Browse* and upload the required .zip file of the API that you externalized from your local file system and choose *Create*.

    For step-by-step instruction on how to import an API, see [Create an API Artifact by Importing an OpenAPI Specification](create-an-api-artifact-by-importing-an-openapi-specification-fb99a7d.md).

8.  To configure the externalize parameters for a fields/attributes in the policy step of the API artifact, select the API artifact you just created. You'll find the API artifact under the *Artifacts* tab.

9.  Choose the *Configure* option on this page.

    Alternatively, you can also find the *Configure* option when you select an API artifact and choose *Actions*.

10. Choose the *Configure* option on this page to configure only those attributes that you've already externalized.

    > ### Note:  
    > In the *Configure* dialog, the *Type* field defaults to *All Parameters*. To access full configuration options—such as dropdown menus—you need to select the corresponding policies.


