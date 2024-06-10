<!-- copyaf8dcd6ea0164a8594640ee24d3e6d1d -->

# Custom Entities

Custom entities are created by a skilled customer modeler to extend the data graph, by designing and adding their own projections as a collection of attribute mappings from available SAP and non-SAP data source entities. The modeler can submit a set of custom entity definition files, developed with a text editor of their choice.

The ability to extend the SAP data graph with custom entities is a powerful capability – customers can essentially design their own corporate data model. Here are some of the advantages:



<a name="copyaf8dcd6ea0164a8594640ee24d3e6d1d__section_fd1_lpy_gvb"/>

## Use the Same Protocols

By mediating your data sources as a data graph, developers enjoy the use of a single data endpoint, a simplification of access and security, and the consistent use of the same query language and protocol. Investments in client-side SDKs, frameworks, and data access abstractions apply to all of the data sources.



<a name="copyaf8dcd6ea0164a8594640ee24d3e6d1d__section_py3_mpy_gvb"/>

## Create Your Own API Shape

From simple renaming, to more powerful transformations, custom entities allow you to control how the data is perceived by app developers. You can:

-   Replace an existing entity with one that is simpler to understand, by filtering out unnecessary or undesired attributes.

-   Rename entities and attributes to match a consistent corporate or SAP data naming convention.

-   Design your interface to precisely match the API expectations of application developers, or of existing applications.




<a name="copyaf8dcd6ea0164a8594640ee24d3e6d1d__section_dz1_vpy_gvb"/>

## Hide Landscape Inconsistencies

Hide incompatibilities between data-source variations or versions as an abstraction. This is useful while preparing for major system upgrades or migrations involving API incompatibilities. Custom entities can hide such API changes, providing you with more control over how to implement the migration, while not breaking dependent applications.



<a name="copyaf8dcd6ea0164a8594640ee24d3e6d1d__section_vy2_xpy_gvb"/>

## Add or Change Semantics

-   Replace a hard-to-understand normalized data representation \(often representing the way that the data is stored\) into a denormalized view that is easier to consume by client applications.

-   Connect separate entities \(with string-type foreign keys\) into a navigable graph of entities, by introducing associations and compositions into the graph.

-   Turn associations into compositions \(to many\) or a structured type \(of one\), making the semantics of the relationship more obvious to understand for consumers.

-   Combine attributes from separate source entities into one virtual, composed entity. Combine data attributes into compositions that hide underlying implementation technicalities. A common example is a side-car extension, such as a CAP-created application that extends an SAP S/4HANA data model, such as a `BusinessPartner`. Using custom entities, you can present a new natural entity with attributes from both.

    > ### Note:  
    > Certain restrictions apply, such as the inability to guarantee atomic data modification, when writing back to two separate data sources.




<a name="copyaf8dcd6ea0164a8594640ee24d3e6d1d__section_agn_hqy_gvb"/>

## Introduce More Control and Security

In many cases, IT administrators can use Graph to avoid the need to create data copies, replications, and complex ETLs \(Extract Transform Load\) to serve the need for simpler data APIs for certain application developers and use cases. Administrators can do the following:

-   Secure their data, by only exposing data that is safe to use.

-   Using a data-filter, custom entities can be used to systematically access only a subset of.data.

-   Projections can support finer-grain authorization: a custom entity can be read-only, for example, while the underlying entities are not.


