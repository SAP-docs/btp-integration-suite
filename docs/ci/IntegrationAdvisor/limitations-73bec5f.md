<!-- loio73bec5f173ae4d27a1d23908a9da62cd -->

# Limitations

The following limitations should be considered when working with an overlay MAG.

**Limitations**


<table>
<tr>
<th valign="top">

Limitation

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Shared Code

</td>
<td valign="top">

-   Base Mapping Elements can use Shared Code defined in the Base MAG, which will be considered in the Overlay MAG.
-   Overlaid Mapping Elements can use Shared Code defined in the Overlay MAG.
-   Overlaid mapping elements cannot reference Shared Code defined in the Base MAG.

> ### Note:  
> Shared Code definitions must have a unique name across both Base and Overlay MAGs.



</td>
</tr>
</table>



<a name="loio73bec5f173ae4d27a1d23908a9da62cd__Limitations_DuplicateTargetNodes"/>

## Duplicate Target Nodes in Overlay MAGs

> ### Note:  
> The behavior of duplicate target nodes in MAGs has changed with release 2601 \(March 2026\). The following migration considerations apply only to overlay MAGs created before that release.

Integration Advisor has improved the handling of duplicate target nodes in base and overlay MAGs. Originally, target node duplicates from the base MAG weren’t visible in the overlay MAG. While you could duplicate target nodes in the overlay MAG, they weren’t linked with existing duplicates in the base MAG and could therefore lead to conflicts.

Now, target node duplicates from the base MAG are visible in the overlay MAG. The target node duplicates defined in an overlay MAG are also explicitly stored as overlay duplicates to allow side-by-side duplicates from base MAG and overlay MAG.

With release 2601, all overlay MAGs with duplicates are migrated once accessed. The finished migration is indicated by a warning icon in the Status column in the MAG editor for the relevant nodes. In most cases, the previous mapping is still valid, but in some edge cases, the mapping behavior can have changed. Therefore, it’s advised that you **check if your mapping is still valid and produces the same mapping output**.

The automatic migration has the following effects:

-   Duplicate target nodes from the base MAG are now visible in the overlay MAG.
-   Base mapping elements pointing to the base duplicate nodes are now valid in the overlay MAG and can be used.

    > ### Note:  
    > If you ever disabled these mapping elements because they were invalid, you can enable them again now.

-   Earlier defined duplicate target nodes from overlay MAGs are automatically migrated to the new overlay duplicates.
-   Earlier defined overlay mapping elements by default now point to the overlay duplicates. Therefore, **check that your original mapping still works as intended**

For more information and illustrative examples, see the blog [Integration Advisor - Base Duplicate Nodes in Overlay Mapping and Automatic Migration](https://community.sap.com/t5/integration-blog-posts/integration-advisor-base-duplicate-nodes-in-overlay-mapping-and-automatic/ba-p/14330637).

