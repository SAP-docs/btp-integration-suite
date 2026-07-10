<!-- loioc744df5a043f49059e8c224240eb51e5 -->

# **Working with Policies and Mediation Steps** 

A policy is a program that executes a specific function at runtime. Policies provide the flexibility to add common functionalities to an API without having to code them individually each time. They enable you to secure APIs, control API traffic, and mediate messages by transforming, mapping, routing, or persisting data as it flows through the API.

With **API-Centric Integration**, the API artifact allows you to combine both policy engine steps \(for security and traffic control\) and mediation steps \(for message processing and transformation\) within the same policy model—enabling you to design end-to-end API flows that address both governance and integration requirements.

> ### Note:  
> For **MCP server**artifacts, only the following policy engine steps are currently supported:
> 
> -   **Security**: Authentication and Authorization
> -   **Traffic Management**: Quota, Surge Protection, and IP Filter
> 
> Mediation steps \(such as Transformation, Mapping, Routing, Security, Persistence, Validator, Participant, Call, Process, and Event \) are not supported for MCP server artifacts at this time.

**Related Information**  


[Add Policies to Artifacts](add-policies-to-artifacts-c2b3e56.md "To enforce security or control traffic, you can set rules on the artifacts (APIs and MCP servers) by adding policies and integration steps to it.")

