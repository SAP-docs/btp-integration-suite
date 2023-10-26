<!-- loio271810669c5a4c5e87e535055cc34434 -->

# Test Message Mapping

Use this design time test to validate correctness of mappings with the given test inputs.



## Prerequisites

You have ensured that your message mapping is complete, that is, your sources are mapped to your targets.



## Context

When you create message mappings, you need to check whether or not they function as expected. By simulating a mapping, you can verify the correctness and functioning of them.

> ### Note:  
> Message Mapping Simulation is supported only for the Cloud Integration runtime profile.



## Procedure

1.  Choose *Design* \> *Integrations and APIs*.

2.  Open your integration flow and select *Edit*.

3.  Select the mapping that you want to test.

    The name of the mapping is displayed under the **Mapping**section.

4.  If you want to test the mapping, choose *Simulate* \> *Upload Input*.

5.  Select the input XML file that you want to test from the file system, and choose *Open*.

    The input XML file data is displayed on the source message table.

6.  Choose *Test*.

    The output XML file data is displayed on the target message table.

7.  If you want to download the output test XML, choose *Download*.

    > ### Note:  
    > -   You do not have to save the mapping to perform simulation.
    > 
    > -   You can also a test a message mapping with scripts.
    > 
    > -   You can also modify any of the following operations in the graphical editor:
    > 
    >     -   New function
    > 
    >     -   Properties
    > 
    > 
    >     Then, you can revalidate if the mapping is working correctly.
    > 
    > -   If you test an incomplete mapping, then you get a validation error.


