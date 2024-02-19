<!-- loio5efa3ac838e349669f3ad543fc596af6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Data Store Delete Operations

This step deletes an entry from a transient data store.



## Context

A data store operations step has to be triggered explicitly, for example, by a Timer event.

> ### Note:  
> A data store can be created during message processing using the following options:
> 
> -   Process a data store Write operation
> 
> -   Create a data store in an XI adapter \(the option *Data Store* must be selected in the *Temporary Storage* parameter\)

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



<a name="loio5efa3ac838e349669f3ad543fc596af6__steps_rsl_lyx_wx"/>

## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Persistence\), then *Data Store Operations* \> *Delete*.

2.  Place the *Delete* element in the integration process and define the message path.

3.  On the *General* tab, you can change the name of the *Delete* operation.

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
    
    Specify an entry ID that is stored together with the message content.

    Note that the delete operation can’t be used to delete whole data stores, but single entries only.

    You can also configure this parameter in such a way that details for the *Entry ID* are read from the incoming message. You can enter the following kinds of expressions to dynamically specify the entry ID:

    -   `${header.headername}`, to dynamically reference an entry ID from the message header.

    -   `${property.propertyname}`, to dynamically reference an entry ID from the exchange property of the message.

    -   `${xpath.<xpath>}`, to dynamically reference an entry ID from an element in the message indicated by an XPath expression.

        > ### Tip:  
        > For example, the message body contains customer review information for a product:
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


    You can also set the header `SapDataStoreId` to specify the *Entry ID*, and the corresponding entry are deleted at runtime.

    > ### Note:  
    > If you leave the *Entry ID* field empty, this step uses the value of the `SapDataStoreId` header \(if this header is set\).
    > 
    > If this header isn't set, this step uses the payload of the message as *Entry ID* and, if there’s an entry with an ID identical to the message payload, it's deleted. In this case, the system always takes into account the whole message payload.
    > 
    > In any way, any value specified in the *Entry ID* field takes precedence over the `SapDataStoreId` header and the message payload.


    
    </td>
    </tr>
    </table>
    
5.  Save the changes.




## Example

You can also delete multiple data store entries at once using the *Delete* step.

For example, let's assume the inbound message contains 2 customer review items, one for product Id `HT-8000` and another one for product Id `HT-1000`:

```
<CustomerReviews>
<CustomerReview>
<Comment>This product is really great. I like especially the design, speed and performance</Comment>
<CreationDate>2015-01-07T00:07:00.000</CreationDate>
<CustomerReviewId>107</CustomerReviewId>
<Rating>5</Rating>
<ProductId>HT-1000</ProductId>
</CustomerReview>
<CustomerReview>
<Comment>very good product!</Comment>
<CreationDate>2021-06-09T16:00:46.542</CreationDate>
<CustomerReviewId>125</CustomerReviewId>
<Rating>5</Rating>
<ProductId>HT-8000</ProductId>
</CustomerReview>
</CustomerReviews>

```

Let's further assume that the related data store contains entries with product Ids `HT-1000`, `HT-2000`, `HT-8000`, and many more.

If in the *Data Store Delete* step you configure the *Entry ID* with the following expression, exactly those entries with ID `HT-1000` and `HT-8000` \(that appear in the inbound message\) are deleted at once:

`${xpath./CustomerReviews/CustomerReview/ProductId/text()}`



<a name="loio5efa3ac838e349669f3ad543fc596af6__postreq_qvd_2wx_tfb"/>

## Next Steps

You can monitor the content of the data store in the *Monitor* section. Under *Manage Stores*, choose the *Data Stores* tile. For more information, see [Managing Data Stores](managing-data-stores-ac39f1d.md).

