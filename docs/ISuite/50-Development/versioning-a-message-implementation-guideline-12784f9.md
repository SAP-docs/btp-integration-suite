<!-- loio12784f9d34444f929f9ea72ef38f7e02 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Versioning a Message Implementation Guideline

This chapter covers the lifecycle of a message implementation guideline, the purpose of each status that a MIG goes through and the procedure to activate the MIG.

There are 3 different status types for an MIG:

-   Draft

-   Active
-   Deprecated

When you create a new message implementation guideline, the newly created MIG has the *Status* field set to *Draft* and the *Version* set as *1.0*. You can now modify this new version of MIG according to your business requirements. You can also copy an existing message implementation guideline. The copied MIG will have the *Version* set as *1.0* and also the term *Copy* suffixed to its name. You can later edit the name of the MIG.

When you activate a message implementation guideline, the *Status* of the MIG is set to *Active*. Once activated, this version of the MIG will be finalised and it cannot be edited thereafter. But you can continue to export documentation and runtime artifacts from the MIG. Activating a MIG will also anonymously push the message implementation guideline into the knowledge graph to contribute and improve the proposal service.

> ### Note:  
> It is always recommended to activate a MIG to use it productively. By doing so,
> 
> -   You protect the MIG against any unwanted changes
> 
> -   Any new requirements for the MIG can be maintained in a new *Draft* version of the MIG without changing the active MIG version currently in use.

If you want to create the next draft version of an active MIG, open the active MIG version and choose *Edit*. You can also choose *Edit* from the action <span class="SAP-icons-V5"></span> button from the MIG overview. This will prompt you to confirm creating a draft version. Choose *OK*. Now the next version of the MIG gets created with the *Draft* status. For example, if the active version of the MIG is 2.0, then the new draft MIG will have the version set as 3.0

After the successful activation of a MIG, the previous active version of the MIG gets deprecated and its *Status* field is set to *Deprecated*.

> ### Note:  
> There can be only one active and draft version of a particular MIG.

Follow the procedure below to activate a message implementation guideline.



<a name="loio12784f9d34444f929f9ea72ef38f7e02__section_d52_2t3_spb"/>

## Procedure

1.  Navigate to *Message Implementation Guideline* <span class="SAP-icons-V5"></span> from the left pane.

2.  Choose the MIG that you want to activate.
3.  Choose *Activate* to mark a version of the MIG as a main version.

    > ### Note:  
    > Any subsequent edit operations on the same MIG would be saved as a different version.
    > 
    > After successful activation of MIG, a confirmation box appears with the following information
    > 
    > -   List of values that get published into the knowledge graph
    > 
    > -   List of values that will not get published into the knowledge graph


If the message implementation guideline is based on a custom message, then the custom message should be activated first before activating that MIG. To do so, follow the procedure below.



<a name="loio12784f9d34444f929f9ea72ef38f7e02__section_gdt_xx3_spb"/>

## Activating a Custom Message

1.  In your MIG, choose <span class="SAP-icons-V5"></span> and select *Activate Message*.

2.  A message is displayed to show the status of the activation.

    You can also view the status after activation under the *Message Status* field in the *Overview* tab of the MIG.

    > ### Note:  
    > Once activated, the version of the activated custom message cannot be deleted.

3.  You can now activate your MIG after activating the custom message the MIG is based on.

