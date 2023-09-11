<!-- loio585639c97b3e4e5b83401f12bee9d5fe -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Unused Bindings



## Context

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

You are editing an OData API artifact and you have bound a function import or operations of an entity set to a data source. At this point, let us assume you changed the name of the function import or entity set, or even deleted it in the OData Model Editor. The binding associated with the renamed or deleted entity set or function import is now unused.

The unused bindings appear in a separate table on the Service Designer page. You cannot deploy the OData API unless you update the unused bindings.

Cloud Integration Web application helps you manage unused bindings by providing you with the following options:

<a name="task_fs2_pd4_pv"/>

<!-- task\_fs2\_pd4\_pv -->

## Reconfigure Binding



## Context

You can use this procedure to reconfigure the binding from the earlier entity set or function import to one in the updated OData model.



<a name="task_fs2_pd4_pv__steps_o1h_rd4_pv"/>

## Procedure

1.  Choose *Bind* \(:link:\) for the entity set or function import associated with the unused binding. The *Reconfigure Binding* dialog box appears.

2.  Select the entity set or function import in the updated OData model to which the unused binding needs to be associated.

3.  Choose *OK*. The selected entity or function import in the updated OData model is now associated with the binding. The *Unused Bindings* table disappears if there are no other unused bindings.

    SAP Cloud Integration updates the sender channel with the new binding information. However, you have to update other integration flow components that references the earlier entity set or function import, such as mapping and scripts.

4.  Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


<a name="task_nbp_xc4_pv"/>

<!-- task\_nbp\_xc4\_pv -->

## Delete Binding



## Context

You can use this procedure to delete the unused binding so that it is no longer associated with any entity set or function import in the OData model.



<a name="task_nbp_xc4_pv__steps_arr_dd4_pv"/>

## Procedure

1.  Choose *Delete Binding* \(:wastebasket:\) for the associated entity set or function import.

2.  Confirm the deletion. The *Unused Bindings* table disappears if there are no other unused bindings.

3.  Choose *Save* to save your changes to the OData API artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


