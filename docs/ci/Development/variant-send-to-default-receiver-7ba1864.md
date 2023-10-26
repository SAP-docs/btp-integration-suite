<!-- loio7ba1864526814e72adef9c96f79d319f -->

# Variant: Send to Default Receiver

In the example integration flow, the message is routed to different receivers depending on the country or region ID of the shipping address \(in other words, depending on a certain routing condition\). If neither routing condition is met, Cloud Integration sends the message to a default receiver. The *Pattern Content Based Routing - Send To Default* reference integration flow has been designed for demo purposes and therefore contains only 2 receivers. It has the following structure.

![](images/ContentBased_Routing_Default_bd47a5b.png)

The integration flow processes the message in the following way:

1.  A Content Modifier step stores the XPath expression value as an exchange property.

    > ### Note:  
    > Instead of directly accessing the content of the message in the Router step via an XPath expression, use a property for your XPath.
    > 
    > That way, traceability is improved \(if trace is switched on\). Furthermore, a better runtime behavior can be expected since the message needs to be parsed only once.

    To check the configuration of the Content Modifier step, select the step and then select the *Exchange Property* tab. In the reference integration flow, the new property *shippingRegion* has been entered with the following attributes:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    XPath
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Data Type
    
    </td>
    <td valign="top">
    
    java.lang.String
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Value
    
    </td>
    <td valign="top">
    
    /ns0:PurchaseOrder/Address/Region\[../../Address\[@Type='Shipping'\]\]
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > The corresponding namespace mapping is maintained on the *Runtime Configuration* tab of the integration flow. In our case: *xmlns:ns0=http://demo.sap.com/eip/content-based-router*.

2.  The Router step is configured in such a way that it contains a default route.

    For the default path \(which the message is supposed to take in case none of the explicit conditions of the other routes are fulfilled\) the option *Default Route* is specified.

    For the other routes, condition expressions are configured based on the previously created exchange property.

    Example condition:

    *$\{property.shippingRegion\} = 'NL'*


**Related Information**  


[Define Router](define-router-d7fddbd.md "")

