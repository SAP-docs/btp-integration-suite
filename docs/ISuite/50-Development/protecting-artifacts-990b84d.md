<!-- loio990b84d5a1ee48e7b66dc3da634e7a61 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Protecting Artifacts

Restrict write access to some artifacts in Integration Advisor by protecting them.



## Prerequisites

Your user in SAP BTP cockpit must have the role `ExtendedContentDeveloper` assigned.



## Context

If you want to restrict write access to certain artifacts so they can't be edited by every user in your organization, you can add a layer of **protection** to them. Only users with the relevant rights can edit protected artifacts or revoke the protection.

Users with the role `ExtendedContentDeveloper` can then protect and unprotect artifacts as well as edit protected artifacts. See also [Results](protecting-artifacts-990b84d.md#loio990b84d5a1ee48e7b66dc3da634e7a61__protect_results).

You can protect the following artifacts in Integration Advisor:

-   Message implementation guidelines \(MIGs\)

-   Mapping guidelines \(MAGs\)

-   Global code value mappings \(GCVMs\)

-   Custom codelists




## Procedure

1.  In SAP Integration Suite, go to the artifact that you want to protect:

    -   Message implementation guideline: *Design* \> *MIGs*
    -   Mapping guideline: *Design* \> *MAGs*
    -   Global code value mapping: *Design* \> *MAGs* \> *Code Value Mappings*
    -   Custom codelist: *Design* \> *Custom Type Systems* \> *Custom Codelists* and expand a codelist entry to see all versions.

2.  For the relevant artifact, choose <span class="SAP-icons-V5"></span> More Options, then choose *Protect MIG*/*Protect MAG**/Protect GCVM**/Protect Codelist*.

    You can also open the artifact in the detail view and choose <span class="SAP-icons-V5"></span> More Options, then choose *Protect MIG*/*Protect MAG**/Protect GCVM**/Protect Codelist*.

3.  In the overview and on the detail screen of the artifact, the protection status is now shown through the :shield: icon.

    To reverse the protection, choose <span class="SAP-icons-V5"></span> More Options, and then *Unprotect MIG*/*Unprotect MAG**/Unprotect GCVM**/Unprotect Codelist*.




<a name="loio990b84d5a1ee48e7b66dc3da634e7a61__protect_results"/>

## Results



### User Access

Users **with** the role `ExtendedContentDeveloper` have the following rights:

-   Protect and unprotect artifacts

-   Full write access to all protected and unprotected artifacts

    Note that if you protect an artifact and then activate it, the activated artifact is protected as well.


For users **without** the role `ExtendedContentDeveloper`, the following applies:

-   Unprotected artifacts: Full write access

-   Protected artifacts: Read and export \(runtime artifacts, documentation as PDF/XLS, ZIP\); also, you can copy protected artifacts and migrate protected MIGs since this creates new artifacts that are unprotected by default.

    Editing, activating, creating new draft versions, and overwriting through import are **not possible**. Drafts created from a protected artifact are protected as well.




### Exporting/Importing Protected Artifacts

The following rules apply to the export and import of protected artifacts:

-   Protection is a tenant-local setting, so it's not automatically transferred to a different tenant if you export or import an artifact. To protect an artifact in another tenant, you need to explicitly protect it after the first import.

-   You can export protected artifacts.

-   Users without the require role can import currently protected artifacts that are not updated, but can't import artifacts that need to be updated.

    For example, if your unprotected MAG uses a MIG that's protected in the target tenant, you can import your MAG only if the protected MIG hasn't changed. Once you'd need to overwrite the MIG because it was changed, you can't import the MAG.


