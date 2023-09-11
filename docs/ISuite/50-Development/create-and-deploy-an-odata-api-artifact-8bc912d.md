<!-- loio8bc912d42c0a4cb284ecc08b4ea4e1b9 -->

# Create and Deploy an OData API Artifact

Use this procedure to create and deploy an OData API artifact.



<a name="loio8bc912d42c0a4cb284ecc08b4ea4e1b9__context_mn5_tdk_f4b"/>

## Context

An OData API artifact creates an OData API-based integration scenario with OData V2 sender adapter.

<a name="task_ytz_gq4_gpb"/>

<!-- task\_ytz\_gq4\_gpb -->

## Create an OData API Artifact



<a name="task_ytz_gq4_gpb__steps_vrz_3q4_gpb"/>

## Procedure

1.  Choose *Design* \> *Integrations*.

2.  Choose *Create*.

3.  Enter the required data for the integration package. See [Creating an Integration Package](creating-an-integration-package-9126d79.md).

4.  In the *Artifacts* tab, choose *Add* \> *OData API*.

5.  In the *Add OData API* dialog box, choose *Create Using Template*.

    By choosing *Create Using Wizard* or *Upload*, you start creating an OData API project. See [Developing an OData API Project](developing-an-odata-api-project-d961654.md).

6.  Enter the name and description for the OData API.

    ID and Runtime Profile are uneditable fields.

7.  Choose *OK* to create the artifact.

    The artifact is added to the integration package.

8.  Save the integration package.

9.  Choose the artifact to open it.

    The integration flow editor opens the default integration flow model.

10. Choose *Edit*.

    A palette appears on top of the integration flow model that provides access to all integration flow steps that you can add to the model. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

11. Choose *Save*.

12. Choose *Deploy* when your artifact is ready for execution.

    > ### Note:  
    > The URL of the OData API endpoint is derived from the name of the OData API artifact.




<a name="task_ytz_gq4_gpb__postreq_izn_tzq_f4b"/>

## Next Steps

You can check the status of all your integration artifacts in the *Monitor* view. By default, API-based artifacts don't appear in the *Monitor*. Perform the steps that follow to view the deployed artifact.

<a name="task_kgx_kq4_gpb"/>

<!-- task\_kgx\_kq4\_gpb -->

## View the deployed OData API Artifact



<a name="task_kgx_kq4_gpb__steps_jv3_4q4_gpb"/>

## Procedure

1.  Choose *Monitor* \> *Integrations*.

2.  Under *Manage Integration Content*, add a new tile.

3.  In the *Tile Settings* dialog, do the following:

    1.  Select *All* from the *Status* list.

    2.  Select OData API from the *Type* list.

    3.  Choose *OK* to create a tile.


4.  Open the tile to view your artifact and its status.




<a name="task_kgx_kq4_gpb__postreq_jcn_xq4_gpb"/>

## Next Steps

Repeat the same process to create a tile under *Monitor Message Processing* to view the status of your processed messages.

