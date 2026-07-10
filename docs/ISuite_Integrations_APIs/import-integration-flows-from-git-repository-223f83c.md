<!-- copy223f83c8d9254f6e89e8eda6a8ef999e -->

# Import Integration Flows from Git Repository



## Prerequisites

-   Ensure that repositories are configured by your tenant admin. See [Git Access](IntegrationSettings/git-access-ae173b0.md) 
-   Your Personal Access Token must have sufficient permissions to access the added GitHub repositories.



## Context

You can create an integration flow by importing it from one of the already added GitHub repositories.



## Procedure

1.  Choose *Design* \> *Integrations and APIs* to view the list of integration packages.

2.  Select the integration package in which you want to add an integration flow and choose *Edit*.

3.  Navigate to the *Artifacts* tab and choose *Add* \> *Integration Flow*.

4.  In the *Add Integration Flow* dialog, choose the method *Add Integrations Manually*.

    > ### Note:  
    > This step is only applicable if you have **Premium** plan. For more information about different service plans and their supported feature set, see [2903776](https://me.sap.com/notes/2903776)

5.  Choose *Git Import* to import an integration flow from Git repository, then execute the following substeps:

    1.  Enter the *PAT Token*.

    2.  Choose *Repository Name* from the list. The repositories are configured in the [Git Access](IntegrationSettings/git-access-ae173b0.md) tab by tenant administrator.

        *Repository URL* will be auto populated.

    3.  Choose the *Branch*.

    4.  Choose the *Integration Flow*.

    5.  Choose *Add* to just create an integration flow or *Add and Open in Editor* to open the integration flow in its editor.





## Results

-   An integration flow from the selected Git repository, is imported and created.

-   You can now perform the [Git Operations](using-git-operations-68d2d79.md) on this imported integration flow.


