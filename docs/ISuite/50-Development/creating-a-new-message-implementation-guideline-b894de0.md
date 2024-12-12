<!-- loiob894de00d93f4f58bfe5fb6ae9d35430 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a New Message Implementation Guideline



<a name="loiob894de00d93f4f58bfe5fb6ae9d35430__prereq_z41_qfr_gcb"/>

## Prerequisites

-   You've logged into SAP Integration Suite.



## Context

A message implementation guideline \(MIG\) is the source/target that you use in a mapping guideline. You use a template from one of the type systems available in the library as the starting point and build your MIG based on your requirement. The application also provides you with proposals on which nodes are most appropriate for you using the existing MIGs as the reference.



## Procedure

1.  Choose MIGs <span class="SAP-icons-V5"></span> icon from the left pane.

2.  Choose *Create* in the resulting screen to create a MIG.

3.  The *Create Message Implementation Guideline* wizard opens. Choose a type system from the list displayed under *Type System*step.

    By default, all standard type systems are listed. If you want to select a custom type system, select the *Custom* button.

4.  The list of messages under the selected type system is displayed under the *Messages* step. Choose a message from the list.

5.  The *Versions* step displays the available versions of the message. Choose the desired version from the list.

6.  In the *Envelope* step, select an envelope for the type system from the list. If you want to continue without any envelope, choose *None*.

7.  \(Optional\) In the *Sample Payload* step, you can browse and upload a payload file using the *Browse* button.

    If you want to skip this step, choose *Skip*.

8.  Set the format of the payload in the *Data Format* field. The supported formats of the payload are:

    1.  EDI Flat File: You can use this format only for type systems ASC X12, Odette, TRADACOMS, and UN/EDIFACT and its subsets. For more information, refer to the blog [Direct Support of EDI Payloads](https://community.sap.com/t5/technology-blogs-by-sap/integration-advisor-direct-support-of-edi-payloads/ba-p/13779418).

        > ### Note:  
        > The flat files might contain envelope segments outside the message structure. Integration Advisor will automatically consider the messages inside this envelope.

    2.  SAP Cloud Integration \(XML\)

    3.  SAP Process Integration \(XML\)


9.  When the MIG is created, any elements/attributes in the message structure get auto-selected when they're present in the sample payload file. You can additionally select *Use file content as example values* to use payload values as example values. Choose *Next*.

10. In the MIG Creation step, maintain the following fields:

    1.  *Name*: Name of the MIG

    2.  *Direction*: Direction is used together with your *Own Business Context* and your *Partners Business Context* to make the *Proposal Service* more precise. The values given describe the direction from a B2B interaction point of view.

        -   *In* - The MIG describes a message that you receive from a Business Partner.

        -   *Out* - The MIG describes a message that you send to a Business Partner.
        -   *Both* - The MIG describes a message that can both be received from a partner or sent to a partner. Or the MIG describes an A2A communication where only the *Own Business Context* is set \(and where *Partner Business Context* isn't relevant\).

        *Example*: Say you receive an EDIFACT message from your Business Partner and map it to an IDoc message that is sent to your backend system. In this case, you should classify both your Source EDIFACT MIG and your Target IDoc MIG as “*In*”, because they both represent a message where your Business Partner is the logical sender and your company is the logical receiver.

    3.  *Summary*: You can provide a text description of the Message Implementation Guideline \(MIG\). This description is visible as short text documentation in the MIG overview list.

    4.  *Business Context*: Select :heavy_plus_sign:, and choose the business context that you want to add. Based on the business context that you add, you're provided with further options in dropdown list. To understand, *Business Context* refer to [Terminology & Glossary for SAP Integration Advisor](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/9c221b48799a4ce59367b0e3367f5a8f.html "") :arrow_upper_right:.


11. Choose *Create*.

    > ### Note:  
    > You can also create a MIG from the Library of Type Systems. Navigate to the *Type Systems* <span class="SAP-icons-V5"></span> icon from the left pane, choose the type systems based on your requirement and navigate to the *Messages* tab.
    > 
    > -   Select your message and the respective version and choose <span class="SAP-icons-V5"></span> to create the MIG.
    > 
    > -   Alternately, open the message in the required version. The application provides a *Create MIG* button in the message type page that allows you to directly create a message implementation guideline.


