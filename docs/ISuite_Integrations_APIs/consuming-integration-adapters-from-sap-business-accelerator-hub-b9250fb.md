<!-- loiob9250fb8dc694a54a46257f7587ceb29 -->

# Consuming Integration Adapters from SAP Business Accelerator Hub

Learn about adapters available in the SAP Business Accelerator Hub.





### Adapters in SAP Business Accelerator Hub

Cloud Integration has a rich set of prebundled adapters that help you to connect to a multitude of cloud and on-premise systems. Apart from these adapters, there are also adapters available in the SAP Business Accelerator Hub.



### Finding and Consuming the Adapters

Like consuming the prebundled adapters, consuming these integration adapters is also simple. Cloud Integration takes care of fetching and deploying the adapter from SAP Business Accelerator Hub. All that you have to do is to choose the adapter in your integration flow design. For more information, see [Import Integration Adapters](import-integration-adapters-386d7d0.md).



### Adapter and Its Package

Each adapter that’s available in the SAP Business Accelerator Hub in contained in a package that is exclusively created for containing only the adapter. When you consume an adapter from SAP Business Accelerator Hub, Cloud Integration creates a package in your design workspace along with the adapter.

> ### Remember:  
> -   When you choose the adapter in your integration flow, Cloud Integration imports its along with its package from SAP Business Accelerator Hub to your design view. The import succeeds only if no package with the same name exists in your tenant; otherwise, it fails. If the adapter is already available in your tenant, it is reused and re-import isn't needed.
> 
> -   **Auto-deployment behavior**: The adapter gets auto-deployed to the runtime profile configured in the integration flow. See: [Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md). For more information, see [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   **Deploying to multiple runtime profiles**: The adapter is not automatically deployed to other runtime profiles. You must manually deploy it to each additional runtime profile before deploying the integration flow there, or the flow will fail. The same applies when the runtime profile of an integration flow is changed.
> -   Alternatively, you can copy the package that contains the adapter from the *Discover* view like you do for standard prepackaged content. This way, you need not import from SAP Business Accelerator Hub during design time. You must first deploy the adapter to a runtime profile of your choice before using it in an integration flow.
> 
>     In this case too, if you want to deploy the adapter to more than one runtime profile, you must manually deploy to each one of them.
> 
> -   **Restrictions**: You cannot edit the adapter package, add artifacts to it, or download it.



### Adapters Lifecycle

Like other prebundled standard packages, the package that contains the adapter supports SAP Business Accelerator Hub lifecycle operations. Every time a new version of the adapter is published to the Hub, you see *Update Available* information for the package in your design workspace. You can easily update the package and use the latest version of the adapter. Upon updating the adapter, your already deployed integration flows start consuming the latest version of the adapter.

> ### Remember:  
> Before using the latest adapter productively, take steps to test the execution of the integration flows so that you validate the updates made to the adapter.



### Adapters Availability

The availability of these adapters is dependent on your service plan. For more information about their availability, see SAP Note [3188446](https://launchpad.support.sap.com/#/notes/3188446).

