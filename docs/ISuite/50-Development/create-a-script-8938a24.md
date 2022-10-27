<!-- loio8938a245c7ba4cf08dc1b20d4bb9b1e7 -->

# Create a Script

This topic desribes how to create a FileResource \(also called Script\).



## Prerequisites

-   You are familiar with the concept of Scripts. For more information, see [File Resource](file-resource-79299d3.md).

-   You have the payload of the Script that you want to create.




## Context

Script is a FileResource or code snippet that is attached to Flows using policies. SAP Integration Suite. supports the creation of JavaScript, Python, and XSL scripts.

**Context**: You are creating an API proxy and want to add a script to it.



## Procedure

1.  While creating an API proxy, navigate to the *Policies on API* tab page.

2.  Select *Invoke Policy Designer*.

3.  Select the icon + \(*Add*\) beside the *Scripts* section at the bottom-left of the Policy Designer.

4.  Enter a name for the script.

5.  From the *Type* field, select one of the following options:

    -   *JavaScript*
    -   *Python*
    -   *XSL*

6.  Choose *Add*.

    The added script appears under the *Scripts* section.

7.  Select the Script you created and provide the script details in the editor.

8.  Choose *Save*.

    You can reference the scripts from a Java Script policy, Python policy or XSL Transform policy.


