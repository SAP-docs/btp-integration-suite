<!-- loio3f2e06bdc2454392a2aa1cd8bc4d37e8 -->

# API Artifact Versioning

API artifact versioning allows you to create and manage multiple releases of an API artifact. You can create a new version when you need to introduce enhancements, modifications, or new functionality without affecting consumers of an existing version.

Create a new version of an API artifact in the following scenarios:

-   You plan to introduce incompatible changes, such as structural modifications or payload changes.

-   You need to enforce additional policies and support a phased transition for API consumers.

-   You want to preserve a stable version while continuing development on a newer version.

-   You need the ability to restore a previously released version.


Multiple versions of the same API artifact can coexist at both design time and runtime, enabling consumers to continue using existing versions while newer versions are introduced.

When creating a new version, you can provide version information and optional comments that describe the purpose of the changes. These comments help identify the differences between versions and simplify version management.

The version history displays details such as:

-   Version number

-   Creation date

-   Creator information

-   Version comments

-   Active version status




## Reverting to a Previous Version

If required, you can revert to an earlier version of an API artifact.

The revert operation restores the selected version and makes it the active version. This allows you to roll back changes and return to a previously known state without recreating the artifact.

> ### Remember:  
> -   Every version is retained in the version history.
> 
> -   Only one version can be the active version at a time.
> 
> -   Reverting to a previous version does not delete other versions from the version history.
> 
> -   Use meaningful version comments to simplify tracking and maintenance of API artifacts.

