<!-- loio8a7669222a864ad4b6f1ad4f66b3b316 -->

# Reduce Size of OData Content Enricher Response

The *Content Enricher* step allows you to add missing information to a message by calling an external service. This step matches the key elements of the original message to the key elements of the so-called lookup message, and this way adds the missing information at the right location of the original message.

Depending on your content enricher query, the lookup call pulls the complete list of missing data also if only a subset is needed. If the size of the lookup response message is large, the performance of the scenario can be degraded.

This guideline shows you how to dynamically modeling the query in such a way that only the relevant information is read. Implementing this guideline allows you to improve the efficiency of the content enricher step.

For a detailed description of the Content Enricher, see [Define Content Enricher](define-content-enricher-8827f9f.md).

For another example of an improved modeling of the content enricher, see the following SAP Community blog: [Handling Large Data with Content Enricher and OData v2 adapter](https://blogs.sap.com/2019/11/08/handling-large-data-with-content-enricher-and-odata-v2-adapter/).



<a name="loio8a7669222a864ad4b6f1ad4f66b3b316__section_omh_5r1_lpb"/>

## Implementation

The scenario is based on the [Content Enricher](content-enricher-0e7ba7f.md) Enterprise Integration Pattern. This pattern adds missing main category information to an order with multiple items, each item referring to a product and a product category. In the implementation of this pattern, the *Content Enricher* step reads the missing data from a demo WebShop application. Using the OData protocol, the complete list of product categories is gathered.

In the *Relax Dependencies - OData Content Enricher* integration flow, the [Content Enricher](content-enricher-0e7ba7f.md) pattern integration flow has been enhanced by adding a filter to the OData query of the *Content Enricher* step so that only the relevant product categories are returned. In an additional Groovy script right before the content enricher, the filter is defined based on the product categories referred to in the order. The rest of the integration flow model remains unchanged.

![](images/Content_Enricher_Filter_dda1e81.png)

The Groovy script is defined in the following way:

```
import com.sap.gateway.ip.core.customdev.util.Message;
import java.util.HashMap;
def Message processData(Message message) {
    //Body 
    def body = message.getBody();
       
    //Parse message body to fetch keys
    def bodyTree = new XmlSlurper().parse(body);
    def categoryList = bodyTree.'**'.findAll{ node-> node.name() == 'Category' }*.text();

    //Define filter
    if(categoryList.isEmpty()){
        message.setProperty("filter", "");
    } else{
        def filter = "Category eq '" + categoryList.unique().join("' or Category eq '") + "'";
        message.setProperty("filter", "\$filter=" + filter);
    }
    
    return message;
}
```

The original message is parsed using `XmlSlurper`. All key elements with name `Category` are stored in a list. Based on this category list, the filter is concatenated, and at the end assigned to the exchange property filter.

The *Query Options* parameter of the OData channel \(tab *Processing*\) is specified in the following way:

`$select=Category,MainCategoryName&${property.filter}`

Note that the expression `&${property.filter}` is added at the end of the query options.



<a name="loio8a7669222a864ad4b6f1ad4f66b3b316__section_fvh_mt1_lpb"/>

## Executing the Scenario

As prerequisite, make sure that both the integration flow *Relax Dependencies - OData Content Enricher* and *Generic Receiver* are deployed. The integration flows are provided in integration package [Integration Flow Design Guidelines - Relax Dependencies to External Components](https://api.sap.com/package/DesignGuidelinesRelaxDependenciestoExternalComponents?section=Overview).

If you use Postman together with the Postman collection provided with the package, expand the collection folder `ODataContentEnricher`. You find 2 requests.

Since all integration flows are CSRF-protected, you first need to run the `HEAD` request to fetch a token before posting the actual data.

If you run the `ODataContentEnricher` POST request, message processing runs successfully. In the data store, you find a new data store *RelaxDependencies-ContentEnricher* with a new entry containing the enriched message.

If you like to ensure that the filter has been correctly set, switch on the *Trace* log level, and rerun the scenario \(see [Setting Log Levels](setting-log-levels-4e6d3fc.md)\). In the trace, check the value of the exchange property filter. With the message body provided in the Postman collection, the filter is defined as follows:

`$filter=Category eq 'Notebooks' or Category eq 'Flat screens' or Category eq 'Software'.`

