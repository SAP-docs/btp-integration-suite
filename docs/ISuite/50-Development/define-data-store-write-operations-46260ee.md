<!-- loio46260ee193ed48f48a9bd5b855861e4d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Data Store Write Operations

This step performs a Write operation on the transient data store.



## Context

A data store operations step has to be triggered explicitly, for example, by a Timer event.

This component stores data on your tenant. Note that the tenant space is limited and shared with other tenant data like message processing logs.

> ### Tip:  
> For more information about the data store component and guidelines when to use it, see:
> 
> -   [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md)
> 
> -   [Data Store/Variables Versus Header/Properties: When to Use Which Option?](data-store-variables-versus-header-properties-when-to-use-which-option-61f4045.md)
> 
> -   [Data Store, Variables, and JMS Queues: When to Use Which Option?](data-store-variables-and-jms-queues-when-to-use-which-option-6bc21cb.md)
> 
> 
> For examples, see: [Examples](examples-c8ba267.md)



<a name="loio46260ee193ed48f48a9bd5b855861e4d__steps_rsl_lyx_wx"/>

## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Persistence\), then *Data Store Operations* \> *Write*.

2.  Place the *Write* element in the integration process and define the message path.

3.  On the *General* tab, you can change the name of the *Write* operation.

4.  On the *Processing* tab, define the attributes of the data store operation based on the descriptions in the following table. The set of attributes depends on the chosen operation.


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Data Store Name* 
    
    </td>
    <td valign="top">
    
    Specifies the name of the data store \(no white spaces\).

    The maximum length allowed for the data store name is 40 characters. If you enter a longer string, a validation error is raised. Note that this length restriction applies to the value that is used for this parameter at runtime. Therefore, if you configure this parameter dynamically, make sure that the expected header or property value does not exceed this length restriction. Otherwise, a runtime error will be raised.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Visibility* 
    
    </td>
    <td valign="top">
    
    Defines whether the data store is shared by all integration flows \(deployed on the tenant\) or only by one specific integration flow.

    -   *Global*: Data store is shared across all integration flows deployed on the tenant.

    -   *Integration Flow*: Data store is used by 1 integration flow. A data store configured with this setting is also referred to as local data store.


    For more information and guidelines how to use this parameter, see [Anticipate Message Throughput When Choosing a Storage Option](anticipate-message-throughput-when-choosing-a-storage-option-5b38765.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Entry ID* 
    
    </td>
    <td valign="top">
    
    Specify an entry ID that is stored together with the message content. The entry ID must not exceed 255 characters.

    Details for the entry ID are read from the incoming message. You can enter the following kinds of expressions:

    -   `${header.headername}`, to dynamically generate the entry ID from the message header.

    -   `${property.propertyname}`, to dynamically generate the entry ID from the exchange property of the message.

    -   `${xpath.<xpath>}`, to dynamically generate the entry ID from an element in the message indicated by an xPath expression.

        > ### Tip:  
        > For example, the message body contains customer review information for an individual product:
        > 
        > ```
        > <CustomerReviews>
        > <CustomerReview>
        > <CreationDate>2021-06-09T16:00:46.542</CreationDate>
        > <CustomerReviewId>125</CustomerReviewId>
        > <Rating>5</Rating>
        > <ProductId>HT-8000</ProductId>
        > </CustomerReview>
        > </CustomerReviews>
        > 
        > ```
        > 
        > If you like to set the related `ProductId` value as *Entry ID*, use the following XPath expression:
        > 
        > `${xpath./CustomerReviews/CustomerReview/ProductId/text()}`


    If you leave the *Entry ID* field empty, this step uses the value of the `SapDataStoreId` header \(if this header is set\).

    If this header is not defined, this step generates an entry ID and sets the `SapDataStoreId` header with the generated value.

    > ### Tip:  
    > If you like the system to *generate* an entry ID for the data store operation, remove the header `SapDataStoreId` before the data store write step and leave the *Entry ID* field in the data store empty.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Retention Threshold for Alerting in \(d\)* 
    
    </td>
    <td valign="top">
    
    Time period \(in days\) within which the messages have to be fetched before an alert is raised.

    Raising an alert means that the corresponding entry in the data store monitor gets the status *Overdue* \(indicated with red color\).

    You can open the data store monitor by selecting the *Data Stores* tile in the *Operations* view of the Web UI under *Manage Stores*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Expiration Period in \(d\)* 
    
    </td>
    <td valign="top">
    
    Number of days after which the stored messages are deleted \(default is 30 days, maximum possible value is 180 days\).

    The minimum value of *Expiration Period* should be at least twice that of *Retention Threshold for Alerting*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Encrypt Stored Message* 
    
    </td>
    <td valign="top">
    
    Select this option to encrypt the message in the data store.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Overwrite Existing Message* 
    
    </td>
    <td valign="top">
    
    Select this option to overwrite an existing message in the data store.

    Trying to overwrite an existing entry without having this option selected results in a `DuplicateEntryException`.

    > ### Caution:  
    > In rare cases, selecting this option may still lead to a `DuplicateEntryException`. For more information, see [2982524](https://me.sap.com/notes/2982524).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Include Message Headers* 
    
    </td>
    <td valign="top">
    
    Select this option to store message headers in addition to the payload.

    > ### Note:  
    > `Camel*` and `SAP_*` headers won't be stored.

    > ### Note:  
    > Only select this option if you want to read the message afterwards by retrieving it with *Get* operations.

    > ### Caution:  
    > Consider that all headers will be stored and it may take up a lot of space.


    
    </td>
    </tr>
    </table>
    
5.  Save the changes.




<a name="loio46260ee193ed48f48a9bd5b855861e4d__postreq_eqk_dwx_tfb"/>

## Next Steps

Be aware of the following fact when you plan to execute a data store. Select an operation in a subsequent integration flow step: When retrieving a message body from a data store in a subsequent step, only XML is supported.

The only option to read non-XML data is provided by the data store Get operation.

You can monitor the content of the data store in the *Monitor* section. Under *Manage Stores*, choose the *Data Stores* tile. For more information, see [Managing Data Stores](managing-data-stores-ac39f1d.md).

> ### Note:  
> If a Datastore Write step fails because the entry already exists \(duplicate key exception\), this exception can't be handled by an Exception subprocess. The reason is that the database transaction is rolled back even if an Exception subprocess is used.

