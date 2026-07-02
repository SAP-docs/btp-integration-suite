<!-- loioefb1ec1acd4d41a7aae366b6a9f92f60 -->

# Matching Rules for Overlay Mapping Guidelines

Matching rules that define how identifiers in base and overlay mapping guidelines are mapped to each other.



According to the basic matching rules, same identifiers in base and overlay MAG are mapped.

For example, the segment group **SG1 in the base** is mapped to the segment group **SG1 in the overlay mapping guideline** because they have the same identifier, **SG1**.

If there are **structural differences** between base and overlay mapping guidelines, the mapping line can’t be drawn and throws an error. In these cases, the identifier in the base mapping guidelines couldn’t be mapped to a corresponding identifier in the overlay mapping guideline.

While errors exist in your mapping, you can’t simulate the mapping guideline. Exclude these erroneous base mappings. They’re shown as missing elements in the mapping list.



## Extended Mapping Rules



### Special Mapping Rules for EDIFACT

For EDIFACT mapping guidelines, extended matching rules apply.

If the structure of an EDIFACT overlay mapping guideline is changed, the numbering of segment groups changes as well. This leads to mismatches in the identifiers between base and overlay mapping guideline.

For example, a **base** mapping guideline looks as follows:

-   SG1
    -   ADDRESS

-   SG2
    -   NAME


Due to an update to the EDIFACT **overlay** mapping guideline, its structure has been changed to look as follows, with the segment group identifiers no longer corresponding to those of the base mapping guideline:

-   SG1
    -   DATE

-   SG2
    -   ADDRESS

-   SG3
    -   NAME


If the matching followed the basic matching rules, the mapping of **SG1 \(base\)** would **fail** since ADDRESS and DATE can’t be matched.

Instead, the **extended matching** recognizes that the trigger segments match and therefore matches **SG1 \(base\) - ADDRESS** with **SG2 \(overlay\) - ADDRESS**. The matching is therefore defined through the **trigger segment** and the mapping line is automatically rerouted.

You can still edit overlay mapping guidelines yourself and disable nodes manually if a mapping is erroneous.



### Mapping Segments That Moved to Segment Groups

A segment in a base mapping guideline could be moved to a segment group in an overlay mapping guideline, or the other way around. This mapping rule ensures that the segments can still be mapped.

For example, a **base** mapping guideline looks as follows:

-   LIN
-   MOA

In the corresponding **overlay** mapping guideline, the segment `MOA` has been moved and now sits within the segment group `SG27`:

-   LIN
-   SG27
    -   MOA


With the extended matching rules, the segments can still be mapped, even though it's been moved one layer deeper in the overlay mapping guideline.



### Mapping Data Elements That Moved to Composites

A data element in a base mapping guideline could be moved to a composite data element in an overlay mapping guideline, or the other way around. This mapping rule ensures that the data elements can still be mapped.

For example, a **base** mapping guideline looks as follows:

-   C002
-   1004
-   1225

In the corresponding **overlay** mapping guideline, the data element `1004` has been moved and now sits within the composite `C106`:

-   C002
-   C106
    -   1004

-   1225

With the extended mapping rules, the data elements can still be mapped, even though it's been moved one layer deeper in the overlay mapping guideline.

