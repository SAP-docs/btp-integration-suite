<!-- loio12398d4ba2ec41728e7221a9f0d5e08c -->

# Creating the Post-Exit Integration Flow



<a name="loio12398d4ba2ec41728e7221a9f0d5e08c__section_hwj_gql_mgb"/>

## Creating the Post-Exit Mapping

Create another integration flow with the same shapes as in the pre-exit integration flow \(also within the same integration package\). Make the following specific settings:

-   In the *Address* field of the ProcessDirect adapter, enter a string that is different to the one in the pre-exit integration flow, for example `/postexit_flow`.

-   Click in the area outside the integration process shape, go to the *Resources* tab, and upload the WSDL files for the messages A', B, and C.

    Note that you get the resource for message B from the standard integration flow, whereas the resource for message C depends on the specific custom enhancements related to the target structure. Typically, message C is similar to message B, but contains additional fields.

-   Configure the message mapping in the following way:

    For the source message, upload both resource files for messages A' **and** B. For the target message, upload the resource file for message C.

    You can proceed in the same way as described for the demo example in [Creating the Custom Mapping](creating-the-custom-mapping-4af8ea7.md).

    ![](images/Post_Exit_Mapping_5a94941.png)

    You will notice that the source message consists of two messages, A' and B.

    Connect **all fields** in the structure below `Message2` with the corresponding fields in the target structure.

-   Define connections **between selected \(additional\) fields of the extended original message A'** \(in the structure below `Message1`\) and selected fields in the target message C \(typically, using fields that have been added in the target structure\).


