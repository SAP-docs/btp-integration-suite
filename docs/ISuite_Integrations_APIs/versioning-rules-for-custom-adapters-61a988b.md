<!-- loio61a988b4854e4e9988237be1673189ae -->

# Versioning Rules for Custom Adapters

Follow the guidelines mentioned below to version a custom adapter.

> ### Note:  
> This versioning feature is available from ADK version 1.38.0.

**Versioning Rules**


<table>
<tr>
<th valign="top">

Version Type

</th>
<th valign="top">

Applicable For

</th>
<th valign="top">

Rules

</th>
</tr>
<tr>
<td valign="top">

Micro Version

</td>
<td valign="top">

Small changes such as label and tooltip updates

</td>
<td valign="top">

-   Existing metadata variant should be updated with new micro version

-   For example, if the current version is 1.0.0, then the version has to be updated to 1.0.1 both at the component and variant level.
-   Relevant metadata changes has to be done in the same file.



</td>
</tr>
<tr>
<td valign="top">

Minor Version

</td>
<td valign="top">

Adding a new feature

> ### Note:  
> It is not recommended to add mandatory fields. If needed, ensure that the runtime is backward compatible.



</td>
<td valign="top">

-   Each variant should be in a single metadata file. If both sender and receiver version has to be updated, two separate metadata files has to be created for each.

-   Both the component and variant version has to be updated.
-   Necessary metadata changes has to be done in the newly created metadata file.
-   The existing version remains unchanged. So, the existing scenarios will have old user interface and it should continue to work as before. Only new scenarios will reflect the new version changes.



</td>
</tr>
<tr>
<td valign="top">

Major Version

</td>
<td valign="top">

Incompatible Changes

> ### Note:  
> This is not supported.



</td>
<td valign="top">

 

</td>
</tr>
</table>

The step by step procedure to perform a micro and minor version update is explained below.

*Micro Version Update*

1.  Ensure that the necessary changes has been made to the existing metadata variant.

2.  Increment the micro version of the existing metadata both at component level and variant level.
3.  Increment the version in `config.adk`.

*Minor Version Update*

1.  Copy the variant of latest version to a new metadata file. Only one variant should exist within a metadata file for any new version.

    > ### Note:  
    > The same metadata directory will contain multiple metadata files. Any naming convention can be followed for versioned files.

2.  Make the minor version increment to the new metadata both at component and variant level.
3.  Make the necessary changes to the metadata.
4.  Make the necessary runtime changes.

    > ### Note:  
    > Make sure the runtime is compatible with earlier version and the existing scenarios should continue to work.

5.  Increment the version in `config.adk`.

