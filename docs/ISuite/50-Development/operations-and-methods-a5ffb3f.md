<!-- loioa5ffb3f0b0e6487dbbfe7d4ebf66bd20 -->

# Operations and Methods

The following table summarizes for each product type the available operations and methods.

****


<table>
<tr>
<th valign="top">

Product Type

</th>
<th valign="top">

Operation Details

</th>
<th valign="top">

Method

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="27">

Splunk Cloud Platform

</td>
<td valign="top" rowspan="4">

Delete

</td>
<td valign="top">

Delete Data Model

</td>
<td valign="top">

Deletes specific data model.

</td>
</tr>
<tr>
<td valign="top">

Delete Saved Search

</td>
<td valign="top">

Deletes saved search by username and search name.

</td>
</tr>
<tr>
<td valign="top">

Remove Index

</td>
<td valign="top">

Removes index by index name.

</td>
</tr>
<tr>
<td valign="top">

Remove Input

</td>
<td valign="top">

Deletes token based on username and input name.

</td>
</tr>
<tr>
<td valign="top">

Patch

</td>
<td valign="top">

Modify Index

</td>
<td valign="top">

Modifies index and index properties such like size of the index, size of the buckets, frozen path and frozenTimePeriodInSecs, and so forth.

</td>
</tr>
<tr>
<td valign="top" rowspan="11">

Post

</td>
<td valign="top">

Create Data Model

</td>
<td valign="top">

Creates new data model.

</td>
</tr>
<tr>
<td valign="top">

Create Index

</td>
<td valign="top">

Creates new index.

The index is the repository for Splunk Cloud Platform data. Splunk Cloud Platform transforms incoming data into events and stores them in indexes. It furthermore processes events in indexes. An index consists of a collection of subdirectories, called buckets.

</td>
</tr>
<tr>
<td valign="top">

Create Input

</td>
<td valign="top">

Creates input by modifying global configuration.

</td>
</tr>
<tr>
<td valign="top">

Create Saved Search

</td>
<td valign="top">

Saves a search as alert and report in Splunk Cloud Platform.

</td>
</tr>
<tr>
<td valign="top">

Edit Saved Search Permissions

</td>
<td valign="top">

Sets permissions for named saved search.

</td>
</tr>
<tr>
<td valign="top">

Get Input

</td>
<td valign="top">

Gets the details of a specific input by username and input name.

</td>
</tr>
<tr>
<td valign="top">

Modify Data Model

</td>
<td valign="top">

Updates a specific data model.

</td>
</tr>
<tr>
<td valign="top">

Modify Input

</td>
<td valign="top">

Updates token configuration information.

This operation helps you to modify the token Generated \(Enable, Disable\), Change Configurations and returns the attributes of the token.

</td>
</tr>
<tr>
<td valign="top">

Modify Saved Search Properties

</td>
<td valign="top">

Modifies the saved search properties like Report description, Report permissions, Report schedule time, Schedule Priority, Time range, Trigger actions and alert description, alert permissions, alert type, trigger conditions, trigger actions.

</td>
</tr>
<tr>
<td valign="top">

Run One Shot Search

</td>
<td valign="top">

Starts a new search and returns the search ID \(<sid\>\) by providing username, search query and execution mode.

</td>
</tr>
<tr>
<td valign="top">

Run Saved Search

</td>
<td valign="top">

Runs a saved search using username and search name.

</td>
</tr>
<tr>
<td valign="top" rowspan="11">

Query

</td>
<td valign="top">

Get Applications

</td>
<td valign="top">

Lists installed apps and properties.

</td>
</tr>
<tr>
<td valign="top">

Get Data Model

</td>
<td valign="top">

Accesses a specific data model. This method helps you to get the details of a data model using the model name.

</td>
</tr>
<tr>
<td valign="top">

Get Data Models

</td>
<td valign="top">

Lists all data models on the server.

</td>
</tr>
<tr>
<td valign="top">

Get Index

</td>
<td valign="top">

Accesses related information about the index. Provides the details of an index.

</td>
</tr>
<tr>
<td valign="top">

Get Indexes

</td>
<td valign="top">

Gets list of the recognized indexes on the server. Request is Datatype and responds with Data Size, Hot buckets, Cold Buckets, Frozen Buckets, and so forth.

</td>
</tr>
<tr>
<td valign="top">

Get Inputs

</td>
<td valign="top">

Lists all inputs, including modular inputs.

</td>
</tr>
<tr>
<td valign="top">

Get Jobs

</td>
<td valign="top">

Gets details of all current searches.

</td>
</tr>
<tr>
<td valign="top">

Get Saved Search

</td>
<td valign="top">

Gets the details of Saved Searches, Parameters like Earliest Time, Latest Time, Default Arguments, and so forth.

</td>
</tr>
<tr>
<td valign="top">

Get Saved Search History

</td>
<td valign="top">

Lists available search jobs created from the \{name\} saved search.

</td>
</tr>
<tr>
<td valign="top">

Run Blocking Search

</td>
<td valign="top">

Gets information about the search job.

</td>
</tr>
<tr>
<td valign="top">

View Named Saved Search

</td>
<td valign="top">

Views the saved search properties like Report description, Report permissions, Report schedule time, Schedule Priority, Time range, Trigger actions and alert description, alert permissions, alert type, trigger conditions and trigger actions.

</td>
</tr>
<tr>
<td valign="top" rowspan="31">

Splunk Enterprise

</td>
<td valign="top" rowspan="4">

Delete

</td>
<td valign="top">

Delete Data Model

