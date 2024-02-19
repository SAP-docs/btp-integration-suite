<!-- loio27c3926556e340d49628fd914dcba5b8 -->

# Upgrade Edge Integration Cell

Learn how to upgrade Edge Integration Cell.

Edge Integration Cell is updated at cloud speed, which means that updates must be done monthly.

Edge Integration Cell only supports a sequential upgrade path. The upgrade can be done only to one version higher than the currently deployed version.

> ### Note:  
> In some situations, SAP skips the delivery of a new version. This will be considered in the upgrade path support.

> ### Remember:  
> The compatibility of Edge Integration Cell with SAP Integration Suite's cloud components is maintained only for the latest version of Edge Integration Cell and its immediate predecessor. For instance, if the current available Edge Integration Cell version is 8.10, then versions 8.10 and 8.9 are compatible with SAP Integration Suite. Any versions lower than 8.9, such as 8.8 and below, are considered as outdated.
> 
> As a result, deployment and undeployment of content is blocked for Edge Integration Cell runtimes operating on these outdated versions. It's essential that you upgrade to the most recent version of Edge Integration Cell to enable all actions.
> 
> Do note that content deployed from previously outdated versions will continue to process without any restrictions.

Before you start the upgrade:

-   Make sure that you're using a Kubernetes version supported by both the old and new Edge Integration Cell versions.

-   Be aware that additional resource can be required during the upgrade process for rolling upgrade strategies or replication of new container images.


To get the latest upgrade and troubleshooting information, see SAP Note [3250441](https://me.sap.com/notes/3250441).



<a name="loio27c3926556e340d49628fd914dcba5b8__section_lwv_d2z_21c"/>

## Edge Integration Cell Versions

To have a quick look at the latest Edge Integration Cell version, choose the *Show Notifications* icon on the top right of the screen. Look out for the *Edge Integration Cell Upgrade* section.

To know the current version of all your Edge Integration Cell runtimes, navigate to *Settings* \> *Integrations*. In the *Runtime Profiles* tab, you see the available runtime profiles and their current versions. For more information, see: [Runtime Profiles](50-Development/IntegrationSettings/runtime-profiles-8007daa.md).

**Related Information**  


[Learn About Upgrading the Kubernetes Cluster](learn-about-upgrading-the-kubernetes-cluster-f1a047b.md "Learn about upgrading the Kubernetes cluster.")

[Upgrade Edge Integration Cell Solution](upgrade-edge-integration-cell-solution-e7b8089.md "Learn how to upgrade the Edge Integration Cell solution.")

