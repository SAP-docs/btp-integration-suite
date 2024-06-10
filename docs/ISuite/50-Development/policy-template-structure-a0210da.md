<!-- loioa0210daca06b4e43af0375224ab28a6e -->

# Policy Template Structure

During an import or export of a policy template, the policy template follows a pre-defined structure.

**Policy Template Structure**


<table>
<tr>
<th valign="top">

Folder Name

</th>
<th valign="top">

Path

</th>
<th valign="top">

Contents

</th>
</tr>
<tr>
<td valign="top">

Policy Template Container

</td>
<td valign="top">

\\PolicyTemplateContainer

</td>
<td valign="top">

Root folder that contains the FileResource and Policy information.

</td>
</tr>
<tr>
<td valign="top">

FileResource

</td>
<td valign="top">

\\PolicyTemplateContainer\\FileResource

</td>
<td valign="top">

Lists all the scripts attached to the policy. Only Java, Python, and XSL Scripts are supported. Follow the below naming convention:

-   Java Script: `<JavaScript name>.js`
-   Python script: `<PythonScript name>.py`
-   XSL script: `<XSLScript name>.xsl` 



</td>
</tr>
<tr>
<td valign="top">

Policy

</td>
<td valign="top">

\\PolicyTemplateContainer\\Policy

</td>
<td valign="top">

Contains a list of all available policies. Each policy is available as a separate file with the naming convention `<Policy name>.xml`.

</td>
</tr>
<tr>
<td valign="top">

`<policytemplatename>.xml` 

</td>
<td valign="top">

\\PolicyTemplateContainer\\`<policytemplate>.xml` 

</td>
<td valign="top">

Contains the header information of all the available policies.

</td>
</tr>
</table>

