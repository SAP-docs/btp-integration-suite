<!-- loio809210ad018c4fecb2f6a353809f8905 -->

# Post Migration Tasks



<a name="loio809210ad018c4fecb2f6a353809f8905__prereq_qjd_vcb_t1c"/>

## Prerequisites

-   Your production tenant is upgraded to Camel 3.14 runtime version.

-   The uploaded integration adapters compatible with Camel 3.14 runtime version have been migrated to the production tenant.




## Context

Import/update the compatible adapters to your design time to avoid any business process disruption.



## Procedure

**SAP Business Accelerator Hub adapters**

Choose *Update Available* information for the package in your design workspace to update your package and use the latest version of the adapter. Upon updating the adapter, your already deployed integration flows start consuming the latest version of the adapter. See: [Consuming Integration Adapters from SAP Business Accelerator Hub](../consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md)

**Other ADK adapters**

For all other custom integration adapters developed by you, partners, or downloaded from SMP, follow these steps:

1.  Choose *Design* \> *Integrations and APIs* to view the list of integration packages. Find and open the integration packages with Camel 2.24 runtime compatible custom adapters.

2.  Select and delete the adapters compatible with Camel 2.24 runtime. See: [Editing an Integration Package](../editing-an-integration-package-155164d.md)

3.  Navigate to the *Artifacts* tab. Choose *Add* \> *Integration Adapter* to import the custom integration adapters \(.esa file\) compatible with Camel 3.14 runtime.

    > ### Caution:  
    > Deploying adapters compatbile with older runtime \(Camel 2.24\) will result in business process disruption, unexpected integration flow behaviour, and overwriting of newly migrated adapters.


