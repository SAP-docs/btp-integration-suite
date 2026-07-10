<!-- loio1a439afed5f44c2b8b493112f44eb634 -->

# Create and Deploy a SOAP API Artifact

Use this procedure to create and deploy a SOAP API artifact.



<a name="loio1a439afed5f44c2b8b493112f44eb634__prereq_fxs_b33_r1c"/>

## Prerequisites

[Creating an Integration Package](creating-an-integration-package-9126d79.md)



<a name="loio1a439afed5f44c2b8b493112f44eb634__context_mn5_tdk_f4b"/>

## Context

A SOAP API artifact creates a SOAP API-based integration scenario with the SOAP 1.x sender adapter.

<a name="task_c2h_xgc_hpb"/>

<!-- task\_c2h\_xgc\_hpb -->

## Create a SOAP API Artifact



<a name="task_c2h_xgc_hpb__steps_qxn_mvw_b4b"/>

## Procedure

1.  Choose *Design* \> *Integrations and APIs* to view the list of integration packages.

2.  Select the integration package where you want to create an SOAP API artifact and choose *Edit*.

3.  In the *Artifacts* tab, choose *Add* \> *API*.

    The *Create API* wizard opens.

4.  Select *Cloud Integration* from the list of available runtime profiles. For more information, see [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md). Choose *Next*.

5.  Choose *SOAP API* \> *Next*.

6.  In the *Select A Method* tab, choose one of the following options:

    -   *Create* – to create a SOAP API artifact.

    -   *Upload* – to create a new SOAP API artifact by uploading the necessary resources from your local file directory.


7.  Enter the SOAP API details as listed in the following table:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SOAP API \(only for upload\)
    
    </td>
    <td valign="top">
    
    Upload a ZIP file containing the SOAP API resources.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Name of the API.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ID
    
    </td>
    <td valign="top">
    
    Uniquely identifies the artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Description of the API and its purpose.
    
    </td>
    </tr>
    </table>
    
    Runtime Profile is an uneditable field.

8.  Choose *Create*.

    The artifact is added to the integration package and the API artifact opens up in the editor.

9.  Choose *Edit*.

    A palette appears on top of the integration flow model that provides access to all integration flow steps that you can add to the model. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

10. Make your changes and choose *Save*.

11. Choose *Deploy* when your artifact is ready for execution.




<a name="task_c2h_xgc_hpb__postreq_izn_tzq_f4b"/>

## Next Steps

You can check the status of all your integration artifacts in the *Monitor* view. By default, API-based artifacts don't appear in the *Monitor*. Perform the steps that follow to view the deployed artifact.

<a name="task_bp3_dhc_hpb"/>

<!-- task\_bp3\_dhc\_hpb -->

## View the deployed SOAP API Artifact



<a name="task_bp3_dhc_hpb__steps_v4n_2hc_hpb"/>

## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.

2.  Under *Manage Integration Content*, add a new tile.

3.  In the *Tile Settings* dialog, do the following:

    1.  Select *All* from the *Status* list.

    2.  Select SOAP API from the *Type* list.

    3.  Choose *OK* to create a tile.


4.  Open the tile to view your artifact and its status.




<a name="task_bp3_dhc_hpb__postreq_jcn_xq4_gpb"/>

## Next Steps

Repeat the same process to create a tile under *Monitor Message Processing* to view the status of your processed messages.

