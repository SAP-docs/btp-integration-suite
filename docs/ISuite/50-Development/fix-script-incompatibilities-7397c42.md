<!-- loio7397c42f0fea40eeb64a35d0d099af6e -->

# Fix Script Incompatibilities

Fix the incompatibilities in the scripts that are automatically identified by the script editor.



<a name="loio7397c42f0fea40eeb64a35d0d099af6e__prereq_d2f_spq_kdc"/>

## Prerequisites

[Define a Local Script Step](define-a-local-script-step-03b32eb.md)



## Context

The script editor helps you keep your custom scripts clean by highlighting the incompatibilities and suggesting ways to fix them. It is important to consider these guidelines so that your custom scripts are future-ready. Also, the scripts become independent of the changes triggered owing to dependency with open source library upgrades.

The script editor categorizes the incompatibilities and further groups into errors, warnings, and information.

> ### Note:  
> -   The automatic suggestions are only supported for Groovy-based scripts.



## Procedure

1.  Open your local Groovy script.

2.  In the *Problems* view, look out for different categories of checks.

    -   Upgrade Readiness Check: This category includes incompatibilities like unused and duplicate import statements, unsupported classes in your scripts. See [Groovy Script](https://help.sap.com/docs/integration-suite/sap-integration-suite/groovy-script?state)
    -   General Script Check: This category includes general script checks. See [Use Scripting Appropriately](https://help.sap.com/docs/integration-suite/sap-integration-suite/use-scripting-appropriately?state)

3.  Navigate to each tab and find the incompatibilities or issues in the script.

4.  Choose *Fix* to let the script editor resolve the problem for you. If an automatic fix is not available, choose *Show More* to view the details of the incompatibility or issue.

5.  In the subsequent dialog box, read about the improvement the editor makes. Choose *Fix* to resolve all occurrences of the problem. After a successful fix, the incompatibility is removed from the Problems view.

6.  Choose *Apply*.

    > ### Note:  
    > If you choose not to fix the problems, you can still deploy the integration flow.

7.  To navigate back to the integration flow, choose *Close*.

8.  Save the integration flow.


