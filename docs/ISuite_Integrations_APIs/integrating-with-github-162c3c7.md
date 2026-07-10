<!-- loio162c3c7d61d7437b8cdad6c2b3e14c65 -->

# Integrating with GitHub

GitHub is a cloud-based platform used to store, manage, and track changes in code using Git. It enables collaboration, version control, and supports CI/CD workflows.

With Cloud Integration, you can connect GitHub repositories and perform Git operations directly from your tenant.



## Key Benefits

-   Efficiency & Simplicity
    -   Perform Git import, pull, and push directly
    -   Simplifies artifact management with repository/branch visibility


-   Collaboration & Control
    -   Enables team collaboration with shared repositories and version tracking
    -   Ensures traceability with clear history and easy rollback


-   Reliability & Scalability
    -   Reduces errors with structured sync
    -   Provides backup and supports CI/CD-ready workflows




## Workflow

The GitHub integration follows a simple workflow across roles:

1.  Configure GitHub Connection \(Tenant Administrator\)

    The tenant administrator sets up the GitHub repository connection and authentication. For instructions, see [Git Access](IntegrationSettings/git-access-ae173b0.md).

2.  Import Integration Flow \(Integration Developer\)

    Import or clone integration flow from a GitHub repository and branch into the tenant. See [Import](https://help.sap.com/docs/integration-suite/integrations-and-apis/creating-integration-flow?state=CLOUD#import-integration-flows-from-git-repositories)

3.  Git Operations \(Integration Developer\)

    Use Git operations to keep artifacts up to date:

    -   Pull: Retrieve the latest changes from the repository. See [Git Pull](git-pull-013867f.md) 
    -   Push: Save local changes back to the repository. See [Git Push](git-push-1860d2a.md)

4.  Track and Monitor \(Integration Developer\)

    You can track the deployed integration flow as usual and also view the repository and branch details for these artifacts in the monitoring view to ensure transparency. See [Manage Integration Content](manage-integration-content-09a7223.md)


**Related Information**  


[Personas for Cloud Integration](60-Security/personas-for-cloud-integration-2937e5c.md "When you perform user management tasks using SAP BTP cockpit, you find a set of predefined roles that you can assign to users of the account. According to the main tasks associated with integration projects, these roles are associated to certain persona relevant for an integration project.")

