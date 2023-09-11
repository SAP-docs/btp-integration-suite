<!-- loio1b801fac95524074a58b4539a580f1c6 -->

# Consuming a Script Collection



<a name="loio1b801fac95524074a58b4539a580f1c6__prereq_nd3_5k4_npb"/>

## Prerequisites

[Creating Scripts in a Script Collection](creating-scripts-in-a-script-collection-ed9b52c.md)



## Context

Consuming a script collection is a two-step process.

-   In the first step, you create a reference to the script collection in your integration artifact.

-   In the next step, you create a script step at the desired position in your integration artifact and select a script from the referenced script collection.


To add a script to your integration artifact without using a script collection, see: [Define a Local Script Step](define-a-local-script-step-03b32eb.md).



## Procedure

1.  Open your integration artifact in edit mode.


Create a reference to the script collection

2.  In the property sheet for the integration artifact, choose *Resources* \> *References* \> *Add References* \> *Script Collection*.

    In the *References* dialog box, by default, script collections that are part of the integration package are listed. From the *Packages* list, select the other packages in the tenant to view the script collections available in them.

3.  Select one or more script collection artifacts to which you want to create a reference.

4.  Choose *OK*.


Create a script step and select a script resource

5.  At the desired position in your integration artifact, choose *Message Transformers* \> *Script*. Choose *Groovy Script* or *JavaScript* based on your requirements.

6.  In the quick action buttons, choose *Assign*.

7.  In the *Select Resource* dialog box, choose the *Reference Resources* tab.

8.  In the *Script Collection* list, select a referenced script collection artifact.

9.  In the *Resources* list, select a script resource and choose *OK*.

    > ### Note:  
    > The scripts that appear in the *Resources* list depend on the script type you chose in a previous step. For example, if you choose JavaScript during script definition, you only see the JavaScript files that are available in the package.

10. Choose *Save*.


