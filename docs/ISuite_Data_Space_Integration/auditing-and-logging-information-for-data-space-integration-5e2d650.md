<!-- loio5e2d65076ea549589b088e2af765c316 -->

# Auditing and Logging Information for Data Space Integration

Here you can find a list of the security events that are logged by Data Space Integration.

**Security events written in audit logs**


<table>
<tr>
<th valign="top">

Event grouping

</th>
<th valign="top">

What events are logged

</th>
<th valign="top">

How to identify related log events

</th>
<th valign="top">

Additional information

</th>
</tr>
<tr>
<td valign="top">

Events within Data Space Integration

</td>
<td valign="top">

-   Registration of a connector

-   Retrieval of a connector's registration information




</td>
<td valign="top">

uriInfo: `registration`

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Events within Data Space Integration 

</td>
<td valign="top">

-   Registration of a technical user

-   Retrieval of a technical user




</td>
<td valign="top">

uriInfo: `credentials/technicaluser`

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Events within Data Space Integration 

</td>
<td valign="top">

-   Registration of data plane credentials

-   Retrieval of data plane credentials




</td>
<td valign="top">

uriInfo: `credentials/dataplane`

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Events within Data Space Integration 

</td>
<td valign="top">

-   Registration of dynamic callback credentials

-   Deletion of dynamic callback credentials




</td>
<td valign="top">

uriInfo: `credentials/callback`

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Events within Data Space Integration 

</td>
<td valign="top">

-   Deployment of integration content

-   Retrieval of integration content status




</td>
<td valign="top">

uriInfo: `dataplane`

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Management events

</td>
<td valign="top">

Creation, update, deletion, and retrieval of assets

</td>
<td valign="top">

uriInfo:

-   `v3/assets` or
-   `v3/assets/request`



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Management events

</td>
<td valign="top">

Creation, update, deletion, and retrieval of policy definitions

</td>
<td valign="top">

uriInfo:

-   `v2/policydefinitions` or
-   `v2/policydefinitions/request`



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Management events

</td>
<td valign="top">

Creation, update, deletion, and retrieval of contract definitions

</td>
<td valign="top">

uriInfo:

-   `v2/contractdefinitions` or
-   `v2/contractdefinitions/request`



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Management events

</td>
<td valign="top">

Retrieval of catalogs

</td>
<td valign="top">

uriInfo: `v2/catalog/request` 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Management events

</td>
<td valign="top">

-   Initiation of contract negotiations

-   Retrieval of contract negotiations

-   Retrieval of contract negotiation state

-   Termination of contract negotiations




</td>
<td valign="top">

uriInfo:

-   `v2/contractnegotiations` or
-   `v2/contractnegotiations/request` or
-   `v2/contractnegotiations/{{negotiationId}}/state` or
-   `v2/contractnegotiations/{{negotiationId}}/terminate`



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Management events

</td>
<td valign="top">

-   Retrieval of contract agreements

-   Retrieval of contract negotiations by contract agreement IDs




</td>
<td valign="top">

uriInfo:

-   `v2/contractagreements` or
-   `v2/contractnegotiations/request` or
-   `v2/contractnegotiations/{{agreementId}}/negotiation`



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Management events

</td>
<td valign="top">

-   Initiation of transfer processes

-   Retrieval of transfer processes

-   Retrieval of the state of transfer processes

-   Deprovisioning of transfer processes

-   Termination of transfer processes

-   Completion of transfer processes




</td>
<td valign="top">

uriInfo:

-   `v2/transferprocesses` or
-   `v2/transferprocesses/request` or
-   `v2/transferprocesses/{{transferprocessId}}/state` or
-   `v2/transferprocesses/{{transferprocessId}}/deprovision` or
-   `v2/transferprocesses/{{transferprocessId}}/terminate` or
-   `v2/transferprocesses/{{transferprocessId}}/complete`



</td>
<td valign="top">

 

</td>
</tr>
</table>



The following information is described in the table columns:

-   *Event grouping* - Events that are logged with a similar format or are related to the same entities.

-   *What events are logged* - Description of the security or data protection and privacy-related event that is logged.

-   *How to identify related log events* - Search criteria or key words that are specific for a log event that is created along with the logged event.

-   *Additional information* - Any related information that can be helpful.


**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

