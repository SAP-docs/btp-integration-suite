<!-- loio7279d38ad1a4496b93098b56b29d215b -->

# Key Performance Indicators for Archiving Runs

In addition to archiving MPLs, the system job also records specific Key Performance Indicators \(KPIs\) of the archiving runs.

You can use these indicators, for example, to check for recurring errors, or potential performance problems. Use the official OData API to query the KPIs.

**List of Job KPIs**


<table>
<tr>
<th valign="top">

Key Performance Indicators

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`RunStart`

</td>
<td valign="top">

Date and time when the archiving run started.

</td>
</tr>
<tr>
<td valign="top">

`RunDurationInMinutes`

</td>
<td valign="top">

Duration of an archiving run \(in minutes\).

</td>
</tr>
<tr>
<td valign="top">

`DataCollectionDurationInMinutes`

</td>
<td valign="top">

Total time needed to collect the data from relevant data stores \(in minutes\).

</td>
</tr>
<tr>
<td valign="top">

`DataCompressionDurationInMinutes`

</td>
<td valign="top">

Total time needed to compress the uploaded data \(in minutes\).

</td>
</tr>
<tr>
<td valign="top">

`DataUploadDurationInMinutes`

</td>
<td valign="top">

Total time needed to upload the data to the CMS \(in minutes\).

</td>
</tr>
<tr>
<td valign="top">

`MplsToBeArchived`

</td>
<td valign="top">

Number of archiving relevant message processing logs \(MPLs\).

</td>
</tr>
<tr>
<td valign="top">

`MplsArchived`

</td>
<td valign="top">

Number of archived MPLs. MPLs already uploaded by a previous run, but not yet flagged as archived, are counted as well.

</td>
</tr>
<tr>
<td valign="top">

`MplsArchivingFailed`

</td>
<td valign="top">

Number of errors that occurred during archiving MPLs. This number includes only errors occurring during preparation of upload and upload of MPLs. Errors leading to the failure of the job run excluded.

> ### Note:  
> The number of `MplsToBeArchived` and the number of `MplsArchivingFailed` **\+** `MplsArchived` can differ, if the archiving job ends with status `FAILED`.



</td>
</tr>
<tr>
<td valign="top">

`MplsArchivedUntilDate`

</td>
<td valign="top">

The date until which MPLs are considered as being archiving relevant for this job run. All MPLs matching the date or older are archived.

</td>
</tr>
<tr>
<td valign="top">

`DateOfOldestMplToBeArchivedAfterRun`

</td>
<td valign="top">

Date of the oldest MPLwhich is still archiving relevant after the run. \(If all MPLs have been archived, this value is `null`\).

</td>
</tr>
<tr>
<td valign="top">

`DataUploadedInMb`

</td>
<td valign="top">

Total volume of uploaded data in megabytes

</td>
</tr>
<tr>
<td valign="top">

`RunStatus`

</td>
<td valign="top">

Status of the job run. Possible values are:`COMPLETED` and `FAILED`.

> ### Note:  
> Status `COMPLETED` doesn't indicate, that no errors occurred during the archiving process. It only states, that the job run without any error causing the job run to end prematurely.



</td>
</tr>
<tr>
<td valign="top">

`RunFailedPhase`

</td>
<td valign="top">

Job phase in which the run failed. The job run is divided into 2 phases: `INITIALIZATION` and `EXECUTION`.

> ### Note:  
> If the `RunStatus` is `COMPLETED`, this indicator is null.

If the job fails during `INITIALIZATION`, some necessary resources during this phase, such as reading values from the destination, run into an error.

In this case,

-   Check if the configuration of your destination is correct.

-   Check if you can successfully connect to the repository,
-   If you use SAP Cloud Connector, check that the configuration of the SAP Cloud Connector is correct. Assure that the SAP Cloud Connector exposes the resources required.
-   Check that the credentials configured in the destination enable the connection to the repository. Assure that the user has all the necessary authorisations for the required operations on the repository.

If the job fails during the `EXECUTION` phase, an error occurred either during retrieval, compression, or uploading of the data.

In this case,

-   Check your repository logs for any recurring errors.

-   Check if the error occurs only once or if it occurs in multiple runs in succession.



</td>
</tr>
</table>

**How to query the Key Performance Indicators.**

You can query the KPIs with the same OData API used to query the Message Processing Logs: `ArchivingKeyPerformanceIndicators` with `RunStart` as primary key.

> ### Example:  
> The following query is an example where the query filter for all entries with `MplsToBeArchived` = `5000`.
> 
> Request Method: `GET`
> 
> Request URL:`https://path-to-odata-api/api/v1/ArchivingKeyPerformanceIndicators?$filter=MplsToBeArchived eq 5000`
> 
> > ### Sample Code:  
> > ```
> > <entry>
> >         …
> >         <content type="application/xml">
> >             <m:properties>
> >                 <d:RunStart>2021-04-30T13:37:00.243</d:RunStart>
> >                 <d:RunDurationInMinutes>11</d:RunDurationInMinutes>
> >                 <d:DataCollectionDurationInMinutes>7</d:DataCollectionDurationInMinutes>
> >               <d:DataCompressionDurationInMinutes>0</d:DataCompressionDurationInMinutes>
> >                 <d:DataUploadDurationInMinutes>2</d:DataUploadDurationInMinutes>
> >                 <d:MplsToBeArchived>5000</d:MplsToBeArchived>
> >                 <d:MplsArchived>4999</d:MplsArchived>
> >                 <d:MplsArchivingFailed>1</d:MplsArchivingFailed>
> >                 <d:MplsArchivedUntilDate>2021-04-30T13:47:47.996</d:MplsArchivedUntilDate>
> >    <d:DateOfOldestMplToBeArchivedAfterRun>
> >     2021-04-30T13:34:54.183
> >    </d:DateOfOldestMplToBeArchivedAfterRun>
> >                 <d:DataUploadedInMb>130</d:DataUploadedInMb>
> >                 <d:RunStatus>COMPLETED</d:RunStatus>
> >                 <d:RunFailedPhase m:null="true"/>
> >             </m:properties>
> >         </content>
> >     </entry>
> > 
> > ```

