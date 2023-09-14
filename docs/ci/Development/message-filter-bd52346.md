<!-- loiobd523460894744a8be6b7bbe3351f795 -->

# Message Filter

You can use the Message Filter pattern to remove any data from a channel that you aren't interested in.

Let's assume that you want to send product information to an inventory system, but the inventory system only handles a subset of the range of products, depending on the product category. You can use the Message Filter pattern to remove any data from a channel that you aren't interested in. The Message Filter is a specific type of the Message Router pattern that has only one single receiver channel. Any incoming message is evaluated, and if it meets the criteria specified by the Message Filter, the message is routed to the receiver, otherwise it's discarded.



<a name="loiobd523460894744a8be6b7bbe3351f795__section_izl_ljx_sjb"/>

## Implementation

The Message Filter pattern is similar to the Content-Based Routing pattern where the message is ignored if the receiver can't be determined. See the reference integration flow *Pattern Content Based Routing - Ignore If No Receiver* \(described in [Variant: Ignore](variant-ignore-4998bd8.md)\).

For the Message Filter pattern however, you define only one single receiver.

In the *Pattern Message Filter* integration flow, a routing condition is defined that is based on the product category. The message is discarded if the routing condition isn't met. This behavior is achieved by adding a default routing pointing to an end event.

![](images/Message_Filter_84df007.png)

A Content Modifier stores the XPath expression value in an exchange property \(with the name `productCategory`\) accessing the desired value with the following XPath expression: `/ns0:Product/Category`.

> ### Tip:  
> Instead of directly accessing the content of the message via an XPath in the Router, a property is used to store the value of the XPath \(for better traceability\).

For the first route, the `${property.productCategory} = 'Notebooks'` condition is defined using this property. For the 2nd route, the *Default Route* option is selected. If the condition isn't met, message processing ends, and the message isn't delivered.

Note that the corresponding namespace mapping is maintained on the *Runtime Configuration* tab of the integration flow: `xmlns:ns0=http://demo.sap.com/eip/message-filter`.

**Related Information**  


[Define Router](define-router-d7fddbd.md "")

