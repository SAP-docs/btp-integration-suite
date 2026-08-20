<!-- loio74b67f9a9b5243af9facf489082aff74 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Creating Message Implementation Guidelines by Payload

Use payload-based creation to automatically generate a message implementation guideline from an existing EDI flat file, with the wizard suggesting matching type systems, message types, versions, and envelopes based on your payload.



<a name="loio74b67f9a9b5243af9facf489082aff74__prereq_z41_qfr_gcb"/>

## Prerequisites

-   You've logged into SAP Integration Suite.

-   Only EDI flat files are currently supported for payload-based MIG creation. For XML payloads, please use the standard creation wizard. See [Creating Message Implementation Guidelines](creating-message-implementation-guidelines-b894de0.md).




## Context

A message implementation guideline \(MIG\) is the source/target that you use in a mapping guideline. You use a template from one of the type systems available in the library as the starting point and build your MIG based on your requirement. The application also provides you with proposals on which nodes are most appropriate for you using the existing MIGs as the reference.

In this process, you use a payload as the base for your new message implementation guideline. To create one without a payload, see [Creating Message Implementation Guidelines](creating-message-implementation-guidelines-b894de0.md).

Based on the payload you provide, the wizard suggests options for type systems, message types, versions, and envelopes according to how closely they match this payload file. The objects and matches are grouped as follows:

-   **Best match based on payload**: The one object that fits the payload the best
-   **Possible matches based on payload**: Other possible matches that fit less than the best match, but are still suitable
-   **Other options**: All remaining objects that don't match the payload criteria of the previous categories, but you can still select them manually

If there's no match, you choose from the full list of available options.



## Procedure

1.  Go to *Design* \> *MIGs*.

2.  Choose *Create* \> *Create by Payload*.

3.  In the first step of the wizard, browse for or upload a payload file, either an EDI payload or a ZIP file containing EDI payloads. If you select a ZIP file, you can then select the exact file before continuing.

    In the next steps, the wizard then suggests available options for type systems, message types, versions, and envelopes by how closely they match this payload file.

4.  In the next step, choose a type system from the list of matches and other available options.

    By default, all standard type systems are listed. If you want to select a custom type system, select the *Custom* button.

5.  Next, the list of messages under the selected type system is displayed under the *Messages* step. Choose a message from the list of matches and other available options.

6.  The *Versions* step displays the available versions of the message. Choose the desired version from the list.

7.  In the *Envelopes* step, select an envelope for the type system from the list.

    > ### Note:  
    > To see the messages allowed for an envelope, go to *Discover* \> *Type Systems* and open the relevant type system. In the tab *Messages*, search for the envelope and open the relevant version. In the *Structure* tab, find the message placeholder and check the codelist assigned to it. The list of code values represents the allowed messages.

    To continue **without an envelope**, choose *None*.

8.  The *Sample Payload* step shows the payload that you selected in the first step of the wizard. Decide whether to use the sample payload for **pre-configuration** by selecting *Use Payload to Pre-Configure Message Implementation Guideline*. If you do, the following sub features appear:

    -   *Select Nodes* \(pre-selected\): All nodes that are part of the sample payload are included in the new message implementation guideline.
    -   *Perform Qualification* \(pre-selected\): In an additional step, you can select relevant nodes for automatic qualification. If there are qualifier values in the sample payload, the nodes selected for qualification are automatically qualified with those values.
    -   *Set Example Values*: Choose if the values present in the sample payload should be transferred to the new message implementation guideline. The values then show up as example values when you select a node and go to *Details* \> *Properties*, or when you run a simulation for the MIG.

    To skip the whole step, choose *Skip*.

9.  In the *Qualification* step, select nodes that the system then automatically qualifies in your MIG based on the qualifier values present in your payload.

    This step only comes up when you chose to use the payload for pre-configuration in the previous step.

    > ### Note:  
    > This step works only if required qualifying values are available in the payload. If available, the nodes selected for qualification are automatically qualified with the qualifier values contained in the payload thereby simplifying the qualification process.
    > 
    > Nodes without a unique qualification marker are disabled for selection.

    See also the blog [Integration Advisor – payload-based qualification at time of MIG creation](https://community.sap.com/t5/technology-blogs-by-sap/integration-advisor-payload-based-qualification-at-time-of-mig-creation/ba-p/13990599).

10. Finally, in the *MIG Creation* step, maintain the following fields:

    1.  *Name*: Name of the message implementation guideline

    2.  *Direction*: Direction is used together with your *Own Business Context* and your *Partners Business Context* to make the *Proposal Service* more precise. The values given describe the direction from a B2B interaction point of view.

        -   *In*: The MIG describes a message that you receive from a business partner.
        -   *Out*: The MIG describes a message that you send to a business partner.
        -   *Both*: The MIG describes a message that can both be received from a partner or sent to a partner. Alternatively, the MIG describes an A2A communication where only the *Own Business Context* is set \(and where *Partner Business Context* isn't relevant\).

        > ### Example:  
        > You receive an EDIFACT message from your business partner and map it to an IDoc message that's sent to your backend system. In this case, you should classify both your source EDIFACT MIG and your target IDoc MIG as *In* because they both represent a message in which your business partner is the logical sender and your company is the logical receiver.

    3.  *Summary*: You can provide a text description of the message implementation guideline. This description is visible as short text documentation in the MIG overview list.

    4.  *Business Context*: Select :heavy_plus_sign:, and choose the business context that you want to add. Based on the business context that you add, you're provided with further options in drop-down list. To understand, *business context*, see [Terminology & Glossary for SAP Integration Advisor](terminology-glossary-for-sap-integration-advisor-9c221b4.md).


11. Choose *Create*.


