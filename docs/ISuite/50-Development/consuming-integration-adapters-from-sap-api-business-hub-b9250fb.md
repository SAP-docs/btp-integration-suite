<!-- loiob9250fb8dc694a54a46257f7587ceb29 -->

# Consuming Integration Adapters from SAP API Business Hub

Learn about adapters available in the SAP API Business Hub.





### Adapters in SAP API Business Hub

SAP Cloud Integration has a rich set of prebundled adapters that help you to connect to a multitude of cloud and on-premise systems. Apart from these adapters, there are also adapters available in the SAP API Business Hub.



### Finding and Consuming the Adapters

Like consuming the prebundled adapters, consuming these integration adapters is also simple. Cloud Integration takes care of fetching and deploying the adapter from SAP API Business Hub. All that you've to do is to choose the adapter in your integration flow design. For more information, see [Import Integration Adapters](import-integration-adapters-386d7d0.md).



### Adapter and Its Package

Each adapter that is available in the SAP API Business Hub in contained in a package that is exclusively created for containing only the adapter. When you consume an adapter from SAP API Business Hub, Cloud Integration creates a package in your design workspace along with the adapter.

> ### Remember:  
> -   While importing the adapter and its package from SAP API Business Hub to your design workspace, Cloud Integration looks out for an already existing package with the same name. If a package with same name exists, then the import of adapter fails. Else, import and deploy of the adapter is successful upon which you can use the adapter for your design.
> 
> -   You can reuse a deployed adapter multiple times. That is, if the adapter \(and its package\) from SAP API Business Hub is already available in your tenant, the adapter gets picked upon selecting it. You need import and deploy every time you want to use it.
> 
> -   You can't edit or add new artifacts to the adapter's package.
> 
> -   For the purpose of protecting the intellectual property, you can't download the adapter.



### Adapters Lifecycle

Like other prebundled standard packages, the package that contains the adapter supports SAP API Business Hub lifecycle operations. Every time a new version of the adapter is published to the Hub, you see *Update Available* information for the package in your design workspace. You can easily update the package and use the latest version of the adapter. Upon updating the adapter, your already deployed integration flows continue to work well with the older version of the adapter without any disruption. If you wish, you can edit the deployed integration flows to use the newer version of the adapter.



### Adapters Availability

The availability of these custom adapters is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

