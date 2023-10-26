<!-- loioeb2e6011a33b4c96a0a9a7d2353a47f0 -->

# Examples

Let's assume, you work with a message that contains an astronomical star catalogue. For each star, the following parameters are provided in the catalogue: its name, its distance from the Sun \(in light years\), and the spectral class.

Although we know of many more stars in our Galaxy, let's assume for reasons of simplicity that the star catalogue has the following content:

```
<starCatalogue>
	<star>
		<class>A</class>
		<name>Vega</name>
		<distance>25.04</distance>
	</star>
	<star>
		<class>A</class>
		<name>Deneb</name>
		<distance>1550</distance>
	</star>
	<star>
		<class>A</class>
		<name>Sirius</name>
		<distance>8.6</distance>
	</star>
	<star>
		<class>G</class>
		<name>Sun</name>
		<distance>0</distance>
	</star>
	<star>
		<class>G</class>
		<name>61 Ursae Majoris</name>
		<distance>31.24</distance>
	</star>
	<star>
		<class>G</class>
		<name>Epsilon Geminorum</name>
		<distance>840</distance>
	</star>
</starCatalogue>

```



<a name="loioeb2e6011a33b4c96a0a9a7d2353a47f0__section_lyf_hvn_kqb"/>

## Using Dynamic Parameters in the XPath Expression

You are interested in filtering the stars for a dedicated spectral class, but in your integration scenario the class parameter is set dynamically at runtime. In this case, configure the Filter step in the following way:


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

XPath Expression

</td>
<td valign="top">

/starCatalogue/star\[\(class le function:simple\('$\{property.class\}'\)\) and \(class ge function:simple\('$\{property.class\}'\)\)\]

</td>
</tr>
<tr>
<td valign="top">

Value Type

</td>
<td valign="top">

Nodelist

</td>
</tr>
</table>

If at runtime the value of exchange property `class` is `A`, the Filter step provides the following message:

```
<star>
	<class>A</class>
	<name>Vega</name>
	<distance>25.04</distance>
</star>
<star>
	<class>A</class>
	<name>Deneb</name>
	<distance>1550</distance>
</star>
<star>
	<class>A</class>
	<name>Sirius</name>
	<distance>8.6</distance>
</star>

```

If at runtime the value of exchange property `class` is `G`, the Filter step provides the following message:

```
<star>
	<class>G</class>
	<name>Sun</name>
	<distance>0</distance>
</star>
<star>
	<class>G</class>
	<name>61 Ursae Majoris</name>
	<distance>31.24</distance>
</star>
<star>
	<class>G</class>
	<name>Epsilon Geminorum</name>
	<distance>840</distance>
</star>

```



<a name="loioeb2e6011a33b4c96a0a9a7d2353a47f0__section_yrk_jvn_kqb"/>

## Filtering for Maximum Value of an Element

Let's assume you are interested to filter the catalogue for the star with the maximum distance from the sun.

In this case, configure the Filter step in the following way:


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

XPath Expression

</td>
<td valign="top">

/starCatalogue/star\[distance = max\(/starCatalogue/star/distance\)\]

</td>
</tr>
<tr>
<td valign="top">

Value Type

</td>
<td valign="top">

Node

</td>
</tr>
</table>

The Filter step provides the following message:

```
<star>
	<class>A</class>
	<name>Deneb</name>
	<distance>1550</distance>
</star>

```

Deneb, a star in the constellation of Cygnus, is the one with maximum distance from the Sun in our catalogue.



For more examples, check out the following SAP Community blog: [Cloud Integration – Filter component is enriched with XPath 3.1 capabilities](https://blogs.sap.com/2019/09/12/cloud-platform-integration-filter-component-is-enriched-with-xpath-3.1-capabilities/)

