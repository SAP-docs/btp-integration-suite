<!-- loio82a50100688e48f694ff28701a33ca8a -->

# Validating Adapters



<a name="loio82a50100688e48f694ff28701a33ca8a__prereq_qvk_ggq_3xb"/>

## Prerequisites

-   You have requested a test tenant from your existing production tenant. See: [Request New Tenant](request-new-tenant-ac413cc.md)
-   You have enabled the *Integration Suite* service in the new test tenant. See: [Subscribing and Configuring Initial Access to SAP Integration Suite](../../10-InitialSetup/subscribing-and-configuring-initial-access-to-sap-integration-suite-8a3c8b7.md)

-   Make necessary modifications in your custom adapters to make them compatible with Apache Camel 3.14 runtime.




<a name="loio82a50100688e48f694ff28701a33ca8a__context_xtl_3hq_3xb"/>

## Context

The custom integration adapters, which you have already depolyed in 2.14 runtime must be verified for compatibility with Apache Camel 3.14 runtime. Post verification, you should test the integration flows.



<a name="loio82a50100688e48f694ff28701a33ca8a__steps_gkv_23c_lxb"/>

## Procedure

1.  Open the newly assigned testIntegration Suite tenant.

2.  Go to *Design* \> *Integration* and import older version of camel adapter and check if it is working in the new tenant.

3.  Verify your integration flows in this new test tenant. For details on standard modifications, troubleshooting and camel version migration, see SAP Note [3326553](https://me.sap.com/notes/3326553).


