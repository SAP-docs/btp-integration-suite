<!-- loiob6a1a6169ab145aa8d647b2e21c54194 -->

# Importing Integration Packages

Upload your existing integration packages that suits your integration scenario to reduce redundancy and duplication efforts of creating a package from scratch.



## Procedure

1.  Choose *Design* \> *Integrations and APIs* \> *Import*.

    > ### Note:  
    > Importing a new version of a package \(zip import\) over an existing package doesn't overwrite the configured values of the externalized parameters in the existing package.
    > 
    > **Merge** scenario – A package exists in the target tenant. If you change the package in its source tenant and try to import with delta changes, the import action overwrites the package in the target tenant with the delta changes. Additionally, if you had added new artifacts to the package in the target tenant, the import action retains those artifacts as is. That is, the import action merges the delta changes and unique artifacts of the package in the target tenant.

2.  Browse and select the integration package for uploading.

3.  Choose *OK*.

    Import of a package fails with *Uniqueness Conflict* when the source package contains one or more artifacts that already exist in other packages of the target tenant.

    A package is created based on the metadata of the uploaded file.


