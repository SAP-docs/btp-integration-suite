<!-- loio09685b71c09943d89419a1b02dd3b82c -->

# Versioning in Trading Partner Management

A version is a snapshot of a configuration and it's crucial for tracking an artifact's chronological progression. As a user, you can see an artifact's version, but can't edit it as it acts as a binding factor across versions related to a trading partner.



## Why Versioning

Implement versioning for the following use cases:

-   Mark a version of an artifact as a stable, working configuration state.

-   Prevent accidental modifications to tested and proven configurations.

-   Ensure clarity of configuration states across different tenants during export and import.




## Versioning Actions

The following actions are related to versioning:

-   *Save as New Version*: Create a new major version, for example, 1.0 to 2.0. This action is only available for drafts.

-   *Copy to Draft*: Reset a draft to a specific historical version.

-   *Copy as New*: Create a new agreement based on the historical version.

-   *Deletion*: You can delete any version, including drafts, or entire artifacts with all versions.




## Supported Artifacts

The following artifacts in Trading Partner Management support versioning:

-   Agreement templates



## Version Lifecycle

The following steps form up an artifact's version lifecycle:

1.  Newly created artifacts are in the version *Draft*.
2.  To save an artifact that you consider to be final to a new version, choose *Save as New Version*. The first version is *1.0*, and all following versions increment sequentially.
3.  Once an artifact is versioned, it becomes *read only* and can't be edited.
4.  To edit a versioned artifact, choose *Copy as Draft* to create a new editable draft version.
5.  There can only be **one draft version** of an artifact at a time. To create a new draft, you must first version or delete the existing one.
6.  A maximum of **five numbered versions** and **one draft** version can exist for the same artifact. If you need to create more, delete existing versions.



## Versioning Conflicts

The following applies if there are conflicts due to import and versioning.

> ### Note:  
> For the versioning to be consistent, always create and version in the development tenants and only transport to the target tenants. To avoid conflicts, don't develop in parallel in different tenants.



### Imported Resource in Status Draft

If the status of the imported resource is **draft**, consider the following:

-   If the resource in the target tenant is **missing or unversioned** and in **draft**, it's imported as **draft**.

-   If the resource in the target tenant is **versioned**, attempting to import it as a **draft** causes the operation to **cancel with an error**.




### Imported Resource in Status Unversioned

If the status of the imported resource is **unversioned**, consider the following:

-   If the resource in the target tenant is **missing**, it's imported as a **draft**.

-   If the resource in the target tenant exists but is **unversioned**, importing again results in **overwriting as a draft**.

-   If the resource in the target tenant exists and is versioned, the system **cancels and throws an error** because versions can't be overwritten.




### Imported Resource in Status Versioned

If the status of the imported resource is **versioned**, consider the following:

-   If the resource in the target tenant is **missing or unversioned**, it's imported as a **draft**.

-   If the imported resource **matches the versioned target exactly**, the import is **skipped**.

-   If there's a **versioned conflict**, the operation is **canceled with an error**. The cancellation can have one of the following reasons:

    -   There's independent versioning in both the source and the target system.

    -   The ZIP file has been tampered with.


-   If the target resource lacks a version but already holds the **maximum of 5 versions**, importing a new version **cancels and throws an error** because the limit is reached.


