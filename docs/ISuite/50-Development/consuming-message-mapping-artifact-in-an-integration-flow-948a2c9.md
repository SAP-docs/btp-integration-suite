<!-- loio948a2c931bbe4be49453b35c13a71121 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Consuming Message Mapping Artifact in an Integration Flow



<a name="loio948a2c931bbe4be49453b35c13a71121__prereq_qnz_mvd_syb"/>

## Prerequisites

You've added a mapping step in your integration flow. See: [Creating Message Mapping as a Flow Step](creating-message-mapping-as-a-flow-step-3d5cb7f.md).



## Context

Consuming a mapping artifact is a two-step process in your integration flow:

1.  Add a reference to the message mapping artifact from your integration flow

2.  Assign the referenced message mapping artifact to a message mapping flow step




## Procedure

1.  To add a reference to the message mapping artifact from your integration flow, perform the following steps:

    1.  Open your integration flow in edit mode.

    2.  In the property sheet, choose *References* \> *Global* \> *Add References* \> *Message Mapping*.

    3.  Select one or more message mapping artifacts that you like to reuse in your integration scenario.

    4.  Choose *OK*.


2.  To reuse mapping artifacts in a message mapping step, perform the following steps:

    1.  Choose the quick action in the *Message Mapping* step, and then choose <span class="SAP-icons-V5"></span> \(Assign\).

    2.  In the *Select Mapping Resource* dialog box, choose the *Global Resources* tab.

    3.  Choose the referenced mapping artifact.

    4.  Choose *OK*.



