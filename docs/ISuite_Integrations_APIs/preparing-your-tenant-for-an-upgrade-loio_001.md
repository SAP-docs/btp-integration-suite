<!-- loio_upgrade_readiness_autofix_deploy_001 -->

# Preparing Your Tenant for an Upgrade

Use the *Prepare for Upgrade* screen to identify incompatible integration artifacts on your tenant, automatically fix eligible artifacts in bulk, deploy the fixed versions, and revert any deployments that fail. This task is performed by a tenant administrator before a planned SAP upgrade to ensure that all integration artifacts remain functional after the upgrade.



<a name="loio_upgrade_readiness_autofix_deploy_001__prereq"/>

## Prerequisites

Before you begin, ensure the following conditions are met:

-   You have the *Tenant Administrator* role in SAP Integration Suite.
-   An SAP upgrade is scheduled for your tenant.
-   Integration artifacts \(integration flows, script collections, APIs\) are deployed on your tenant.
-   You have reviewed the upgrade announcement and are aware of the target runtime version.



<a name="loio_upgrade_readiness_autofix_deploy_001__context"/>

## Context

The *Prepare for Upgrade* screen guides you through four phases:

| Phase | What You Do |
|---|---|
| **Phase 1 – Scan and Review** | Review the compatibility summary and identify which artifacts are incompatible with the target version. |
| **Phase 2 – Auto-Fix** | Select eligible artifacts and run bulk Auto Fix. The system creates a new artifact version, fixes supported incompatibilities, and imports required libraries. |
| **Phase 3 – Deploy** | Select fixed artifacts from the *Ready to Deploy* queue and deploy them to your tenant in bulk. |
| **Phase 4 – Revert \(if needed\)** | If a deployment fails, revert the artifact to its last stable version and return it to the auto-fix queue for re-processing or manual remediation. |

The entire workflow is accessible from the single *Prepare for Upgrade* screen. You do not need to navigate away at any point.



<a name="loio_upgrade_readiness_autofix_deploy_001__steps"/>

## Procedure

**Phase 1: Review Incompatible Artifacts**

1.  In SAP Integration Suite, go to *Modernize* \> *Upgrade Readiness* \> *Prepare for Upgrade*.

2.  On the *Prepare for Upgrade* screen, review the *Artifact Compatibility Summary* tile. It shows the proportion of compatible and incompatible artifacts on your tenant.

3.  In the *Manage Incompatible Artifacts* section, review the metric tiles:

    -   *Scripts* — total incompatible script files
    -   *Packages* — packages that contain incompatible artifacts
    -   *Artifacts* — individual incompatible integration flows and script collections
    -   *REST, SOAP, and OData APIs* — incompatible API artifacts

    Choose any tile to open the corresponding detail table and inspect individual items.

4.  In the *Fix and Deploy* section, note the *Ready to Auto Fix* tile. It shows the number of artifacts that are eligible for Auto Fix. Choose the tile to open the *Manage Artifacts Ready to Auto Fix* screen.

**Phase 2: Auto-Fix Eligible Artifacts**

5.  On the *Manage Artifacts Ready to Auto Fix* screen, the *Ready to Auto Fix* tab is active by default. The table lists all artifacts that can be fixed automatically.

    > ### Note:  
    > Artifacts that require manual remediation are listed in the detail tables accessible from the metric tiles \(Step 3\). The Auto Fix table shows only eligible artifacts.

6.  To select artifacts for Auto Fix, do one of the following:

    -   Select the checkbox in the table header to select all eligible artifacts.
    -   Select the checkboxes in individual rows to select specific artifacts.

    The *Auto Fix* button becomes active in the toolbar when at least one artifact is selected.

7.  Choose *Auto Fix*.

8.  In the *Auto Fix* dialog, review the summary:

    -   For integration flows: the system creates a new artifact version, analyzes each script, fixes supported incompatibilities, imports required libraries, and saves the changes.
    -   For API artifacts \(REST, SOAP, OData\): the system converts each API artifact to an integration flow as part of the upgrade.

    Choose *Auto Fix* to proceed, or choose *Cancel* to return to the table.

9.  After you confirm, each selected artifact shows an *In Progress* status indicator in the *Fix Status* column. You can continue reviewing other artifacts while processing runs.

10. When processing completes, each artifact shows one of the following statuses:

    -   *Fixed* — the artifact was fixed successfully and is ready for deployment.
    -   *Failed* — the artifact could not be fixed automatically.

    If an artifact shows *Failed*:

    -   Hover over or expand the row to view the failure reason.
    -   Choose *Download Log* in the toolbar to download the full fix log for further analysis.
    -   Artifacts that failed Auto Fix remain in the *Ready to Auto Fix* tab. You can attempt Auto Fix again, or open the artifact in your design workspace to resolve the issue manually and redeploy it. Manual changes appear in the table after you deploy the artifact.
    -   If you require assistance, create a support case.

**Phase 3: Deploy Fixed Artifacts**

11. Choose the *Ready to Deploy* tab. The tab label shows a badge with the number of artifacts ready for deployment.

    The table lists all artifacts whose Auto Fix succeeded. The *Deployment Status* column shows *Ready* for each artifact.

12. To select artifacts for deployment, do one of the following:

    -   Select the checkbox in the table header to select all artifacts in the queue.
    -   Select the checkboxes in individual rows to select specific artifacts.

    The *Deploy* button becomes active in the toolbar when at least one artifact is selected.

13. Choose *Deploy*.

14. In the *Deploy* dialog, review the artifact count and any warnings. Choose *Deploy* to proceed, or choose *Cancel* to return to the table.

15. After you confirm, each selected artifact shows an *In Progress* status indicator in the *Deployment Status* column.

16. When deployment completes, each artifact shows one of the following statuses:

    -   *Deployed* — the artifact was deployed successfully.
    -   *Failed* — the deployment failed.

    To monitor deployment progress in detail, choose *Open Monitoring* in the toolbar.

    If an artifact shows *Failed*, proceed to Phase 4.

**Phase 4: Revert a Failed Deployment \(If Needed\)**

17. In the *Ready to Deploy* table, locate the artifact with *Failed* deployment status.

18. Do one of the following to initiate a revert:

    -   Select the checkbox for the failed artifact, then choose *Revert* in the toolbar.
    -   Choose the revert icon in the *Action* column of the failed artifact's row.

19. In the *Revert* dialog, review the revert description: the artifact is restored to the last stable version, and the restored artifact moves to the *Ready to Auto Fix* queue.

    Choose *Revert* to proceed, or choose *Cancel* to return to the table.

20. A confirmation notification confirms that the revert was successful.

21. Choose the *Ready to Auto Fix* tab. The reverted artifact appears with a *Reverted* marker. You can now select it and run Auto Fix again \(from Step 6\), or open it in your design workspace for manual remediation.



<a name="loio_upgrade_readiness_autofix_deploy_001__result"/>

## Results

After completing this procedure, you have:

-   Identified all incompatible integration artifacts on your tenant.
-   Auto-fixed and deployed the eligible artifacts in bulk.
-   Resolved deployment failures by reverting affected artifacts to their last stable state.

Your tenant is prepared for the upcoming SAP upgrade. Artifacts that required manual remediation remain in the *Ready to Auto Fix* queue for further action.

**Related Information**  


[Ensure Upgrade Readiness](ensure-upgrade-readiness-6adb0ca.md "Design guidelines to create and maintain integration artifacts that are clean, consistent, and prepared for future runtime version upgrades.")

[Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md "Fix the incompatibilities in the scripts that are automatically identified by the script editor.")
