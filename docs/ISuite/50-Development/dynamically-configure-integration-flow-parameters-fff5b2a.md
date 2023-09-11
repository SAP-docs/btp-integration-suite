<!-- loiofff5b2a27deb49389c502287dbf8a85b -->

# Dynamically Configure Integration Flow Parameters

For certain integration flow parameters you can enter a reference to a header or property instead of a fixed value. At runtime, the actual value of the header or property in the incomung message is then used as parameter value. This is referred to as dynamic configuration.



<a name="loiofff5b2a27deb49389c502287dbf8a85b__prereq_ehv_wxr_pdb"/>

## Prerequisites

-   The parameter supports dynamic configuration.

    More information: [Parameters That Support Dynamic Configuration](parameters-that-support-dynamic-configuration-c9bba0e.md)

-   There is a header or property that you can use for dynamic configuration of the parameter. Either the header/property is defined by a preceding component in the integration flow or it is provided by the integratrion framework.




## Context

The following kinds of headers and properties can be used to dynamically configure a certain parameter.

-   Headers or properties defined by a content modifier step \(preceding the step or adapter for which you like to define a dynamic parameter\)

    More information:

    [Define Content Modifier](define-content-modifier-8f04a70.md)

-   Predefined headers or properties that are provided by the integration framework.

    More information:

    [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)


> ### Note:  
> If you’re configuring the *Connection* of an Adapter with dynamic parameters, then you must use the same dynamic parameter name for a given `<host>:<port>` combination across all integration flows in your tenant.



## Procedure

1.  Open the integration flow in edit mode and select the component where you like to dynamically configure a parameter.

2.  Specify the parameter value by entering an expression of the following form.

    `${header.<name of header>}`

    or

    `${property.<name of property>}`

    Example:

    In a content modifier step that is placed before the component where you dynamically configure a parameter, you have defined the following header \(which contains the customer number of an inbound message\): `customerNo`.

    For the parameter \(to be defined dynamically\) enter the following expression:

    `${header.customerNo}`

    At runtime, the actual value for the header `customerNo` \(derived from the inbound message\) is used as parameter value.

3.  Finish the configuration of the integration flow.


**Related Information**  


[Dynamic Parameters \(Example\)](dynamic-parameters-example-5705f2b.md)

[Parameters That Support Dynamic Configuration](parameters-that-support-dynamic-configuration-c9bba0e.md "")

[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md "")

