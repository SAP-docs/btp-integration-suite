<!-- loio74e431cfbc8b45c59d897c80b41639fd -->

# Handle Exceptions When Using the Splitter Pattern

In many integration scenarios, larger messages are split into smaller parts using a splitter pattern. The smaller chunks are then processed by SAP Integration Suite .  

In such scenarios, multiple errors can occur that you can handle in different ways.



<a name="loio74e431cfbc8b45c59d897c80b41639fd__section_plw_ftz_flb"/>

## Implementation

Use a proper combination of *Stop on Exception* \(in the Splitter step\) with End Events in the Exception Subprocess.

If you set the *Stop on Exception* flag in the Splitter step, choose one of the following options:

-   Use no Exception Subprocess.

-   If  you need a specific error handling, configure the Exception Subprocess to end with an Error End event.


If you don't set the *Stop on Exception* flag in the Splitter step, choose one of the following options:

-   Use no Exception Subprocess.

-   If you need a specific error handling, configure the Exception Subprocess to end with a Message End event.


> ### Tip:  
> Follow these general guidelines:
> 
> -   Use separate Local Integration Process for split processing \(between Splitter and Gather step or after the Splitter step if no Gather step is used\).
> 
>     That way, you can configure a dedicated exception handling for errors occurring in the split processing using an Exception Subprocess in this Local Integration Process.
> 
> -   Use a dedicated exception handling in the Exception Subprocess.
> 
>     More information: [Handle Exceptions](handle-exceptions-ca95c61.md)
> 
> 
> When using the Gather step, consider the following aspects:
> 
> -   Create a valid XML in the Exception Subprocess. If you handle split errors in an Exception Subprocess and use a Gather step after the Splitter, create a valid XML to be passed on to the Gather step. Otherwise, the Gather step stops with an error caused by the wrong format and the whole message processing ends with a *Failed* status.
> 
> -   Avoid configuring Splitter – Gather scenarios without error handling in an Exception Subprocess in the following case: You use the *Aggregation Algorithm* *Combine* for input XML messages of the same or different format in the Gather step. Otherwise, the Gather step stops with an error because the payload at the time the exception occurs has the wrong format \(wrong XML or no XML at all\). In such a case, message processing ends with a *Failed* status.

Depending on the overall use case for the scenario, there are different variants with different exception handling. 

-   [Variant 1: Splitter Without Gather with Stop on Exception and with Exception Subprocess](variant-1-splitter-without-gather-with-stop-on-exception-and-with-exception-subprocess-d2445ff.md)

-   [Variant 2: Splitter Without Gather Without Stop on Exception and with Exception Subprocess](variant-2-splitter-without-gather-without-stop-on-exception-and-with-exception-subprocess-f9a508a.md) 

-   [Variant 3: Splitter with Gather with Stop on Exception and with Exception Subprocess](variant-3-splitter-with-gather-with-stop-on-exception-and-with-exception-subprocess-4eac8a7.md) 

-   [Variant 4: Splitter with Gather Without Stop on Exception and with Exception Subprocess](variant-4-splitter-with-gather-without-stop-on-exception-and-with-exception-subprocess-77b89c1.md) 


Use the options with *Stop on Exception* if you want to cancel processing in an error case to ensure that everything has been executed in 1 unit of work. The options without *Stop on Exception* are useful if you want to process as many split parts as possible, and postprocess all incorrect parts later on using an alternative processing.



<a name="loio74e431cfbc8b45c59d897c80b41639fd__section_vwb_4nw_glb"/>

## Executing the Scenario

To simulate these scenarios, different request payloads are provided together with the Postman collection uploaded to the integration package.

**Related Information**  


[Handle Exceptions](handle-exceptions-ca95c61.md "Handle exceptions by extending an integration flow with an exception subprocess.")

