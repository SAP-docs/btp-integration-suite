<!-- loiofc4f957900b04f3a9df14757cdff0a66 -->

# Upload Custom Adapters



<a name="loiofc4f957900b04f3a9df14757cdff0a66__prereq_if4_b2q_3xb"/>

## Prerequisites

Custom integration adapters have been validated in the 3.14 runtime from the new test tenant.



<a name="loiofc4f957900b04f3a9df14757cdff0a66__context_mvv_c3q_3xb"/>

## Context

Upload the adapters compatible with Camel 3.14 runtime version from your existing production tenant to make them available in your tenant when the software is updated with the new runtime.



<a name="loiofc4f957900b04f3a9df14757cdff0a66__steps_c2v_d3q_3xb"/>

## Procedure

1.  From the subaccount of your productive Integration Suite tenant, go to *Services* \> *Integration Suite* \> *Settings* \> *Integrations* \> *Camel 3.14 Upgrade* \> *Upload*.

2.  **For your custom integration adapters:** In the Upload Custom Integration Adapter dialog box, *Browse* and select the adapter for uploading.

    > ### Note:  
    > -   The 3.14 runtime compatible adapter can only be uploaded if its 2.24 runtime compatible version is already deployed in the tenant.
    > -   The successfully uploaded custom adapters will be available in your production tenants after migration.

    **For your existing OEM adapters**: Select the checkbox beside *Enable porting of your existing OEM adapters to Apache Camel 3.14 runtime* to allow automatic porting of OEM adapters into your tenant once the tenants are migrated. You may also do it manually, by downloading OEM adapters from SMP and then uploading the adapters as mentioned above. For more details, see SAP Note [3326553](https://me.sap.com/notes/3326553).

    > ### Note:  
    > Autoporting will update your adapter to the latest version.

3.  After your tenant is upgraded to Camel 3.14 version, upload the adapter \(.esa file\) to the appropriate integration package. This action is done to ensure that your design time too has the latest version of the adapter.


