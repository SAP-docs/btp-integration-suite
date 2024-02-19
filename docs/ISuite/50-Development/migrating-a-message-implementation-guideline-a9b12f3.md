<!-- loioa9b12f33ecee41fd90b90f41013fb465 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Migrating a Message Implementation Guideline

You can migrate your Message Implementation Guideline \(MIG\) to a different version \(newer or older\) of the same message or even to a different message \(of the same or a different type system\). A new MIG is created based on the new message you have chosen and customizations done in your previous MIG are copied over to the new MIG based on a best-effort strategy.



## Context

MIGs are developed based on predefined message definitions of a specific type system version. A MIG derives its structure definition, properties, documentation, and codelists from the underlying message template. The message structure can then be customized to meet specific business requirements.

Let’s consider a scenario where, you and your Business Partner 1 agreed on using an UN/EDIFACT D.01B S3 version ORDER message. You've created a MIG based on this specific version of the message from the type system library. You've also customized your MIG definition to meet your business needs. Later, you realize that you need to build another MIG for Business Partner 2 who is also using the same message of the same type system but a different version, say, D.16A S3. However, messages from two different versions of the same type system have similar settings except for a few variations. Earlier, you had to create a new MIG based on the new version and redo the customizations that you had done in the existing MIG. Instead, you can now migrate your existing MIG to a different version of the same type system. After migration, a new MIG is created based on the chosen version including the customizations done in the existing MIG.

> ### Note:  
> Customizations or nodes that are incompatible with the new version aren’t migrated. They're notified through error messages.

After migrating your MIG, you can use the status review section available in the MIG editor to view notifications, add comments, and mark review status for all the selected nodes that are part of the MIG. You can identify nodes needing further rework or discussion by reviewing the icons in the Status column on the Structure tab. You can also compare the MIGs after migration to review them. Comparisons are made across the structure definition, properties, documentation, code values, and example values of the MIGs. This allows easy identification of similarities and variations across MIGs.

**Other Supported Scenarios**

-   When a newer revision for a specific type system version is available, you're notified of it during migration. You can choose to migrate your existing MIG, in this case, to a newer revision of the type system version so that you can use the already customized MIG in the newest revision.

-   You can also choose to migrate your MIG to a different type system if the underlying message structure is similar enough, such as from EDIFACT to EANCOM or from SAP S/4HANA Cloud SOAP to SAP S/4HANA On Premise SOAP. The compatibility is determined on a case-to-case basis.

-   You can also migrate your MIG to a different message such as from ORDERS05 to ORDERS03 in IDoc version 1809 FPS02 if the underlying message structure is similar enough. The compatibility is determined on a case-to-case basis.

-   You can also migrate your MIG to a different message type with different root node. The migration will be done on a best-effort strategy for the subnodes that are present in the old and new message structure.



## Procedure

1.  On the *Message Implementation Guidelines* screen, choose <span class="SAP-icons-V5"></span> \(More Options\) on the MIG that you want to migrate and then choose *Migrate*.

    > ### Tip:  
    > The *Migrate* option is also available on both the *Overview* tab and the *History* link of the MIG that you want to migrate.

2.  In the *Migrate Message Implementation Guideline* dialog box, on the *Versions* tab, select the version that you want to migrate your MIG to.

    > ### Note:  
    > Choose the *Messages* tab or the *Type Systems* tab to migrate your MIG to a different message or a different type system.

    The resulting *Migrate Message Implementation Guideline* dialog box displays the details of the MIG including the new version number.

3.  Optional: You can review the details and optionally choose to customize by adding more details regarding your and your partner’s business context. To add your or your partner’s business context, choose :heavy_plus_sign: to provide more details. This helps the application provide an appropriate proposal based on the defined business context. The accuracy of the proposal depends on the number of selected business context categories and business context values.

4.  Choose *Create*.




<a name="loioa9b12f33ecee41fd90b90f41013fb465__result_zrc_dc1_lpb"/>

## Results

A new MIG is created.

> ### Tip:  
> A few pointers to keep in mind while you review and verify your MIG after migration:
> 
> -   The migration works on a best-effort strategy and considers frequently occurring situations. But there can be situations \(when it comes to considering all three of previous message, previous MIG and new message\) which can't be easily resolved and might need user interaction. In such cases a node or property can't be migrated and you will be notified of this through a status notification.
> -   Nodes and their properties are migrated only if they're selected in the original MIG. Unselected mandatory nodes and their properties are not migrated.
> 
> -   Since mandatory nodes are preselected based on the underlying message template when a MIG is created, MIG migration does not actively unselect such mandatory nodes.
> -   For each selected node of the original MIG -
> 
>     -   If a matching node is available in the new message structure, details such as properties, code values, and documentation associated with this node gets migrated to the matched node in the new MIG.
> 
>     -   There can be situations where a node can't be fully matched but where the migration finds an alternative match. For example, say Node1 in namespace1 is not present in the new message but there is a Node1 in namespace2 available. In such case, migration will be done for this alternative match and you will be notified through a status notification to review this decision.
>     -   If a matching node isn't present in the new message structure, you're notified through status notifications.
> 
>     > ### Note:  
>     > If a matching group node isn't available in the new message structure, its subnodes aren't migrated as well.
> 
> -   Any modification done to an element's property, code value, or documentation in your original MIG remains intact even after MIG migration. For example, if a node's standard maximum length property of 10 was changed to 5 in the original MIG, the chosen value of 5 is retained in the new migrated MIG irrespective of the new MIG version's standard value.
> -   However, if you retained the standard values for an element's property, code value, or documentation in your original MIG, MIG migration keeps the standard setting in the new MIG as well. For example, if a node's standard maximum length property of 10 was unchanged in the original MIG, the matching node's standard maximum length property of 20 is retained in the new migrated MIG reflecting the new MIG version's standard value.
> -   In case of conflicts, an element's property, code value, or documentation might not get migrated. They are notified via status notifications.

This section contains the recommended follow-up steps for review and verification after migration.

1.  To review status notifications, on the *Structure* tab, review the message structure and filter for any notification on the *Status* column to display the number of errors, warnings, informational messages, and comments.

    1.  Select the required cell in the *Status* column to view more details in the *Notifications* section.

    2.  Choose *Edit* to add comments and set a status for the node in the *User Review* section. You can also choose to *Discard*any status notifications that you have reviewed and no longer need it.

    3.  Choose *Save*.


    > ### Tip:  
    > -   On the *Structure* tab, choose *Show Status Comments* <span class="SAP-icons-V5"></span> to hide some of the columns for the prominent visibility of *Status* and *Comment*.
    > 
    > -   On the *Structure* tab, choose *Settings* :gear: to customize column visibility of the properties.

2.  Choose *Show Changes Mode* <span class="SAP-icons-V5"></span> to see differences between the MIG and its underlying message template.

3.  Choose *Edit* to customize your MIG as per your business needs.

4.  Choose *Save*.


