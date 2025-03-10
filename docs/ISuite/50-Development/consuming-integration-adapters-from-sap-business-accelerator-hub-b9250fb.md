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
> -   When you choose the adapter in your integration flow, it triggers the importing of the adapter and its package from SAP Business Accelerator Hub to your design workspace. While doing so, Cloud Integration looks out for an already existing package with the same name. If a package with the same name doesn't exist, then the import and deploy of the adapter succeeds upon which you can use the adapter for your design. Else, import of the adapter fails.
> 
>     The adapter gets auto-deployed to the runtime profile configured in the integration flow. See: [Specify the Runtime Configuration](specify-the-runtime-configuration-0c1c96e.md). If you want to deploy the adapter to more than one runtime profile, you must manually deploy to each one of them. For more information, see [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   Alternatively, you can copy the package that contains the adapter from the *Discover* view like you do for standard prepackaged content. This way, you need not import from SAP Business Accelerator Hub during design time. You must first deploy the adapter to a runtime profile of your choice before using it in an integration flow.
> 
>     In this case too, if you want to deploy the adapter to more than one runtime profile, you must manually deploy to each one of them.
> 
> -   You can reuse a deployed adapter multiple times. That is, if the adapter \(and its package\) from SAP Business Accelerator Hub is already available in your tenant, the adapter gets picked upon selecting it. You need not import and deploy every time you want to use it.
> 
> -   You can't edit or add new artifacts to the adapter's package.
> 
> -   For the purpose of protecting the intellectual property, you can't download the adapter.



### Adapters Lifecycle

Like other prebundled standard packages, the package that contains the adapter supports SAP Business Accelerator Hub lifecycle operations. Every time a new version of the adapter is published to the Hub, you see *Update Available* information for the package in your design workspace. You can easily update the package and use the latest version of the adapter. Upon updating the adapter, your already deployed integration flows start consuming the latest version of the adapter.

> ### Remember:  
> Before using the latest adapter productively, take steps to test the execution of the integration flows so that you validate the updates made to the adapter.



### Adapters Availability

The availability of these adapters is dependent on your service plan. For more information about their availability, see SAP Note [3188446](https://launchpad.support.sap.com/#/notes/3188446).

