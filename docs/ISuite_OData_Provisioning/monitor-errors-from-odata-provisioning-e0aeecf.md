<!-- loioe0aeecf5888d4ba7bc86f630b166c2fd -->

# Monitor Errors from OData Provisioning

Analyze the root cause for errors and where they originated.



<a name="loioe0aeecf5888d4ba7bc86f630b166c2fd__prereq_v4v_zzp_tjb"/>

## Prerequisites

-   You’ve activated the OData Provisioning capability, and have completed the steps for runtime access and role assignment. See [Activating and Managing Capabilities](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/2ffb343c163c48a4b3a90f9f3c487328.html "Activate capabilities for SAP Integration Suite.") :arrow_upper_right: and [Runtime Access and Role Assignment for OData Provisioning](runtime-access-and-role-assignment-for-odata-provisioning-b46816c.md).
-   You have the *ODPManage* role assigned. See [Configuring User Access to SAP Integration Suite](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/2c6214a3228e4b4cba207f49fda92ed4.html "Assign the required roles and role collections to users for accessing the individual capabilities.") :arrow_upper_right:.



## Context

You can view the errors logged for the technical and registered OData services calls and view details like timestamp, service name, namespace, description of the error and the transaction ID.



## Procedure

1.  In the Integration Suite, navigate to *Monitoring* \> *OData Services*.

2.  Select *From* and *To* dates. Choose *Search*.

    The errors that occurred during the selected time frame are shown.


**Related Information**  


[Register OData Services](register-odata-services-9dfa56a.md "You can register OData services in the SAP Integration Suite to access back-end services from SAP Business Suite .")

[Manage Metadata Validation and Cache Settings for OData Services](manage-metadata-validation-and-cache-settings-for-odata-services-dd4df7a.md "Enable or disable metadata validation for a registered OData service. You can also allow caching of metadata, which significantly improves performance of the OData service calls. Additionally, you can view the list of services which has cached metadata. You can clear the metadata cache of the selected service or all the services.")

[Troubleshooting for OData Provisioning](troubleshooting-for-odata-provisioning-cdcbaa2.md "Access information about troubleshooting for OData Provisioning.")

