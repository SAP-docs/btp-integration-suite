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
> -   The category *Clean Code Checks* is available now. This category includes incompatibilities like unused and duplicate import statements in your scripts.
> 
> -   The automatic suggestions are only supported for Groovy-based scripts.



## Procedure

1.  Open your local Groovy script.

2.  In the *Problems* view, look out for different categories of checks.

3.  In the *Clean Code Checks* category, check if there are incompatibilities found in any of the grouping.

4.  Navigate to each incompatibility check and understand the problem.

5.  Choose *Fix* to let the script editor resolve the problem for you.

6.  In the *Fix Incompatibility* dialog, read about the improvisation the editor makes. Choose *Fix* to resolve all occurences of the problem.

7.  Choose *Apply*.

    > ### Note:  
    > If you choose not to fix the problems, you can still deploy the integration flow.

8.  To navigate back to the integration flow, choose *Close*.

9.  Save the integration flow


