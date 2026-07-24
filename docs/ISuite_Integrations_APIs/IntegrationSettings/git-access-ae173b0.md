<!-- loioae173b0eaea9430cba52240728b97052 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Git Access

Cloud Integration enables seamless integration of web based online platform, GitHub into the design time lifecycle of integration content. It helps teams improve collaboration, governance, and delivery speed by aligning integration development with standard Git workflows and CI/CD practices.



## Adding GitHub Repositories

**Prerequisite**

-   You've tenant admin role assigned to your user. See [Personas for Cloud Integration](../60-Security/personas-for-cloud-integration-2937e5c.md)
-   Your Personal Access Token \(PAT\) must have sufficient permissions to access the added GitHub repositories.

    > ### Note:  
    > To generate a PAT token, login to your GitHub account. From your profile, navigate to *Settings* \> *Developer Settings* \> *Personal Access Tokens* \> *Fine-Grained Tokens or Tokens \(Classic\)* \> *Generate New Token*.




### Procedure

1.  Navigate to *Settings* \> *Integrations* and choose *Git Access*.
2.  Choose *Edit* below the *Repository Details* table.
3.  Choose *Add*.
4.  In the dialog, enter the *PAT token*.
5.  Enter the *Repository URL*.
6.  Choose *Connect* to establish the connection with the repository to be configured.

    The Repository Name and Descriptions are auto populated from GitHub.

7.  Choose *Add*.

    The repository details will be added in the table.

    > ### Note:  
    > You can configure maximum up to 50 repositories.

8.  Choose *Save*.




### Results

Once repositories are added by the Tenant Administrator, Integration Developers can perform the following actions:

-   **[Import](https://help.sap.com/docs/integration-suite/integrations-and-apis/creating-integration-flow?state=CLOUD#import-integration-flows-from-git-repositories) Artifacts**: Import integration artifacts directly from a selected repository branch of a configured GitHub repository.
-   **[Push](../git-push-1860d2a.md) Artifacts**:
    -   Push integration artifacts from the design view to a selected repository branch.


-   **[Pull](../git-pull-013867f.md) Artifacts**:
    -   Pull integration artifacts from a repository branch into the design view.





## Edit GitHub Repository

On the *Git Access* tab, you can modify the repository details

1.  Choose *Edit* and :pencil2:, to update the repository URL and PAT Token.

2.  Choose *Connect* \> *Update* \> *Save*.


