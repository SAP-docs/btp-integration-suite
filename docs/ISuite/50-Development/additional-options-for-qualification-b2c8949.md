<!-- loiob2c89498886f443ba4e8ce618b316b50 -->

# Additional Options For Qualification

After qualifying the node, you can now perform the following functions from the context menu of the qualified node

-   *Change Qualified Node* allows you to modify the qualifier values of the node.

-   *Change Order of Qualified Node* allows you to change the order of the qualified nodes.
-   *Duplicate Qualified Node* creates a duplicate version of the qualified node where you can set different qualifier values.
-   *Duplicate Qualified Node for Remaining Values* creates a duplicate version of the qualified node that includes values that are not part of other instances of the same element group.
-   *Add Qualifier* allows you to add another qualifier to the node. By using this option you can also extend a simple qualification to a compound qualification.
-   *Delete Qualified Node\(s\)* allows you to delete one or more qualified nodes. Selecting this option provides you with two options
    -   *Delete this Qualified Instance*: If the selected node has other qualified instances, then this option only removes this instance and the node stays qualified.

        If the selected node has only one qualified instance, then the instance is removed and the node gets unqualified. The details of the earlier qualified node will be copied to the now unqualified node.

        > ### Note:  
        > The name and cardinality of the qualified node as well as the selected code values of the qualifying node will not be copied and they will be returned to the standard values from the message template:

    -   *Delete All Qualified Instances*: On choosing this option, the list of all qualified nodes corresponding to the selected node gets displayed. If you want to retain the details of any of the qualified nodes, select the node from the list. This will copy the details of the selected qualified node to the unqualified node.

        > ### Note:  
        > The name and cardinality of the qualified node as well as the selected code values of the qualifying node will not be copied and they will be returned to the standard values from the message template:



