<!-- loiocb5311a37aa244cc9056b209f07152a4 -->

# Troubleshooting Message Mapping

Information on troubleshooting incidents and errors for Message Mapping.



<a name="loiocb5311a37aa244cc9056b209f07152a4__section_hkv_ykp_dfc"/>

## Issues faced during Design time

****


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Description

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Design time issues

</td>
<td valign="top">

Unable to simulate

</td>
<td valign="top">

The [Message Mapping](50-Development/message-mapping-459ccdf.md) simulation feature enables integration developers to test mapping within the web application by deploying an integration project to an available IFLMAP worker node. If no worker node is available, the simulation cannot proceed. To address this, verify the status of the runtime nodes and activate at least one to enable the simulation.

</td>
</tr>
<tr>
<td valign="top">

Groovy function not listed

</td>
<td valign="top">

Functions from the attached Groovy file are not appearing in the message mapping functions tree.

Make sure the following settings are maintained:

-   Only Groovy functions that meet the message mapping's defined conditions will be listed in the tree.
-   In Eclipse, the Create Wizard's help contents define the contracts, while the '?' button in the web UI provides this information.
-   Modify the functions to comply with the conditions so they appear in the mapping.

> ### Note:  
> Reopen the message mapping to apply updates from the script file.



</td>
</tr>
<tr>
<td valign="top" rowspan="6">

Runtime issues

</td>
<td valign="top">

Errors occur at runtime due to incomplete mapping or unassigned mandatory fields.

</td>
<td valign="top">

During the Integration flow deployment:

1.  Open the mapping and execute checks via the flyout context menu in SMP Tooling.
2.  Inspect the mapping for any incomplete expressions in the target nodes.
3.  Verify if any mandatory target node is unmapped.



</td>
</tr>
<tr>
<td valign="top">

Unexpected output occurs due to issues with value mapping

</td>
<td valign="top">

Verify for the following:

1.  Source and Target agency
2.  The schema specified in the "Value mapping" node function is present in the deployed value mapping XML.
3.  The value in the input payload matches the source value specified in the value mapping.



</td>
</tr>
<tr>
<td valign="top">

Validation error during Integration flow deployment

</td>
<td valign="top">

Verify for the following:

1.  Message Mapping lacks support for composite WSDLs, which work in Eclipse due to EMF plugins. Deployment fails as mapping validation cannot resolve WSDL import statements. To fix this, flatten your WSDL file.
2.  Message mapping can reference WSDL/XSD/EDMX/GSH files, but files with spaces in their names won't resolve. Rename the file to remove spaces and use the replace button in the editor to assign the updated file.



</td>
</tr>
<tr>
<td valign="top">

Mapping output does not align with the input source message structure

</td>
<td valign="top">

Verify the namespace binding for both the source message and the input payload.

> ### Example:  
> If the root node of the source message is "ns2:root," the input message must include the namespace prefix, which should be properly defined to achieve the expected output.



</td>
</tr>
<tr>
<td valign="top">

Output payload does not display the mapped child node

</td>
<td valign="top">

Verify the root node cardinality.

If the mapping is "0..unbounded," the root node must be mapped to include the child node in the output; otherwise, the context will be skipped.

</td>
</tr>
<tr>
<td valign="top">

Error: Cannot produce target element <XPATH\>

</td>
<td valign="top">

Perform the following:

1.  Verify the mapping for the XPATH mentioned in the error and examine the related source context.
2.  Ensure the source context path exists in the input payload and is valid according to the mapping.



</td>
</tr>
</table>

