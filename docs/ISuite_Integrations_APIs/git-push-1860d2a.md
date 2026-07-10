<!-- loio1860d2a33fbc4477882a13cf9bf3e52b -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Git Push

Git Push is a Git operation used to upload local changes from an integration artifact to a connected remote Git repository, ensuring that the repository is updated with the latest modifications.



## Prerequisites

Ensure that repositories are configured by your tenant administrator. See [Git Access](IntegrationSettings/git-access-ae173b0.md)



## Procedure

1.  Choose *Design* \> *Integrations and APIs* to view the list of integration packages.

2.  Select the required integration package and choose *Artifacts* to view the list of artifacts available in the integration package.

3.  On the artifact, choose <span class="SAP-icons-V5"></span> and *Git Push*.

4.  In the *Push* dialog box, enter the *PAT Token*.

5.  Choose the *Repository Name*.

    > ### Note:  
    > If the selected artifact is imported from a GitHub Repository, the details will be auto populated in the *Push* dialog box.

    *Repository URL* will be auto populated.

6.  Choose the *Branch* from the list.

    > ### Note:  
    > One artifact can be mapped to one branch only.

7.  Enter a *Commit Message*.

8.  Choose *Push*.


