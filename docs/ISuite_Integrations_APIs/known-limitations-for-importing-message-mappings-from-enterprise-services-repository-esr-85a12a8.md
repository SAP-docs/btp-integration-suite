<!-- loio85a12a87aec045a3b68c7b757cca1e2e -->

# Known Limitations for Importing Message Mappings from Enterprise Services Repository \(ESR\)

When importing message mappings from Enterprise Services Repository \(ESR\) into SAP Integration Suite, certain message mapping constructs, functions, parameters, and function library implementations aren't fully supported.

> ### Note:  
> You can still import unsupported message mappings by selecting Import Selected Message Mapping during the import process. See [Import a Message Mapping from ESR](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/creating-message-mapping-as-artifact?version=CLOUD#import-a-message-mapping-from-enterprise-services-repository-(esr))



## Unsupported Message Mapping and User-Defined Functions

****


<table>
<tr>
<th valign="top">

Limitation

</th>
<th valign="top">

Impact

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Message mapping uses the jdbclookup function.

</td>
<td valign="top">

JDBC lookups aren't supported in imported message mappings.

</td>
<td valign="top">

Replace the lookup implementation with supported SAP Integration Suite capabilities.

</td>
</tr>
<tr>
<td valign="top">

Message mapping uses the rfclookup function.

</td>
<td valign="top">

RFC lookups aren't supported in imported message mappings.

</td>
<td valign="top">

Reimplement the lookup logic using supported integration flow components.

</td>
</tr>
<tr>
<td valign="top">

Message mapping uses the sender function.

</td>
<td valign="top">

Sender context information isn't supported.

</td>
<td valign="top">

Provide the required values through message headers or exchange properties.

</td>
</tr>
<tr>
<td valign="top">

Message mapping uses the receiver function.

</td>
<td valign="top">

Receiver context information isn't supported.

</td>
<td valign="top">

Provide the required values through message headers or exchange properties.

</td>
</tr>
<tr>
<td valign="top">

User-defined functions contain parameters of type Channel.

</td>
<td valign="top">

Channel-type parameters aren't supported.

</td>
<td valign="top">

Redesign the function using supported parameter types.

</td>
</tr>
<tr>
<td valign="top">

User-defined functions use the Dynamic Configuration API to access adapter-specific message attributes.

</td>
<td valign="top">

Dynamic Configuration APIs aren't supported.

</td>
<td valign="top">

Replace the implementation with supported message headers, exchange properties, or integration flow logic.

</td>
</tr>
</table>



## Parameter-Related Limitations

****


<table>
<tr>
<th valign="top">

Limitation

</th>
<th valign="top">

Impact

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Message mapping uses parameters.

</td>
<td valign="top">

Certain parameter scenarios aren't supported after import.

</td>
<td valign="top">

Redesign the mapping using message headers, exchange properties, or externalized parameters.

</td>
</tr>
<tr>
<td valign="top">

Importing message mappings with parameters as local message mappings.

</td>
<td valign="top">

Local message mappings don't support imported parameters.

</td>
<td valign="top">

Use a reusable message mapping artifact instead of a local message mapping.

</td>
</tr>
<tr>
<td valign="top">

Imported mappings use Simple Type parameters, Adapter-type parameters, function libraries with Simple Type parameters, or Dynamic Configuration APIs.

</td>
<td valign="top">

Additional manual adjustments may be required to ensure correct runtime behavior.

</td>
<td valign="top">

Review and manually adapt the integration flow after import.

</td>
</tr>
</table>



## Source and Target Message Limitations

****


<table>
<tr>
<th valign="top">

Limitation

</th>
<th valign="top">

Impact

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Source messages contain XML payload attachments.

</td>
<td valign="top">

The message mapping may not be supported after import.

</td>
<td valign="top">

Redesign the mapping using supported message structures.

</td>
</tr>
<tr>
<td valign="top">

Target messages contain XML payload attachments.

</td>
<td valign="top">

The message mapping may not be supported after import.

</td>
<td valign="top">

Redesign the mapping using supported message structures.

</td>
</tr>
<tr>
<td valign="top">

Source messages contain ZIP attachments.

</td>
<td valign="top">

ZIP-based message definitions aren't supported.

</td>
<td valign="top">

Remove ZIP-based dependencies before import.

</td>
</tr>
<tr>
<td valign="top">

Target messages contain ZIP attachments.

</td>
<td valign="top">

ZIP-based message definitions aren't supported.

</td>
<td valign="top">

Remove ZIP-based dependencies before import.

</td>
</tr>
</table>



## Function Library Limitations

****


<table>
<tr>
<th valign="top">

Limitation

</th>
<th valign="top">

Impact

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Function library contains user-defined functions with execution type ALL\_VALUES\_OF\_QUEUE.

</td>
<td valign="top">

The function library isn't supported.

</td>
<td valign="top">

Redesign the implementation using supported execution types.

</td>
</tr>
<tr>
<td valign="top">

Function library contains user-defined functions with arguments of type Channel.

</td>
<td valign="top">

The function library can't be imported successfully.

</td>
<td valign="top">

Replace Channel-type arguments with supported alternatives.

</td>
</tr>
<tr>
<td valign="top">

Function library init\(\) method contains arguments of type Parameter.

</td>
<td valign="top">

The function library isn't supported.

</td>
<td valign="top">

Remove unsupported parameter types from the implementation.

</td>
</tr>
<tr>
<td valign="top">

Function library class name doesn't match the function library name.

</td>
<td valign="top">

Import validation may fail.

</td>
<td valign="top">

Ensure that the class name and function library name are identical.

</td>
</tr>
<tr>
<td valign="top">

Multiple methods use the same combination of category and title attributes.

</td>
<td valign="top">

The function library doesn't meet import requirements.

</td>
<td valign="top">

Ensure that each method uses a unique category-title combination.

</td>
</tr>
<tr>
<td valign="top">

Function library contains user-defined functions that use Dynamic Configuration APIs.

</td>
<td valign="top">

The function library isn't supported.

</td>
<td valign="top">

Replace Dynamic Configuration API usage with supported SAP Integration Suite capabilities.

</td>
</tr>
</table>



## Import Dependency Limitations

****


<table>
<tr>
<th valign="top">

Limitation

</th>
<th valign="top">

Impact

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

Multiple dependent Message Types have identical names but different namespaces and are imported as WSDL files.

</td>
<td valign="top">

Only one WSDL file may be uploaded because uniqueness is based on the filename. This can result in empty nodes and an erroneous message mapping state.

</td>
<td valign="top">

Ensure that each Message Type generates a uniquely named WSDL file before import.

</td>
</tr>
<tr>
<td valign="top">

Dependent archive objects of a function library aren't imported automatically.

</td>
<td valign="top">

Imported function libraries may reference missing archive dependencies.

</td>
<td valign="top">

Manually import the required archive objects and reference them in the corresponding Imported Archives artifact.

</td>
</tr>
</table>

