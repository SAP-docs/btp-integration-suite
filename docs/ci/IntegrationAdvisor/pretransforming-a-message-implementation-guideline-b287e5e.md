<!-- loiob287e5eae6e54359bd0103d0f148befb -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Pretransforming a Message Implementation Guideline

Learn how to transform the structure of a message implementation guideline to better use it in a mapping guideline.



## Context

When working with a mapping guideline, in some scenarios the source MIG and the target MIG can't be mapped due to significant structural differences between them, for example, node hierarchies. The goal of **pretransformation** is to allow you to define, simulate, and pretransform a source MIG including the source message instance so that it fits better to the structure of the target MIG. Once pretransformed, you can use the MIG in the normal mapping of a MAG.

Pretransformation is a way of modifying the source structure of a MIG with the purpose of allowing later mappings that wouldn't be possible in the application without such a modified source structure being applied. The creation of mappings, that is, the drawing of mapping lines in a mapping guideline, always requires a MIG on either side of the mapping. Therefore, pretransformation applies a certain structural transformation to the hierarchy of the incoming payload and its corresponding MIG defined by a pretransformation script \(PTS\). As a next step for the payload to be executable at runtime in an integration flow, PTS needs to provide a corresponding runtime artifact. So, pretransformation consists of two major operations:

-   The **MIG transformation**, which is performed at design time. Its goal is to provide the corresponding transformed message structure for the MIG that replaces the MIG structure on the left side of a MAG.

-   The **payload transformation**, which is performed in an integration flow. To achieve the transformation, the application exports an additional XSLT script which is, however, contained in the same XSL file as the main XSLT script.



## Procedure

1.  Let's assume that you've created a MAG with two MIGs and you want to transform a MIG to continue with the mapping.

    Open your MAG and choose *Edit*.

2.  Navigate to the *Overview* tab. The *Pretransformation* field under *Source and Target MIGs* displays the name of the pretransformation. If no transformation is done, the value is *None*.

3.  Next to the field, choose :heavy_plus_sign: to open the *Mapping* tab with the pretransformation function. By default, the source MIG of the mapping structure is considered for pretransformation.

    The page consists of the following sections:

    -   *MIG Structure*: The structure of the MIG chosen for pretransformation. It always shows the unmodified source MIG structure.

    -   *Pretransformation/Main Transformation*: The button that helps you toggle between pretransformation and the main mapping guideline. Below *Pretransformation*, you have the tables to define your transformation steps and the corresponding parameters.
    -   *Pretransformed Structure*: The pretransformation that you define is applied on this structure and this modified MIG becomes the pretransformed MIG. You can check the results and move to *Main Transformation* for mapping.

4.  The field *New Pretransformation* shows the name of the transformation. Edit it to give it a meaningful name according to your business purpose.

5.  Next to *Transformation Steps*, choose *Add*. Choose one of the following options:

    -   *Group by Key*: Group the elements based on the values of specified node and puts them under a new wrapper node. If you choose this step, continue with step 6.
    -   *Copy referenced node*: Copy an element referenced by a key or ID into a specified node. If you chose this step, continue with step 7.

6.  If you chose *Group by Key*, maintain the following parameters in the *Operation Parameters* table displayed below the *Transformation Steps* table:

    **Operation Parameters**


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Grouped node
    
    </td>
    <td valign="top">
    
    The group node whose instances are grouped.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key node
    
    </td>
    <td valign="top">
    
    The leaf node that contains the key for grouping. This node must be a child node of the grouped node.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Wrapper name
    
    </td>
    <td valign="top">
    
    The name of the group node that contains the grouped nodes. This node becomes the parent node of the grouped node.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Group key node
    
    </td>
    <td valign="top">
    
    Child node of the wrapper node that contains the key of the group for each instance.
    
    </td>
    </tr>
    </table>
    
7.  If you chose *Copy referenced node*, maintain the following parameters in the *Operation Parameters* table displayed below the *Transformation Steps* table.

    **Operation Parameters**


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Receiving node
    
    </td>
    <td valign="top">
    
    The group node to which the referenced node is copied into.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Node with reference ID
    
    </td>
    <td valign="top">
    
    Leaf node that contains the reference ID of the node to be copied. This node must be a child node of the receiving node.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Referenced Node
    
    </td>
    <td valign="top">
    
    Group node which is referenced and copied.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Referenced ID Node
    
    </td>
    <td valign="top">
    
    Leaf node that contains the ID which is referenced. This node must be the child node of the referenced node.
    
    </td>
    </tr>
    </table>
    
8.  After maintaining all the entries, choose *Execute* to apply the operation to the MIG structure. The pretransformed structure is displayed under *Pretransformed Structure*.

9.  Review the results and modify your operation accordingly. You can also delete your transformation step by choosing :wastebasket:.

10. If you're satisfied with the outcome of the transformation, choose *Save*.

11. Continue to the mapping by choosing *Main Transformation*.

    You can now see that source MIG is the latest pretransformed MIG.

    To simulate and see the effects of your pretransformation on a payload, choose *Simulate*.




## Example

To learn more about pretransformation and look at an example, see the blog [New Feature in Integration Advisor: Reordering of Source Structure](https://community.sap.com/t5/technology-blog-posts-by-sap/new-feature-in-integration-advisor-reordering-of-source-structure/ba-p/13563089).



## Next Steps

You can start working on mapping using this MIG. See [Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md).

