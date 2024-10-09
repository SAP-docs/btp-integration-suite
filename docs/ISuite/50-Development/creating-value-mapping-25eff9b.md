<!-- loio25eff9b4884d4f6e859e6ebf898dcb71 -->

# Creating Value Mapping



## Context

You use the value mapping artifact to represent multiple values for a single object. For example, a product in Company A is referred by the last three letters as "IDE". The same product is referred in Company B by product code ''0100IDE". When Company A sends message to Company B, it needs to take care of the difference in the representations of the same product. So, Company A defines an integration flow with a mapping element that contains reference to the value mapping definition. You create such value mapping groups in a *Value Mapping* artifact.



## Procedure

1.  Choose the integration package where you want to add the *Value Mapping* artifact and choose *Edit*.

2.  Choose *Artifacts* \> *Add* \> *Value Mapping*.

3.  If you want to upload a value mapping artifact from your local file system, perform the following substeps:

    1.  Choose *Upload* \> *Browse*.

    2.  Navigate to the location where the artifact file is located and upload it.

    3.  Enter values in mandatory fields, & optional fields if necessary. Choose *OK*.

        You see a message confirming that the value mapping artifact is created successfully.


4.  If you want to create a value mapping artifact, perform the following substeps:

    1.  Enter the *Name* for your value mapping artifact.

    2.  If necessary, enter values in the optional fields and choose *OK*.


    You see a message confirming that the value mapping artifact is created successfully. Configure the value mapping artifact by referring to [Configuring Value Mappings](configuring-value-mappings-6c8847f.md).

5.  If you want to import a value mapping from your Integration Directory in a PI landscape, perform the following substeps:

    > ### Note:  
    > Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

    > ### Note:  
    > The supported service packs for importing a value mapping are SAP Process Orchestration 7.5 SP22 and onwards.

    1.  Choose *Integration Directory*.

        The properties of the ES Repository to which connection is already established by the tenant admin gets auto-populated.

    2.  Choose *Connect*.

        All value mappings from the ES Repository get listed.

    3.  Select a value mapping from the list. You can use the filter to search for a specific value mapping. Choose *OK*.

        Properties like Name, ID, and Description of the value mapping comes up.

    4.  Edit the name and description, if needed. Choose *OK*.

        You see a message confirming that the value mapping artifact is created successfully.


6.  Configure the value mapping artifact by referring to [Configuring Value Mappings](configuring-value-mappings-6c8847f.md).