</td>
<td valign="top">

Deletes specific data model.

</td>
</tr>
<tr>
<td valign="top">

Delete Saved Search

</td>
<td valign="top">

Deletes saved search by username and search name.

</td>
</tr>
<tr>
<td valign="top">

Remove Index

</td>
<td valign="top">

Removes index by index name.

</td>
</tr>
<tr>
<td valign="top">

Remove Input

</td>
<td valign="top">

Deletes token based on username and input name.

</td>
</tr>
<tr>
<td valign="top" rowspan="15">

Post

</td>
<td valign="top">

Add Data to Index

</td>
<td valign="top">

Adds data to index by providing token and event.

</td>
</tr>
<tr>
<td valign="top">

Add Data to TCP Input

</td>
<td valign="top">

Updates the container for managing data by providing username and port no.

</td>
</tr>
<tr>
<td valign="top">

Add Data to UDP Input

</td>
<td valign="top">

Edits properties of the named UDP data input by providing username and port no.

</td>
</tr>
<tr>
<td valign="top">

Create Data Model

</td>
<td valign="top">

Creates new data model.

</td>
</tr>
<tr>
<td valign="top">

Create Index

</td>
<td valign="top">

Creates new index.

The index is the repository for Splunk Enterprise data. Splunk Enterprise transforms incoming data into events and stores them in indexes. It furthermore processes events in indexes. An index consists of a collection of subdirectories, called buckets.

</td>
</tr>
<tr>
<td valign="top">

Create Input

</td>
<td valign="top">

Creates input by modifying global configuration.

</td>
</tr>
<tr>
<td valign="top">

Create Saved Search

</td>
<td valign="top">

Saves a search as alert and report in Splunk Enterprise.

</td>
</tr>
<tr>
<td valign="top">

Edit Saved Search Permissions

</td>
<td valign="top">

Sets permissions for named saved search.

</td>
</tr>
<tr>
<td valign="top">

Enable Global Settings

</td>
<td valign="top">

Enables global settings for inputs. Specify value 0 or 1 to disable or enable it.

</td>
</tr>
<tr>
<td valign="top">

Modify Data Model

</td>
<td valign="top">

Updates specific data model

</td>
</tr>
<tr>
<td valign="top">

Modify Index

</td>
<td valign="top">

Modifies index and index properties such like size of the index, size of the buckets, frozen path and frozenTimePeriodInSecs, and so forth.

</td>
</tr>
<tr>
<td valign="top">

Modify Input

</td>
<td valign="top">

Updates token configuration information. This operation helps you to modify the token Generated \(Enable, Disable\), Change Configurations and returns the attributes of the token.

</td>
</tr>
<tr>
<td valign="top">

Modify Saved Search Properties

</td>
<td valign="top">

Modifies the saved search properties like Report description, Report permissions, Report schedule time, Schedule Priority, Time range, Trigger actions and alert description, alert permissions, alert type, trigger conditions, trigger actions.

</td>
</tr>
<tr>
<td valign="top">

Run One Shot Search

</td>
<td valign="top">

Starts a new search and returns the search ID \(<sid\>\) by providing username, search query and execution mode.

</td>
</tr>
<tr>
<td valign="top">

Run Saved Search

</td>
<td valign="top">

Runs a saved search using username and search name.

</td>
</tr>
<tr>
<td valign="top" rowspan="12">

Query

</td>
<td valign="top">

Get Applications

</td>
<td valign="top">

Lists installed apps and properties.

</td>
</tr>
<tr>
<td valign="top">

Get Data Model

</td>
<td valign="top">

Accesses a specific data model. This method helps you to get the details of a data model by providing the model name.

</td>
</tr>
<tr>
<td valign="top">

Get Data Models

</td>
<td valign="top">

Lists all data models on the server.

</td>
</tr>
<tr>
<td valign="top">

Get Index

</td>
<td valign="top">

Accesses related information about the index. Provides the details of an index.

</td>
</tr>
<tr>
<td valign="top">

Get Indexes

</td>
<td valign="top">

Gets list of the recognized indexes on the server. Request is Datatype and responds with Data Size, Hot buckets, Cold Buckets, Frozen Buckets, and so forth.

</td>
</tr>
<tr>
<td valign="top">

Get Input

</td>
<td valign="top">

Gets the details of a specific Input by username and input name.

</td>
</tr>
<tr>
<td valign="top">

Get Inputs

</td>
<td valign="top">

Lists all inputs, including modular inputs.

</td>
</tr>
<tr>
<td valign="top">

Get Jobs

</td>
<td valign="top">

Gets details of all current searches.

</td>
</tr>
<tr>
<td valign="top">

Get Saved Search

</td>
<td valign="top">

Gets the details of Saved Searches, Parameters like Earliest Time, Latest Time, Default Arguments, and so forth.

</td>
</tr>
<tr>
<td valign="top">

Get Saved Search History

</td>
<td valign="top">

Lists available search jobs created from the \{name\} saved search.

</td>
</tr>
<tr>
<td valign="top">

Run Blocking Search

</td>
<td valign="top">

Gets information about the search job.

</td>
</tr>
<tr>
<td valign="top">

View Named Saved Search

</td>
<td valign="top">

Views the saved search properties like Report description, Report permissions, Report schedule time, Schedule Priority, Time range, Trigger actions and alert description, alert permissions, alert type, trigger conditions and trigger actions.

</td>
</tr>
</table>

> ### Note:  
> For more information on IP address ranges to be used to configure a Splunk instance, see [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/f344a57233d34199b2123b9620d0bb41.html).

