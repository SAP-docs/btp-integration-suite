<!-- loio93fa2ceb2a9a4c57abc60f618badff4d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Smoke Test Scenario

This is a simple test to verify that your SAP Cloud Integration simulation is working as expected.



## Context

In this scenario, you run a simulation without deploying the integration flow and you can check the trace results in the message envelope.

In the course of this exercise, you execute a simulation tool on an integration flow.

> ### Note:  
> Create an integration flow, add the following details, and save.
> 
> -   Insert `${in.body}`in the message body of *Content Modifier*.
> 
> -   Insert XPath Expression as `//root/order` in the processing section of the *Filter*.



## Procedure

1.  Choose an Integration flow and keep it in a read-only mode.

2.  Select the connector line between *Timer* and *Content Modifier* and choose *Simulation Start Point* <span class="SAP-icons-V5"></span> .

3.  Select the connection between *XML to JSON Converter* and *End Message* and choose Simulation End Point <span class="SAP-icons-V5"></span> . 

    You can see that the first two icons of the simulation tool have been enabled.

4.  We need to provide an input for the simulation to run. You can add a header value or a property or, you can enter a payload in the body. For this test case, let us provide an input payload in the body.

5.  Choose the *Simulation Start Point*, a dialog opens to *Add Simulation Input*. Provide an input payload in the *Body* section and choose *OK*. The subset of an integration flow now filters the incoming payload based on the XPath provided in the Filter step.

    Use the following payload:

    `<root><order><orderno>OD100</orderno></order></root>`

6.  Select simulation tool and choose *Run Simulation*:arrow_forward:

7.  You receive a toast message that the simulation completed successfully, the simulation *End Point* turns from black color to green and a message envelope :envelope: appears between start and end point.

8.  Choose*Message Envelope* located next to *XML to JSON Converter*. A message content opens, check the body section and verify that the input payload has been simulated. Based on the input and the XPath provided, the output message consist of the order details.

    You can check that based on the filter criteria, the resulting message has been generated correctly.

9.  Choose *Clear Simulation*<span class="SAP-icons-V5"></span> located in the simulation tool to clear all defined simulation path.


