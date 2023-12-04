<!-- loiob287e5eae6e54359bd0103d0f148befb -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Pretransformation of a Message Implementation Guideline

Learn how to transform the structure of a Message Implementation Guideline.

When working with a mapping guideline, there could be scenarios where the source MIG and the target MIG could not be mapped together due to significant structural differences between them such as node hierarchies etc.

The goal of Pretransformation is to allow a business user to define, simulate and pretransform a source MIG including the source message instance so that it fits better to the structure of the target MIG. Once pretranformed, the MIG can then be used in the normal mapping of a MAG.

Pretransformation means a way of modifying the source structure of a MIG with the purpose of allowing subsequent mappings that would not be possible in the application without such a modified source structure being applied. The creation of mappings respectively the drawing of mapping lines in a mapping guideline always requires a MIG on either side of the mapping. Therefore, Pretransformation applies a certain structural transformation to the hierarchy of the incoming payload and its corresponding MIG defined by a Pretransformation Script\(PTS\). As a next step for the payload to be executable at runtime in an integration flow, PTS also needs to provide a corresponding runtime artifact. So, Pretransformation comprises of two major operations:

-   **MIG Transformation** which is executed at design time to provide the corresponding transformed message structure for the MIG that replaces the MIG structure that's on the left side of a MAG.

-   **Payload Transformation** which is executed in an integration flow. To do this, the application would export an additional XSLT script which is, however, contained in the same xsl file as the main XSLT script.

    Follow the procedure below to know how to create and delete a pretranformation.




<a name="loiob287e5eae6e54359bd0103d0f148befb__section_uxl_1xf_mvb"/>

## Creating a Pretransformation

Suppose, let us say you have created a MAG with two MIGs and want to transform a MIG to continue with the mapping.

1.  Open your MAG and choose *Edit*.

2.  Navigate to the *Overview* tab. The *Pretransformation* field under *Source and Target MIGs* displays the name of the pretransformation. If no transformation is done, the value is *None*.

    Choose the Add button :heavy_plus_sign:

    next to the field.

3.  This will open the *Mapping* tab with the pretransformation function. By default the source MIG of the mapping structure is considered for pretransformation.
4.  The page consists of 3 sections:
    -   *MIG Structure*: The structure of the MIG chosen for pretransformation. This would always show the unmodified source MIG structure.

    -   *Pretransformation/Main Transformation*: The button that helps you toggle between pretransformation and the main mapping guideline. Below *Pretransformation*, you have the tables to define your transformation steps and the corresponding parameters.
    -   *Pretransformed Structure*: The pretransformation that you define gets applied on this structure and this modified MIG becomes the pretransformed MIG. You can check the results and move to *Main Transformation* for mapping.

5.  The text field *New Pretransformation* shows the name of the transformation. You can edit and give a meaningful name according to your business purpose.
6.  Next to *Transformation Steps*, choose *Add*. It has the following options:

    -   *Group by Key*: This option allows you to group the elements based on the values of specified node and puts them under a new wrapper node.

    -   *Copy referenced node*: This option allows you to copy an element referenced by a key or ID into a specified node.

    Choose one of the options.

7.  If you chose *Group by Key*, then maintain the following parameters in the *Operation Parameters* table displayed below the *Transformation Steps* table.

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
    
    The group node whose instances will be grouped.
    
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
    
    The name of the group node that will contain the grouped nodes. This node will become the parent node of the grouped node.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Group key node
    
    </td>
    <td valign="top">
    
    Child node of the wrapper node that will contain the key of the group for each instance.
    
    </td>
    </tr>
    </table>
    
8.  If you chose *Copy referenced node*, then maintain the following parameters in the *Operation Parameters* table displayed below the *Transformation Steps* table.

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
    
    Group node which is referenced and will be copied.
    
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
    
9.  After maintaining all the entries, choose *Execute* that is displayed next to the *Transformation Steps* table. This will apply the operation to the MIG structure and pretransformed structure is displayed under *Pretransformed Structure* on the right.
10. You can check for the results and modify your operation accordingly. You can also delete your transformation step using the Delete :wastebasket: button provided in the *Transformation Steps* table.
11. If you are satisfied with the outcome of the transformation, choose *Save* and you can continue to the mapping by choosing *Main Transformation*.
12. You can now see that source MIG is the latest pretransformed MIG. You can start working on mapping using this MIG. To know about mapping the source and target nodes, see [Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md)
13. You can also simulate and see the effects of your pretransformation on a payload. To do so, choose *Simulate*.
14. Refer to this [blog](https://blogs.sap.com/2022/11/28/new-feature-in-integration-advisor-reordering-of-source-structure/) post to know more about pretransformation through a real-time example.

