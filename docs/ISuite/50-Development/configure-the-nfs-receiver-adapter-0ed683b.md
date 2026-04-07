<!-- loio0ed683b66ee7471aa6b20b01be0e8e90 -->

# Configure the NFS Receiver Adapter

NFS Receiver Adapter provides the ability to write to a file on the NFS server.

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



## Configure the NFS Receiver Adapter

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Specify the hostname or IP address of the NFS server.

Example: `12.123.12.123`

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Drive Name*

</td>
<td valign="top">

Specify the name of the drive.

Example: `NFSShareDrive`

> ### Note:  
> Ensure that NFS sharing is enabled for the drive.

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*User ID \(UID\)*

</td>
<td valign="top">

Specify the Secure Parameter alias that stores the User ID associated with the NFS client.

> ### Note:  
> File ownership and permissions on the NFS server depend on the UID and GID mapping of the user performing the operation.

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Group ID \(GID\)*

</td>
<td valign="top">

Specify the Secure Parameter alias that stores the Group ID associated with the NFS client.

> ### Note:  
> File ownership and permissions on the NFS server depend on the UID and GID mapping of the user performing the operation.

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Maximum Connection Attempts*

</td>
<td valign="top">

Specify the maximum number of connection attempts to the NFS server. The default is 3 attempts.

Example: `5`

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Reconnect Delay \(in ms\)*

</td>
<td valign="top">

Specify the waiting time in milliseconds before attempting to reconnect to the NFS server. The default is `1000`.

Example: `300000`

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
</table>

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Directory*

</td>
<td valign="top">

Specify the directory where the files will be created. Use `/` to specify the root folder.

Example: `/Records/Day1`

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Create Directories*

</td>
<td valign="top">

Enable to create the missing folders in the target path as specified in the *Directory* field.

</td>
</tr>
<tr>
<td valign="top">

*File Name*

</td>
<td valign="top">

Specify the name of the file.

Example: `Order2026.txt`

> ### Note:  
> -   Use Camel expressions to add a timestamp if required.
> -   Certain special characters are not permitted for file names by the server. Example: '\*'. Using restricted characters may result in an error.

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Chunk Size \(in MB\)*

</td>
<td valign="top">

Specify the chunk size \(in MB\) depending on your NFS Server configurations.

Default value: `-1`

> ### Note:  
> -   The adapter dynamically queries the NFS server to determine its preferred write size \(wtpref\) and allocates a corresponding buffer to align each WRITE operation with the server’s optimal transfer size.
> 
> -   If -1, then chunk size is calculated using server configurations. Using the default configuration \(-1\) allows the adapter to internally determine a preferred chunk size \(in MB\) and orchestrate the write operation.
> -   Keep in mind that a request is processed through multiple recursive calls, hence your chunk size should reflect the client's capacity to handle these recursive calls. Use a custom value for chunk size only if your scenario has such a requirement, however it is recommended to retain the default configuration \(-1\).

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Append Message ID*

</td>
<td valign="top">

Enable to append the Message Processing Log ID to the file name.

Example: `Sharefile_AGkFE1kB-PrKO5nJQV1KR9amXjoh.txt`

</td>
</tr>
<tr>
<td valign="top">

*Append Timestamp*

</td>
<td valign="top">

Enable the checkbox to append the timestamp to the file name. The format for Timestamp is `yyyyMMdd-HHmmss-SSS`.

> ### Note:  
> For a custom format, use a camel expression in the File Name.



</td>
</tr>
<tr>
<td valign="top">

*Existing File Handling*

</td>
<td valign="top">

Select the action to take if a file with the same name already exists:

-   *Append*: Add the new content to the end of the existing file.
-   *Fail*: Stop the operation and raise an error.
-   *Ignore*: Leave the file unchanged.
-   *Override*: Replace the existing file’s content with the new one.

> ### Note:  
> For *Existing File Handling* as *Append*, if two or more processes write to the same file in append mode simultaneously, it can result in data corruption.



</td>
</tr>
<tr>
<td valign="top">

*Use Temporary File*

\(only available when *Existing File Handling* is selected as *Fail*, *Ignore*, and *Override*\)

</td>
<td valign="top">

Enable to use a temporary file name during file creation.

The data is first written to a temporary file and renamed to the final name only after the write completes successfully, preventing incomplete or corrupted files from being picked up by any other application.

</td>
</tr>
<tr>
<td valign="top">

*Temporary File Name*

\(only available when *Existing File Handling* is selected as *Fail*, *Ignore*, and *Override*\)

</td>
<td valign="top">

Specify the temporary file name.

Example: `${file:onlyname}.tmp`

> ### Note:  
> Camel file name expressions like `${file:onlyname.ext}` are also supported.

You can configure this parameter by entering a dynamic expression such as `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
</table>

