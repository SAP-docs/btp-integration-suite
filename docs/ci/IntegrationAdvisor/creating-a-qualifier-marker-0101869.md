<!-- loio0101869f1b1d4118bd76a48feb9ba6e8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Qualifier Marker

Create qualifier markers that can be used to qualify a node.



<a name="loio0101869f1b1d4118bd76a48feb9ba6e8__prereq_dsp_b1d_cqb"/>

## Prerequisites

-   You've opened the MIG in the edit mode.
-   You've selected both the qualifying node and the node you want to qualify to include them in your MIG.
-   A qualifier marker from the qualifying node to the node you want to qualify isn't available in the *Constraint* column.
-   The cardinality of the qualifying node must be either \[1..1\] or \[0..1\].
-   The qualifying node has a codelist assigned to it. For more information, see [Assigning Codelists to Leaf Nodes](assigning-codelists-to-leaf-nodes-770f7be.md).



<a name="loio0101869f1b1d4118bd76a48feb9ba6e8__context_kc1_gbq_cqb"/>

## Context

The qualifier feature allows you to set a qualifier marker that identifies the element that is qualified by another data element. Qualifier markers are either automatically provided by message templates from type systems, or you can create your own qualifier markers to suit your business context. The procedure below explains how to create a qualifier marker.



## Procedure

1.  On the *Structure* tab, select the leaf node that you want to use as the qualifying node.

2.  On the *Details* tab of the resulting pane, choose :heavy_plus_sign: in the *Qualifiers* field.

3.  In the resulting *Qualifiable Nodes* dialog box, select the node you want to qualify from the list of qualifiable nodes.

4.  Choose *Add*.




<a name="loio0101869f1b1d4118bd76a48feb9ba6e8__result_y2f_m2q_cqb"/>

## Results

The selected qualifiable node appears in the list of *Qualifiers* and a new qualifier marker arrow appears in gray colour from the qualifying node to the qualifiable node.

