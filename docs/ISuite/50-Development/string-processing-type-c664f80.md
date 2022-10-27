<!-- loioc664f802dd094a58a6231e9425af6423 -->

# String Processing Type

You use the *String Processing* type to map multiple source node of type *String* and *Token* to one or more target nodes of type *String* and *Token*.

1.  To apply string processing, select the source node and navigate to the *Functions* tab and choose *Switch to String Processing*.

    This will automatically consider the properties of the mapped source and target nodes without the need to create any additional functions or post processing scripts.

    > ### Note:  
    > Switching to String Processing will delete the existing function.

2.  The string processing function considers the length and cardinality of the target nodes to distribute lengthy source message among the target nodes. When the source message exceeds the maximum string length defined for the target node, the message gets truncated.

    To process messages that contain delimiters, select the corresponding delimiter from the *Source Delimiter* drop down.


