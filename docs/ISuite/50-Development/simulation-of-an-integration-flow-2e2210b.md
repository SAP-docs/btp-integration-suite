<!-- loio2e2210b6db0c4fdb937b3a57d952f582 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Simulation of an Integration Flow

The simulation feature allows you to test an integration flow or its subset and see if you can get the desired outcome even before you deploy the integration flow. Based on the simulation result, you can decide to deploy the integration flow or resolve any errors.

<a name="concept_yxf_f5w_1lb"/>

<!-- concept\_yxf\_f5w\_1lb -->

## Scope of an Integration Flow Simulation

The simulation feature is evolving in numerous directions and incorporating new capabilities with multiple increments of development.

-   We allow simulation in the read and edit mode of an integration flow. You can test the integration flow during the development phase itself.

-   In edit mode, you can simulate an integration flow without saving the data and settings.

    > ### Note:  
    > When you switch from edit to read mode, the simulation output isn't retained.


<a name="concept_vfh_tdv_vkb"/>

<!-- concept\_vfh\_tdv\_vkb -->

## Benefits of Simulation

This section lists the advantages of using simulation in an integration flow.

-   Realistic input for integration developers when designing an integration flow.

-   You can simulate dependencies and identify issues at an early stage.

-   Any errors identified during the simulation are recorded as a message along with details about how to fix it.

-   Improves integration developer productivity and saves time in developing an integration flow.

-   The smart upload functionality allows you to upload a zip file as a simulation input payload. The content of the trace message can also be downloaded after simulation.


<a name="concept_gjj_ztw_1lb"/>

<!-- concept\_gjj\_ztw\_1lb -->

## Elements Supported in Simulation


<table>
<tr>
<th valign="top">

Category

</th>
<th valign="top">

Elements

</th>
<th valign="top">

Supported Elements

</th>
</tr>
<tr>
<td valign="top">

Message Transformers

</td>
<td valign="top">

-   Content Modifier

-   Converter

-   Decoder

-   Encoder

-   Filter

-   Message Digest

-   Script




</td>
<td valign="top">

All

> ### Note:  
> HTTP calls can’t be simulated for the Script flow step.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Call

Call

</td>
<td valign="top">

External Call

-   Request Reply

-   Content Enricher

-   Send




</td>
<td valign="top">

All

You can't make the actual call to a receiver system to get the response. However, you can mock the response from the receiver system via receiver adapter. Select the receiver adapter that is connected to *Request Reply* step and select *Add Simulation Response*. Provide the payload or headers in the dialog and the same is considered as a response when you run the simulation. If you don't mock the response, the message payload from the previous steps is be considered.

</td>
</tr>
<tr>
<td valign="top">

Local Call

-   Process Call

-   Looping Process Call




</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

Message Routing

</td>
<td valign="top">

-   Aggregator

-   Join

-   Router

-   Splitter

-   Multicast

-   Gather




</td>
<td valign="top">

Aggregator isn't supported.

</td>
</tr>
<tr>
<td valign="top">

Security Elements

</td>
<td valign="top">

-   Decryptor

-   Encryptor

-   Signer

-   Verifier




</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

Persistence

</td>
<td valign="top">

-   Data Store operations

-   Persist

-   Write Variables




</td>
<td valign="top">

You can only simulate the read operation for *Write Variables* and *Data Store.* 

</td>
</tr>
<tr>
<td valign="top">

Validator

</td>
<td valign="top">

XML Validator

</td>
<td valign="top">

XML Validator

</td>
</tr>
</table>

<a name="concept_czr_ssg_xkb"/>

<!-- concept\_czr\_ssg\_xkb -->

## Functionalities of Simulation

This section explains the different functionalities and how they work in the simulation tool.

**Details of Simulation Functionalities**


<table>
<tr>
<th valign="top">

Functionalities

</th>
<th valign="top">

Icon

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

*Start Point* 

</td>
<td valign="top">

<span class="SAP-icons-V5"></span>

</td>
<td valign="top">

Place a Start Point at the beginning of your flow path. It feeds a simulation input.

</td>
</tr>
<tr>
<td valign="top">

*End Point* 

</td>
<td valign="top">

<span class="SAP-icons-V5"></span>

</td>
<td valign="top">

Place an End Point to end the simulation on your connection or the defined path of simulation.

</td>
</tr>
<tr>
<td valign="top">

*Add Simulation input* 

</td>
<td valign="top">

<span class="SAP-icons-V5"></span>

</td>
<td valign="top">

When you choose a Start Point, the *Add Simulation Input* dialog opens where an integration developer can add the following types of input:

-   *Header*

-   *Properties*

-   *Body*: You can copy and paste your payload content into the body or upload from the file system. Upon uploading the content, if there are any changes required you can edit in the content section and provide the necessary input.

-   *Upload from File system*: Upload input payload from the file system.

    > ### Note:  
    > -   You can upload not only the standalone zip file, but also individually as headers, properties, and body.
    > 
    > -   The maximum size of the payload is 1 MB.


For more information, see [Using Various Types of Body Files in the Simulation](using-various-types-of-body-files-in-the-simulation-2e3cf3b.md).

</td>
</tr>
<tr>
<td valign="top">

*Add Simulation Response* 

</td>
<td valign="top">

<span class="SAP-icons-V5"></span>

</td>
<td valign="top">

Allows the integration developer to simulate the response from the receiver adapter connected to:

-   The Request-Reply step

-   Read of variable in the content modifier

-   Read of the data store in the Get element.



</td>
</tr>
<tr>
<td valign="top">

*Run Simulation* 

</td>
<td valign="top">

:arrow_forward:

</td>
<td valign="top">

Used to run the simulation once the start and end point have been defined.

</td>
</tr>
<tr>
<td valign="top">

*Clear Simulation* 

</td>
<td valign="top">

<span class="SAP-icons-V5"></span>

</td>
<td valign="top">

Removes all of the simulation elements such as the start point, end point, and message processing output.

</td>
</tr>
<tr>
<td valign="top">

*Message Envelope* 

</td>
<td valign="top">

:envelope:

</td>
<td valign="top">

When the simulation run is successful, the message envelope opens and you can find it between the start and end point. Choose the message envelope to display the message content. After simulation, you can download trace message content.

</td>
</tr>
</table>

<a name="concept_blw_fr5_zkb"/>

<!-- concept\_blw\_fr5\_zkb -->

## Color Conventions

During the simulation process, certain colors are familiarly associated with particular meanings.

**Colors and Their Meanings in the Simulation Tool.**


<table>
<tr>
<th valign="top">

Color Code

</th>
<th valign="top">

Used For

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Blue

</td>
<td valign="top">

Start point and Message Envelope

</td>
<td valign="top">

-   *Start Point:* Always remains the same.

-   *Message Envelope:* Appears after running the simulation successfully.



</td>
</tr>
<tr>
<td valign="top">

Red

</td>
<td valign="top">

End point and Message Envelope

</td>
<td valign="top">

Appears when there are any errors. Choose the respective elements to check error messages.

</td>
</tr>
<tr>
<td valign="top">

Black

</td>
<td valign="top">

End point

</td>
<td valign="top">

Normal behavior and no action required.

</td>
</tr>
<tr>
<td valign="top">

Green

</td>
<td valign="top">

End point

</td>
<td valign="top">

Appears on successful execution of the simulation.

</td>
</tr>
</table>

For detailed steps about using simulation, see [Configure Simulation](configure-simulation-45a71f8.md) 

