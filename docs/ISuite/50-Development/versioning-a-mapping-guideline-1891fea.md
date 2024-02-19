<!-- loio1891fea318aa41bfa19b00b365f7e4d9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Versioning a Mapping Guideline

This chapter shows you how to activate a mapping guideline

Once you have edited the mapping details in an MAG that suits your scenario, you can activate the mapping guideline for using it productively. There are 3 different types of status set for an MAG and each one of them is defined below:

-   *Draft*: When you create a new mapping guideline, the newly created MAG has the *Status* field set to *Draft* and the *Version* set as *1.0*. You can now modify this new version of MAG according to your business requirements.

    > ### Note:  
    > You can also copy an existing mapping guideline. The copied MAG will have the *Version* set as *1.0* and also the term *Copy* suffixed to its name. You can later edit the name of the MAG.

-   *Active*: After activating a mapping guideline, the *Status* of the MAG is set to *Active*. Once activated, this version of the MAG will be finalised and it cannot be edited thereafter. But you can continue to export documentation and runtime artifacts from the MAG.

    > ### Note:  
    > Activating a MAG will also anonymously push the mapping guideline into the knowledge graph to contribute and improve the proposal service.
    > 
    > It is always recommended to activate a MAG to use it productively. By doing so,
    > 
    > -   You protect the MAG against any unwanted changes
    > 
    > -   Any new requirements for the MAG can be maintained in a new *Draft* version of the MAG without changing the active MAG version currently in use.

    If you want to create the next draft version of an active MAG, open the active MAG version and choose *Edit*. You can also choose *Edit* from the action <span class="SAP-icons-V5"></span> button of the MAG overview. This will prompt you to confirm creating a draft version. Choose *OK*. Now the next version of the MAG gets created with the *Draft* status. For example, if the active version of the MAG is 2.0, then the new draft MAG will have the version set as 3.0

-   *Deprecated*: After activating a MAG, the previous active version of the MAG gets deprecated and its *Status* field is set to *Deprecated*.

    > ### Note:  
    > There can be only one active and draft version of a particular MAG.




<a name="loio1891fea318aa41bfa19b00b365f7e4d9__section_qdw_ssc_2qb"/>

## Procedure

1.  Open your mapping guideline and choose *Edit*.

    Before activating the MAG, ensure that you have activated the source and target message implementation guidelines used in this MAG. You can navigate to those MIGs using the links provided under the*Source and Target MIGs* section in the *Overview* tab.

    To know how to activate a MIG, see [Versioning a Message Implementation Guideline](versioning-a-message-implementation-guideline-12784f9.md).

2.  Choose *Activate*. The system now activates the activated mapping guideline.

    > ### Note:  
    > Any subsequent edit operations on the same MIG would be saved as a different version.
    > 
    > After successful activation of MIG, a confirmation box appears with the following information
    > 
    > -   List of values that get published into the knowledge graph
    > 
    > -   List of values that will not get published into the knowledge graph


