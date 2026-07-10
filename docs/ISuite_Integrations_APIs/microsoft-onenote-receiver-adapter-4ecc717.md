<!-- loio4ecc717b679b427ebf58d7470edb1ac6 -->

# Microsoft OneNote Receiver Adapter

Use M365 OneNote Receiver Adapter to connect directly with the M365 Graph API v1.0 and access the OneNote functionality with seamless integration. This adapter automates common business operations by integrating MS OneNote with other business applications. It connects an SAP Integration Suite tenant to a remote system using HTTP protocol.

The Microsoft OneNote Receiver adapter helps use various product features from OneDrive such as Drive, Drive Item, Permissions, Sharing, Content, and Batching. For more information, see [Access OneNote via Microsoft Graph API - OneNote Dev Center | Microsoft Learn](https://learn.microsoft.com/en-us/graph/api/resources/onenote-api-overview?view=graph-rest-1.0&preserve-view=true).

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you've created a receiver channel and selected the **Microsoft OneNote** receiver adapter, you can configure the following attributes.

Select the *General* tab to access the following parameters.

****


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

*Name*

</td>
<td valign="top">

Name of the Microsoft OneNote Storage adapter.

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type*

</td>
<td valign="top">

Microsoft OneNote

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol*

</td>
<td valign="top">

HTTP/HTTPS

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol*

</td>
<td valign="top">

REST

</td>
</tr>
<tr>
<td valign="top">

*Description*

</td>
<td valign="top">

Find useful information which describes the adapter.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

****


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

*Site Host Name*

</td>
<td valign="top">

Enter the host name of the Microsoft OneNote account.

> ### Example:  
> `cloudintegrationmail2.sharepoint.com`



</td>
</tr>
<tr>
<td valign="top">

*Server Relative Path*

</td>
<td valign="top">

Enter server relative path of the Microsoft OneNote account.

> ### Example:  
> `/teams/OneNoteAdapter`



</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication type. Supported types are:

-   *OAuth2 Authorization Code*
-   *Dynamic*

    You must define the authentication method in the message exchange using the property `SAP_SharePointAuthMethod`. Supported value is:

    -   oAuth2AuthorizationCode


    If you select *Dynamic* and don't define the property, a runtime error occurs.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Enter the alias name of the deployed user credentials artifact.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

Select proxy type. Supported types are:

-   *Internet*
-   *Dynamic*

    Select *Internet* as proxy type to connect to the Cloud server.

    If you select *Dynamic* and don't define the property `SAP_OneNoteAuthMethod` in Content Modifier, a runtime error occurs.

    Supported value is *internet*.




</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)*

</td>
<td valign="top">

Enter the maximum waiting time, in milliseconds, to contact the Microsoft OneNote server while establishing a connection or performing a read operation. The default value is 60000.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

****


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Sub Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top" rowspan="5">

*Operation Group*

</td>
<td valign="top">

Notebooks

</td>
<td valign="top">

Select one of the operations:

-   *Create Notebook*: Create a notebook by posting to the notebooks collection.
-   *List Notebooks*: Get a collection of notebooks.
-   *Get Notebook*: Retrieve the properties and relationships of a notebook object.
-   *Create Section*: Create a new OneNote Section in the specified notebook.
-   *List Sections*: Retrieve a list of OneNote Section objects from the specified notebook.
-   *Create Section Group*: Create a new section group in the specified notebook.
-   *List Section Groups*: Retrieve a list of section groups from the specified notebook.
-   *Copy Notebook*: Copies a notebook to the Notebooks folder in the destination Documents library. The folder is created if it doesn't exist.



</td>
</tr>
<tr>
<td valign="top">

Section

</td>
<td valign="top">

Select one of the operations:

-   *List Sections*: Retrieve a list of OneNote Section objects.
-   *Get Section*: Retrieve the properties and relationships of a OneNote Section object.
-   *Create Page*: Create a new page in the specified section.
-   *List Pages*: Retrieve a list of page objects from the specified section.
-   *Copy to Notebook*: `microsoft.graph` copies a section to a specific notebook.
-   *Copy to Section Group*: `microsoft.graph` copies a section to a specific section group.



</td>
</tr>
<tr>
<td valign="top">

Section Group

</td>
<td valign="top">

Select one of the operations:

-   *Get Section Group*: Retrieve the properties and relationships of a Section-Group object.
-   *List Section Groups*: Retrieve a list of Section-Group objects.
-   *List Sections*: Retrieve a list of OneNote Section objects from the specified section group.
-   *Create Section*: Create a new OneNote Section in the specified section group.



</td>
</tr>
<tr>
<td valign="top">

Pages

</td>
<td valign="top">

Select one of the operations:

-   *Create Page*: This operation allows you to create a page in section specified, which is in the default notebook only

    > ### Note:  
    > This operation does not support creating pages in any notebooks other than the default one.
    > 
    > If you have mulitple notebooks and need to set a default notebook in OneNote,
    > 
    > -   Open *OneNote File* \> *File* \> *Options* \> *Save & Backup* \> *Default Notebook Location* \> *Modify Location* \> *OK*.

    To identify Default notebook in a sharepoint site use List Notebooks URL -`> /sites/{siteId}/onenote/notebooks?$filter=isDefault eq true`. The default notebook only will have the field *isDefault* as true

-   *Get Page*: Retrieve the properties and relationships of a page object.
-   *Update Page*: Update the content of a OneNote page.
-   *Delete Page*: Delete a OneNote page.
-   *Copy to Section*: Copy a page to a specific section.



