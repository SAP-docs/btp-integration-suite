<!-- loio8e83d460bff24dada765187ace8a5cec -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# AI-based Memory Profiling

AI-Assisted integration flow memory profiling feature enhances the existing integration flow simulation by providing memory profiling during integration flow simulation.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

Integration developers can obtain flow component-level profiling data, focusing on memory allocation behavior, and receive AI-driven recommendations for memory optimization before deployment.

These actionable and validated recommendations are aligned with [integration flow design guidelines](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/design-guidelines?).



## Prerequisite

-   A tenant administrator must enable the memory profiling feature on from [Artificial Intelligence](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/artificial-intelligence?) settings page.

-   If the integration flow contains groovy script step:

    -   The Integration flow must be in edit mode as the [optimization](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/optimize-groovy-scripts-with-ai?) inputs for groovy scripts can be applied in the groovy editor.
    -   A tenant administrator must enable the script optimization feature from Artificial Intelligence settings page. See [Artificial Intelligence](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/artificial-intelligence?)




## Procedure

To enable AI-based memory profiling during simulation, see [Configure Simulation](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/configure-simulation?version=CLOUD&ai=true#procedure).


<dl>
<dt><b>

For step-by-step visual instructions, refer to the [blog](https://community.sap.com/t5/technology-blog-posts-by-sap/ai-based-memory-profiling-for-integration-flow-simulation-optimize-before/ba-p/14461815).

</b></dt>
<dd>



</dd>
</dl>

You can watch a short video to understand the steps: 



## Implication

For each flow step, choose the :envelope: to view the simulation result, and for the top memory-contributing flow steps, the *Memory Profiling Insights* tab contains data regarding memory allocation behavior and AI insights for Optimizations.

> ### Note:  
> For Groovy scripts, choose *Optimize in Editor* to navigate to the script editor and then choose *Optimize* to view the recommendations, which will also include memory-related insights and optimization suggestions, where applicable. See [Optimize Groovy Scripts with AI](optimize-groovy-scripts-with-ai-3b7a5a1.md)



## Results

By integrating profiling and AI-assisted analysis directly into the simulation process, developers can proactively optimize integration flows, improve memory characteristics, and address potential issues before deploying content to the runtime environment.

