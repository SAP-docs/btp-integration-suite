<!-- loio45a71f8ffd74436aaf02a3536f3c6992 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Simulation

Use *Simulation* feature to test an integration flow and check the desired outcome even before the deployment.



## Prerequisites

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

-   A tenant admin must enable the memory profiling feature on from [Artificial Intelligence](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/artificial-intelligence?) settings page.

-   If the integration flow contains groovy script step:

    -   The Integration flow must be in edit mode as the [optimization](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/optimize-groovy-scripts-with-ai?) inputs for groovy scripts are needed to be opened in the groovy editor.

    -   A tenant admin must enable the script optimization feature from Artificial Intelligence settings page. See [Artificial Intelligence](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/artificial-intelligence?)





## Context

The steps described here explains the process of running a *Simulation* in both read and edit mode of an integration flow.

> ### Remember:  
> If your tenant is provisioned in Cloud Foundry Environment, then the input payload size for the simulation must be less than 100KB and the overall output payload must be less than 1MB.



<a name="loio45a71f8ffd74436aaf02a3536f3c6992__procedure"/>

## Procedure

1.  Choose your package and then select the integration flow.

2.  You can see simulation tool on the palette.

    The simulation tool includes the following functionalities:-

    1.  *Run Simulation:* Use it to execute the simulation process.

    2.  *Clear Simulation:* Use it to clear the previously used simulations. Once you clear the simulation, you cannot undo it.


3.  Identify subset of an integration flow that you would like to simulate and choose the connection to locate the *Start Point* and the *End Point* for the simulation.

4.  Choose <span class="SAP-icons-V5"></span>as a start point of the simulation on any connection to begin.

    1.  Choose the start point at a connection gives an option to provide the input to simulation and trigger it accordingly.

    2.  A dialog opens to add a simulation input. Provide the necessary details. You can add input that could be *Payload* or *Headers* or *Properties*. You can also upload input payload from your local file system.

    3.  Under AI configuration, select *Enable Memory Profiling* to obtain memory profiling insights after a successful simulation run. Read this [blog](https://community.sap.com/t5/technology-blog-posts-by-sap/ai-based-memory-profiling-for-integration-flow-simulation-optimize-before/ba-p/14461815) or watch a short [video](https://video.sap.com/media/t/1_bmqaway5) for this AI feature.

    4.  Choose *OK* to submit input. For more information, see [Using Various Types of Body Files in the Simulation](using-various-types-of-body-files-in-the-simulation-2e3cf3b.md).


5.  Choose <span class="SAP-icons-V5"></span>to end the defined simulation flow step.

    > ### Note:  
    > -   You can’t run simulation if you don't define the end point. In this case *Run Simulation* button grayed out.
    > 
    > -   Simulation fails if there are any check errors in resources like mapping.
    > 
    > -   You can allow maximum of 10 integration flow step per simulation to run. The best practice is to allow lesser than or equal to 10 flow steps for complex integration flows.
    > 
    > -   Simulation of looping process call with maximum number of iterations more than 10 is not supported.

6.  Choose :arrow_forward: to run the simulation. Once the simulation run is successful, a message :envelope:envelope appears alongside each flow component with a tracing information. Choosing the envelope you can see the details.

    > ### Note:  
    > If you have enabled Memory profiling and the flow step is one of the top memory-contributing flow step, you'll be able to view the memory profiling insights.
    > 
    > If the integration flow contains Groovy script step, choose *Optimize in Editor* and then *Optimize* to view the recommendations in the script editor. See  <?sap-ot O2O class="- topic/xref " href="3b7a5a1258ea469b963dc047c3f443a0.xml" text="" desc="" xtrc="xref:7" xtrf="file:/home/builder/src/dita-all/zpk1713331951414/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/45a71f8ffd74436aaf02a3536f3c6992.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

7.  **\(Only if memory profiling is enabled\)**: Review the reported top memory contributors and the recommendations. Apply the suggested fix to that flow step and re-run simulation to identify other significant memory issues.

8.  Choose <span class="SAP-icons-V5"></span>to clear the simulation and you can start with fresh flow steps to begin new set of simulation.

    > ### Note:  
    > -   Changing integration flow mode \(Read or Edit\) loses the configuration of an integration flow simulation.
    > 
    > -   When the simulation is cleared, simulation data is lost.


