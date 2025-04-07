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
<tr>
<td valign="top">

Duplicate Target Nodes

</td>
<td valign="top">

-   Duplicated target nodes in the Base MAG are not automatically propagated to the Overlay MAG.
-   As a workaround, you can manually duplicate the same target nodes in your Overlay MAG to achieve the desired outcome.



</td>
</tr>
<tr>
<td valign="top">

Pretransformation

</td>
<td valign="top">

-   Pretransformations defined in the Base MAG are not automatically propagated to the Overlay MAG.
-   As a workaround, you can manually redefine the same Pretransformation in your Overlay MAG to achieve the desired outcome.



</td>
</tr>
</table>

