<!-- loio6426313875e04271a062ed31fe797c0b -->

# Entities

Information and examples about entity and namespace names.



<a name="loio6426313875e04271a062ed31fe797c0b__section_d1v_5d3_bvb"/>

## Entity Names

A fully qualified entity name consists of two parts:

-   The namespace in which the entity is grouped.

-   The entity name, also known as the resource name.


Entity names contain only ASCII alphanumeric characters and underscores. By convention, entity names are singular and start with an uppercase letter and use upper CamelCase to mark word parts. Acronyms, when used, remain in capital letters. Technically, entity names match a regex.

Here are some examples of entity names:

-   `SalesOrder`

-   `HROrganizationUnit`

-   `MRPArea`

-   `AutomobilePart`




<a name="loio6426313875e04271a062ed31fe797c0b__section_zk2_2p3_bvb"/>

## Namespace Names

Namespaces are, by convention, all lowercase alphanumeric, but can also contain dots \(but not underscores\), to create a pseudo hierarchy. A common convention is to start the namespace with a unique company indicator. The namespaces `sap.*` and `graphql` are reserved for SAP, and can't be used.

Here are some examples of namespace names:

-   `bestrun`

-   `bestrun.hr`

-   `br.sales`


When writing out the full entity name, it's written as a single string with the last dot separating the namespace from the entity name. When using the full entity name in OData URLs, the namespace is considered a service name, and the entity name is considered the resource, separated from the service by a forward slash \(/\), rather than a dot. For example, to get a list of teachers called `Joan`, use the following query:

```
GET https://<subdomain>.a.integration.cloud.sap/graph/api/v1/my.new/Teacher?$filter=startswith(name,'Joan')
```

**Related Information**  


[Try Out Regular Expressions \(Regex\)](https://regex101.com/r/NKEN4r/1)

