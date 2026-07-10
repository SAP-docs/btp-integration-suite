<!-- loioe0009f33c1764beea6b00e35cf6ca5d5 -->

# Access Policies

With access policies you can restrict the access to integration artifacts and to the data stored and processed by them.

With access policies, you can protect access to certain sets of artifacts. You can define artifact references for:

-   A package – by which all artifacts of the integration package and the package actions are protected.

-   A specific artifact type – for example, script collection or integration flow.


If access to at least one artifact of an integration package is restricted, you can't export, publish, or delete the integration package.

Access policies affect artifact access in the following dimensions:

> ### Remember:  
> With access policies in place, an unauthorized user is still allowed to view a protected resource.


<table>
<tr>
<th valign="top">

Dimension

</th>
<th valign="top">

Restricts ...

</th>
</tr>
<tr>
<td valign="top">

Design time artifact

</td>
<td valign="top">

Operations you can perform in the *Design* section on the artifact \(such like creating, uploading, editing, saving, deploying, or deleting the artifact\)

Simulation of artifacts is also restricted.

</td>
</tr>
<tr>
<td valign="top">

Deployed artifact

</td>
<td valign="top">

Operations you can perform on the deployed artifact under *Monitor* \> *Integrations and APIs* \> *Manage Integration Content* \(such like restarting or undeploying the artifact or changing the log level for monitoring\)

</td>
</tr>
<tr>
<td valign="top">

Data stored and processed by the artifact at runtime

</td>
<td valign="top">

Access to data collected or created during the execution of all integration artifacts

-   Monitoring data \(such like message processing log attachments or business data available when *Trace* log level is selected\)

-   Data stored in data stores, variables, and message queues

    > ### Note:  
    > When you've restricted access to a specific integration flow \(with artifact reference for *Integration Flow* artifact type\) that contains data store operations or variables, only access to local data stores or variables \(associated with this integration flow\) is limited. If you like to restrict access to global data stores, global variables and message queues, you need to define an access policy with an artifact reference specified as *Global Data Store*, *Global Variable*, or *Message Queue*.


> ### Caution:  
> Custom header properties are **not** protected by access policies. Note that custom header properties are not supposed to contain sensitive data.



</td>
</tr>
</table>



<a name="loioe0009f33c1764beea6b00e35cf6ca5d5__section_w34_bck_51c"/>

## Package-Level Access Policy

An access policy for an integration package limits:

-   Operations on the integration package \(such like exporting the package\)

-   Operations on all artifacts contained in the package


If an access policy for an integration package is created, users without the corresponding role can’t access any data stored at runtime \(for example, MPL attachments, integration flow tracing data, data store or variables entries\).

Such users also can’t perform any activities on the deployed artifact \(for example, restarting an integration flow or changing the log level\).



<a name="loioe0009f33c1764beea6b00e35cf6ca5d5__section_xtw_kck_51c"/>

## Artifact-Level Access Policy

An access policy for an artifact limits:

-   Operations on the specific artifact

-   Operations you can perform on the deployed artifact under *Monitor* \> *Integrations and APIs* \> *Manage Integration Content* \(such like restarting or undeploying the artifact or changing the log level for monitoring\).




<a name="loioe0009f33c1764beea6b00e35cf6ca5d5__section_rw1_d2k_51c"/>

## Things to Remember

-   Access policies cover user interface-based and API-based access to the artifact.

-   If access policies form an intersection, meaning that an artifact is protected by multiple different access policies, the following rule applies: If the user has a role associated with at least one of the access policies, the user has access to the artifact.

    In particular, access policies for integration packages and for specific artifact types \(such like integration flows and script collections, for example\) co-exist in the following terms:

    Assume that you've defined an access policy for a specific integration package. Furthermore, the integration package contains an artifact for which you've defined another access policy. In this case, a user with necessary role for the package-level access policy can perform operations on all artifacts, including the artifact that is protected by an additonal access policy.


> ### Tip:  
> To learn more how access policies work, check out some examples at [Access Policies Examples](access-policies-examples-f1dc1a7.md).

