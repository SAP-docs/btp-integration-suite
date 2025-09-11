<!-- loio820c9e8219ca4ab88c7a80950c6fe360 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Copy an API Artifact

You may want to create a copy of an existing API artifact with all its configurations and policies intact. This can be useful when you want to create a similar API artifact but with some modifications or variations.



<a name="loio820c9e8219ca4ab88c7a80950c6fe360__prereq_rnp_v53_b2b"/>

## Prerequisites

You are assigned the *PI\_Integration\_Developer* role.



<a name="loio820c9e8219ca4ab88c7a80950c6fe360__context_snp_v53_b2b"/>

## Context

The copy feature allows you to quickly duplicate the API artifact and make the necessary changes without starting from scratch. You can create a duplicate of an API artifact by copying it within the same package or to a different integration package. Please ensure that you explicitly update the base path of the copied API; otherwise, the deployment will fail.

API artifacts often have multiple policies, such as authentication, rate limiting, caching, and transformation policies. When you copy an API artifact, all the policies are copied, allowing you to maintain consistency across multiple API artifacts. This saves time and effort in configuring policies for each API individually.

To copy an API artifact, proceed as follows:



<a name="loio820c9e8219ca4ab88c7a80950c6fe360__steps_tnp_v53_b2b"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Design* \> *Integrations and APIs*.

3.  Select the *<integration package\>* from where you want to copy the API artifact.

4.  On the *<integration package\>* details page, choose *Artifacts*.

5.  Choose the <span class="SAP-icons-V5"></span> Action icon against the required API artifact and then select the *Copy* option.

6.  In the *Copy <API Artifact\>* dialog box, the details for each attribute is pre filled.

    By default, "\_copy" will get appended to the *Name*. However, you have the option to change the *Name* and provide a unique name for the API artifact you are copying. When you change the *Name*, the *ID* will be automatically generated.

    > ### Note:  
    > If you try to copy the API artifact with the same name, the copy action will fail and display the following error: "The <API artifact\> could not be copied because an API artifact with the same ID already exists. Please edit the name to modify the ID and try again.".
    > 
    > Whether you're copying an API artifact within the same integration package or a different package, you must provide a unique name for the copied API artifact.

    ![](images/Copy_API_Artifact_c29a3b1.png)

    > ### Note:  
    > The name should start with an alphabet or an underscore \(\_\). It can also include numbers, spaces, periods, or hyphens \(-\), but it must not end with a period \(.\)

7.  To copy this API artifact to an Integration package of your choice, choose *Select*.

    In the *Package Selection* dialog, search for and select the desired package.

8.  Choose *Copy* to initiate the copying process.




<a name="loio820c9e8219ca4ab88c7a80950c6fe360__result_av2_h23_31c"/>

## Results

After the copying process is finished, you will receive a success message instructing you to go to the package where the copied API artifact has been added.

You can access the API artifact in view mode, allowing you to download, deploy, and copy the API artifact. If you want to delete the API artifact, simply switch to edit mode by selecting the *Edit* option.

**Related Information**  


[Create an API Artifact](create-an-api-artifact-c2fe62c.md "Create an API artifact to securely expose backend services, apply consistent governance by adding security and traffic management policies, and gain better visibility and control over how your APIs are accessed and used.")

[Add Resources to an API Artifact](add-resources-to-an-api-artifact-b5d0e4c.md "Add a resource to refer to individual endpoints or services.")

[Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md "You can define the behavior of an API by using policies.")

[Deploy an API Artifact](deploy-an-api-artifact-b70e7ec.md "After creating an API artifact, it is necessary to deploy it on the chosen runtime in order to make it executable and ready for use.")

[Externalize Parameter for API Artifact](externalize-parameter-for-api-artifact-ce0a468.md "You can use the externalization feature to define API policies and integration flows that can retrieve externalized configuration values during runtime. These parameters can be utilized later without modifying the standard API artifact.")

