<!-- loio232ac4601f5c40999cc40fe96e62aaf4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Data Store Get Operations

This step gets a specific entry from the transient data store.



## Context

A data store operations step has to be triggered explicitly, for example, by a Timer event.

> ### Note:  
> A data store can be created during message processing using the following options:
> 
> -   Process a data store Write operation
> 
> -   Create a data store in an XI adapter \(the option *Data Store* must be selected in the *Temporary Storage* parameter\)

> ### Caution:  
> This step overwrites the body of the input message.

> ### Note:  
> From component version 1.5 onwards, the *Created At* \(header: `SAP_DataStoreCreatedAt`\) and *Retain Until* \(header: `SAP_DataStoreExpiresAt`\) timestamps of the data store entry are included in the message.

> ### Tip:  
> For more guidelines about how to use the data store component, see:
> 
> -   [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md)
> 
> -   [Data Store/Variables Versus Header/Properties: When to Use Which Option?](data-store-variables-versus-header-properties-when-to-use-which-option-61f4045.md)
> 
> -   [Data Store, Variables, and JMS Queues: When to Use Which Option?](data-store-variables-and-jms-queues-when-to-use-which-option-6bc21cb.md)
> 
> 
> For more information, see: [Examples](examples-c8ba267.md)



<a name="loio232ac4601f5c40999cc40fe96e62aaf4__steps_rsl_lyx_wx"/>

## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Persistence\), then *Data Store Operations* \> *Get*.

2.  Place the *Get* element in the integration process and define the message path.

3.  On the *General* tab, you can change the name of the *Get* operation.

4.  On the *Processing* tab, define the attributes of the data store operation based on the descriptions in the following table. The set of attributes depends on the operation chosen.


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

    -   *Integration Flow*: Data store is used by one integration flow. A data store configured with this setting is also referred to as local data store.


    For more information and guidelines how to use this parameter, see [Anticipate Message Throughput When Choosing a Storage Option](anticipate-message-throughput-when-choosing-a-storage-option-5b38765.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Entry ID* 
    
    </td>
    <td valign="top">
    
    Specify an entry ID that is stored together with the message content.

    Details for the entry ID are read from the incoming message. You can enter the following kinds of expressions to dynamically specify the entry ID:

    -   `${header.headername}`, to dynamically generate the entry ID from the message header.

    -   `${property.propertyname}`, to dynamically generate the entry ID from the exchange property of the message.

    -   `${xpath.<xpath>}`, to dynamically generate the entry ID from an element in the message indicated by an xPath expression.

        Example: `${xpath./CustomerReviews/CustomerReview/ProductId}`


    You can also set the header `SapDataStoreId` to specify the *Entry ID*, and the corresponding entry is read at runtime.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Delete on Completion* 
    
    </td>
    <td valign="top">
    
    Select this option to delete a message from the data store after having successfully processed the message.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Throw Exception on Missing Entry*
    
    </td>
    <td valign="top">
    
    You have the option to throw an exception if the entry with the specified *Entry ID* does not exist in the datastore.

    This checkbox is selected by default.

    > ### Remember:  
    > If you disable this option, the header `SAP_DatastoreEntryFound` is set to false and no exception is thrown, even if the *Entry ID* does not exist.


    
    </td>
    </tr>
    </table>
    
5.  Save the changes.




<a name="loio232ac4601f5c40999cc40fe96e62aaf4__postreq_etr_cwx_tfb"/>

## Next Steps

You can monitor the content of the data store in the *Monitor* section. Under *Manage Stores*, choose the *Data Stores* tile. For more information, see [Managing Data Stores](managing-data-stores-ac39f1d.md).

