<!-- loio65cc0bcf4e8c4b1f85d94242f6b5912b -->

# Configure Runtime Profile for an Integration Flow

You can use runtime profile in an integration flow, to develop content for a particular runtime.



## Prerequisites

-   Your user is assigned with integration developer role.
-   You have opened an integration flow in the editor.



## Context

Runtime profile is a collection of capabilities such as OData adapter, splitter or datastore elements, available for a particular product. You can consume these capabilities at the time of designing integration flows.

The tool enables you to design for multiple runtimes at the same time. You should select specific runtime profile to develop content for the respective runtime.

> ### Note:  
> If a runtime profile does not support a particular capability then the checks report errors for unsupported components in the integration flow.



## Procedure

1.  Choose the *Runtime Configuration* tab page.

2.  Select relevant runtime profile from the *Runtime Profile* dropdown list.

    > ### Note:  
    > -   If you want to publish content in the catalog, then it is a recommendation to select a specific runtime profile.
    > 
    > -   If you switch runtime profiles, then the system reloads the palette and displays relevant capabilities.

3.  Choose *Save* or *Deploy* as appropriate.


**Related Information**  


[Runtime Profiles](runtime-profiles-8007daa.md "Integration Suite allows you to design integration content for different target integration platforms. Accordingly, different runtime profiles are available to adapt the user interface of the integration content designer to the specifications and capabilities of the target integration platform.")

