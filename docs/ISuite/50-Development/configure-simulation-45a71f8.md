<!-- loio45a71f8ffd74436aaf02a3536f3c6992 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Simulation

Use *Simulation* feature to test an integration flow and check the desired outcome even before the deployment.



## Context

The steps described here explains the process of running a *Simulation* in both read and edit mode of an integration flow.

> ### Remember:  
> If your tenant is provisioned in Cloud Foundry Environment, then the input payload size for the simulation must be less than 100KB and the overall output payload must be less than 1MB.



## Procedure

1.  Choose your package and then select the *Artifact*.

2.  You can see simulation tool on the palette.

    The simulation tool includes the following functionalities:-

    1.  *Run Simulation:* Use it to execute the simulation process.

    2.  *Clear Simulation:* Use it to clear the previously used simulations. Once you clear the simulation, you cannot undo it.


3.  Identify subset of an integration flow that you would like to simulate and choose the connection to locate the *Start Point* and the *End Point* for the simulation.

4.  Choose <span class="SAP-icons-V5"></span>as a start point of the simulation on any connection to begin.

    1.  Choose the start point at a connection gives an option to provide the input to simulation and trigger it accordingly.

    2.  A dialog opens to add a simulation input. Provide the necessary details. You can add input that could be *Payload* or *Headers* or *Properties*. You can also upload input payload from your local file system.

    3.  Choose *OK* to submit input. For more information, see [Using Various Types of Body Files in the Simulation](using-various-types-of-body-files-in-the-simulation-2e3cf3b.md).


5.  Choose <span class="SAP-icons-V5"></span>to end the defined simulation flow step.

    > ### Note:  
    > -   You can’t run simulation if you don't define the end point. In this case *Run Simulation* button grayed out.
    > 
    > -   Simulation fails if there are any check errors in resources like mapping.
    > 
    > -   You can allow maximum of 10 integration flow step per simulation to run. The best practice is to allow lesser than or equal to 10 flow steps for complex integration flows.
    > 
    > -   Simulation of looping process call with maximum number of iterations more than 10 is not supported.

6.  Choose :arrow_forward: to run the simulation. Once the simulation run is successful, a message :envelope:envelope appears with a tracing information. Choosing the envelope you can see the details.

7.  Choose <span class="SAP-icons-V5"></span>to clear the simulation and you can start with fresh flow steps to begin new set of simulation.

    > ### Note:  
    > -   Changing integration flow mode \(Read or Edit\) loses the configuration of an integration flow simulation.
    > 
    > -   When the simulation is cleared, simulation data is lost.


