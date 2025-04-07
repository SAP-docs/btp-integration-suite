<!-- loiob70e7ece2edb46cab447a6bec891fe7e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Deploying an API Artifact

After creating an API artifact, it is necessary to deploy it on the chosen runtime profile in order to make it executable and ready for use.



<a name="loiob70e7ece2edb46cab447a6bec891fe7e__prereq_x3l_jbg_q1c"/>

## Prerequisites

You should have at least one runtime provisioned.



<a name="loiob70e7ece2edb46cab447a6bec891fe7e__steps_sqd_4wk_q1c"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Design* \> *Integrations and APIs*.

3.  Select the *<integration package\>* where you want to create your API artifact.

4.  To expose a service as an API artifact, choose *Edit* and navigate to the *Artifacts* tab. For detailed steps on how to add an API artifact, see [Adding an API Artifact](adding-an-api-artifact-c2fe62c.md).

    If you wish to deploy an API artifact that has already been created, select the *<integration package\>* where you created the API artifact.

5.  Choose the <span class="SAP-icons-V5"></span> Action icon next to the required API artifact and then select the *Deploy* from the options.

    > ### Note:  
    > Alternatively, you can deploy an API artifact from its details page. First, select the *<integration package\>* in which you created the API artifact. Then, select the API to open its *Details* page. On the API details page, you will find the option to deploy the API. Simply select *Deploy* to proceed with the deployment.

6.  On the *Confirmation* dialog, the runtime you chose while creating the API artifact will be selected by default. However, you can choose another valid runtime profile from the dropdown menu while deploying the artifact.

    > ### Note:  
    > The associated virtual host URL will be automatically updated when you select the runtime profile of your choice. Additionally, your API URL will be updated accordingly.




<a name="loiob70e7ece2edb46cab447a6bec891fe7e__result_l2r_tvf_5pb"/>

## Results

Once an API artifact is deployed, it becomes available for consumption.



<a name="loiob70e7ece2edb46cab447a6bec891fe7e__postreq_f3l_hpl_q1c"/>

## Next Steps

After deploying the API artifact, you can check the runtime logs and the status of the API artifact. For more information, see [Monitor APIs](monitor-apis-399b6c6.md).

**Related Information**  


[Adding an API Artifact](adding-an-api-artifact-c2fe62c.md "Add an API artifact to an package.")

[Copying an API Artifact](copying-an-api-artifact-820c9e8.md "You may want to create a copy of an existing API artifact with all its configurations and policies intact. This can be useful when you want to create a similar API but with some modifications or variations. The copy feature allows you to quickly duplicate the API artifact and make the necessary changes without starting from scratch.You can create a duplicate of an API artifact by copying it within the same package or in a different integration package within the same SAP Integration Suite subscription.")

[Policy Definition and Types of Policies](policy-definition-and-types-of-policies-c744df5.md "You can define the behavior of an API by using policy steps.")

[Request Reply Step for API Artifact](request-reply-step-for-api-artifact-a0b3712.md "You can use this step to call an external receiver system in a synchronous step and get back a response.")

