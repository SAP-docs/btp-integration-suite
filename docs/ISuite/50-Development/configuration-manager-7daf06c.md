<!-- loio7daf06ceece84dc09d3ca63fc62d0a61 -->

# Configuration Manager



<a name="loio7daf06ceece84dc09d3ca63fc62d0a61__section_x2f_xb2_jzb"/>

## Custom Search Attributes

The *B2B Scenarios* tab under the *Monitor* section allows you to monitor the interchanges that are created during a B2B transaction. The interchanges are displayed in a list with a list of filters using which helps you find a specific interchange easily. These search filters are provided in a standard format. There could be scenarios where you need to search for an interchange using a filter that is not provided in general. In such cases, the *Configuration Manager* allows you to create and use custom search fields. To do so, follow the procedure below:

1.  Login to your application and navigate to *Design* \> *B2B Scenarios*.

2.  Select the *Configuration Manager* tab and choose *Create* to create your custom search attribute.

    > ### Note:  
    > You can create a maximum of 10 custom search attributes.

3.  Enter a meaningful name in the *Name* field and provide a description in the *Description* field.
4.  Choose *Save*. The custom search attribute has been created successfully.

After creating your custom attribute, you need to assign these attributes to a transaction for it to reflect in the B2B monitor. To know more, see [Creating a Trading Partner Agreement](creating-a-trading-partner-agreement-9bd43c9.md).

*How are the custom search attributes consumed*

Once your create and define the custom search attributes, you need to use them in the necessary B2B transacations in an agreement. These attributes are then pushed into the partner directory upon activation of the agreement. The incoming payload consists of the search values in XPath format and when the payload is parsed, the values are read and displayed in the B2B monitor.



<a name="loio7daf06ceece84dc09d3ca63fc62d0a61__section_y5v_1rb_bzb"/>

## Maximum Retry Count

The integration flows once deployed, run the transaction activity and try to deliver the message. Sometimes, they fail due to unknown errors. In such cases, you can provide an option to re-trigger the integration flows. With *Maximum Retry Count*, you can now define the maximum number of retries for failed integration flows. This is applicable for *Step 2 - Interchange Processing Flow* and *Step 3 - Receiver Communication Flow*. Follow the procedure below to know how to maintain the retry entries.

1.  Navigate to the *Configuration Manager* in your application.

2.  In the *Maximum Retry Count* section, choose *Edit*.
3.  Set the *Maximum Retry* count for the fields *Interchange Processing Flow* and *Receiver Communication Flow*.
4.  Choose *Save*. Saving the values will immediately push the data into Partner Directory. Choose *OK*.

