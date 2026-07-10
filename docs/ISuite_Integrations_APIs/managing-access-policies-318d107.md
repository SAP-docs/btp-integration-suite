<!-- loio318d107538644d1483c49eb97542b8da -->

# Managing Access Policies

Define access policies to restrict the access to integration artifacts and data processed and stored by them.



<a name="loio318d107538644d1483c49eb97542b8da__AccessPolicies_Intro"/>

## Access Policies

In SAP Integration Suite, user permissions are granted in such a way that all tasks can be performed on all artifacts and data. Access policies provide a way to restrict access to selected artifacts and their data.

See: [Access Policies](access-policies-e0009f3.md).

> ### Tip:  
> To learn more how access policies work, check out some examples at [Access Policies Examples](access-policies-examples-f1dc1a7.md).





### Define Access Policies

To define an access policy, you go to *Monitor* \> *Integrations and APIs* \> *Manage Security* and select the *Access Policies* tile.

Here, you define the set of artifacts that are to be protected by the access policy \(for example, a specific set of integration flows\).

An access policy can contain multiple artifact references, each artifact reference defining an artifact type and a condition for the name or ID of the artifacts to be protected.

See: [Defining Access Policies](defining-access-policies-b0d7950.md)



### Provide User Access

To give dedicated users access to the artifacts protected by the access policy, you define a role and associate it with the access policy \(using SAP Business Technology Platform cockpit\).

Only users that are assigned to that role can access the artifacts protected by the access policy.

See: [Creating Custom Roles for Access Policies](creating-custom-roles-for-access-policies-7db3c87.md)

> ### Note:  
> You can also retrieve access policies \(read and write operations\) by an OData V2 application programming interface \(API\). You find the API and its documentation on SAP Business Accelerator Hub at: [Security Content](http://help.sap.com/disclaimer?site=https%3A%2F%2Fapi.sap.com%2Fapi%2FSecurityContent%2Fresource).

