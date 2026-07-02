<!-- loiocb536a32a9684b6a98c43a4b1f41fc28 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Versioning of Artifacts

Cloud Integration offers an easy version management capability for your integration artifacts.

You can version both the integration package and its artifacts and documents.

When editing an artifact, you can either choose *Save as Version* to save your changes. Choose *Save* to save your artifact as *Draft* version. Choose *Save as Version* to create a new version of the artifact. In this case, you can specify the version in the upcoming *Version Information* dialog. In the *Comment* section, you can add additional information specific to the artifact for later reference. This helps you determine the purpose of each version.

-   The artifact version management is specific to the tenant that you are using it in. It will not work across tenants.

-   When you create a new artifact, it is created with the version 1.0.0 by default.

-   If you choose *Save* after editing an artifact, the artifact version will be *Draft*. You can only see the latest *Draft* version.

-   If you choose *Save as Version*, by default the micro version is increased, for example, from `1.0.0`to `1.0.1`. You can either confirm the proposed version number or change according to your policy.


By default, artifact versions follow the versioning convention of `<major>.<minor>.<micro>`. Although Cloud Integration does not prevent you from maintaining any version number, it is recommended to follow this convention. In combination with a well-defined versioning policy, thie measure helps you to understand to which extent changes of the package or artifact were done.

> ### Note:  
> **Example**
> 
> -   If you add a new integration flow step to an existing integration flow, increase the micro version, for example, from version `1.0.1` to `1.0.2`.
> 
> -   If you enhance an integration flow with a further integration process or an exception subprocess, increase the minor version, for example, from version `1.0.1` to`1.1.0`.
> 
> -   If you have updated an existing integration flow within an integration package, increase the micro version of the package.
> 
> -   If you have added a new integration flow to an integration package, increase the minor version of the package.

By default, you only see the latest version of the artifact in the integration package. However, the older versions of the artifact are available for you in the backend. If you want to switch to a different version of that artifact, you can do that by selecting the version and choosing the <span class="SAP-icons-V5"></span> icon corresponding to the version. This feature allows you to replace integration content of the current version with the selected version.

> ### Example:  
> You are currently using the `1.2.0` version of the artifact, but you want to switch to version `1.1.8`. You select the version number `1.2.0`, and in the *Version History* dialog, you choose <span class="SAP-icons-V5"></span> icon next to `1.1.8` to replace the integration content of the `1.2.0` version with `1.1.8` version. You can choose *More* to see comments about each version, if any.