</td>
</tr>
<tr>
<td valign="top">

Batching

</td>
<td valign="top">

Select the below operation: *Batch*: JSON batching allows you to optimize your application by combining multiple requests \(up to 20\) into a single JSON object.

Combining these ‘n’ individual requests into a single batch request can save the application significant network latency.

> ### Note:  
> Can be combined up to 20 calls only in request body.



</td>
</tr>
<tr>
<td valign="top">

*Operation Name*

</td>
<td valign="top" colspan="2">

Operation name is selected according to requirement from above options.

</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top" colspan="2">

Enter the query parameter to filter the search results. Syntax: `searchindex=indexname`.

> ### Example:  
> -   `$top=10`
> 
> -   `$skip=10`
> 
> -   `$filter=Price gt 100`
> 
> -   `$select=Name,Price&$top=3`



</td>
</tr>
<tr>
<td valign="top">

*Notebook Name*

</td>
<td valign="top" colspan="2">

Enter the Notebook name for the following purposes:

-   To create a new OneNote notebook.
-   To get the OneNote notebook Object.
-   To perform some operations in OneNote depends on the operation chosen.



</td>
</tr>
<tr>
<td valign="top">

*Section Name*

</td>
<td valign="top" colspan="2">

Enter Section Name for the following purposes:

-   To create a new OneNote Section.
-   To get the OneNote Section Object.
-   To perform some operations in OneNote depends on the operation chosen.



</td>
</tr>
<tr>
<td valign="top">

*Section Group Name*

</td>
<td valign="top" colspan="2">

Enter the Section Group name for the following purposes:

-   To create a new OneNote Section Group.
-   To get the OneNote Section Group Object.
-   To perform some operations in OneNote depends on the operation chosen.



</td>
</tr>
<tr>
<td valign="top">

*Page Name*

</td>
<td valign="top" colspan="2">

Enter Page Name for the following purposes:

-   To create a new OneNote Page.
-   To get the OneNote Page Object.
-   To perform some operations in OneNote depends on the operation chosen.



</td>
</tr>
<tr>
<td valign="top">

*Source Notebook Name*

</td>
<td valign="top" colspan="2">

Enter the name of the notebook to be read.

</td>
</tr>
<tr>
<td valign="top">

*Target Notebook Name*

</td>
<td valign="top" colspan="2">

Enter name of the notebook that must be placed in the target.

</td>
</tr>
<tr>
<td valign="top">

*Source Section Name*

</td>
<td valign="top" colspan="2">

Enter the name of the section to be read.

</td>
</tr>
<tr>
<td valign="top">

*Target Section Name*

</td>
<td valign="top" colspan="2">

Enter the name of the section that must be placed in the target.

</td>
</tr>
<tr>
<td valign="top">

*Target Section Group Name*

</td>
<td valign="top" colspan="2">

Enter the name of the Section Group that must be placed in the target.

</td>
</tr>
<tr>
<td valign="top">

*Content Type*

</td>
<td valign="top" colspan="2">

Specify the content type in input section.

> ### Example:  
> -   `text/html`
> -   `Page_CreatePage- text/html`
> -   `Page_UpdatePage- application/json`



</td>
</tr>
<tr>
<td valign="top">

*Page Size*

</td>
<td valign="top" colspan="2">

Specify the page size in input section.

</td>
</tr>
<tr>
<td valign="top">

*Process in Page*

</td>
<td valign="top" colspan="2">

Select to enable the adapter to process messages in batches. The size of a message is defined by the value that you specify for the *Page Size*.

You can select one of the following from the dropdown list:

-   *Not Required*
-   *Required*
-   *Dynamic*

    > ### Note:  
    > If you select dynamic then define value in property as `SAP_OneNote_Process_In_Pages`. Values can be required or notRequired




</td>
</tr>
<tr>
<td valign="top">

*Response Format*

</td>
<td valign="top" colspan="2">

Select one of the values:

-   JSON
-   XML
-   Dynamic

You must define the value ‘json’ or ‘xml’ in the message exchange using the property `SAP_OneNoteOutboundResponseFormat`.

</td>
</tr>
<tr>
<td valign="top">

*Additional Arguments*

</td>
<td valign="top" colspan="2">

You can pass additional arguments as key-value pair in this section.

</td>
</tr>
<tr>
<td valign="top">

*Request Header*

</td>
<td valign="top" colspan="2">

Pipe separated list of HTTP request headers to be sent to the Microsoft OneNote target system.

> ### Example:  
> |Content-Type|Accept
> 
> -   `Content-Type: application/json`
> -   `Accept: application/json`



</td>
</tr>
<tr>
<td valign="top">

*Response Header*

</td>
<td valign="top" colspan="2">

Pipe separated list of HTTP response headers. The specified headers from Microsoft OneNote target system are received in the message exchange.

> ### Example:  
> Location|Retry-After
> 
> -   `Location`: URL of uploaded file.
> -   `Retry-After`: If OneNote asks to wait before retrying.



</td>
</tr>
</table>

> ### Note:  
> The OneNote adapter supports dynamic configurations of fields with the help of Content Modifier, [Define Content Modifier](define-content-modifier-8f04a70.md). The fields can be set with syntax $\{header.fieldname\} or $\{property.fieldname\} and the values can be set under the Content Modifier under message headers or exchange properties section.
> 
> In case of post call at the receiver side, the request body needs to be passed under the message body section.

