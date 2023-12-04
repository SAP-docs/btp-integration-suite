<!-- loio58097acbb3944aadbb3b3d41b597a5cd -->

# API Revisions

With API revisions, you can make incremental changes to an API proxy without causing any disruption to the deployed API. Access the past changes made to the API proxy, and even restore the API to any of its previous states.

In this table, we’ve summarized the key features of API versions and API revisions :


<table>
<tr>
<th valign="top">

API Revision

</th>
<th valign="top">

API Version

</th>
</tr>
<tr>
<td valign="top">

Revisions typically include small incremental and compatible changes. For example, adding a property or adding a new resource or a policy to an API proxy. You create revisions when there are changes that don't break the existing consumption flows. API revisions are agnostic of the actual URL that is used for consuming the API. Since the deployed revision is being consumed, you don't have to access it separately. The API proxy URL doesn't change across revisions of an API proxy.

</td>
<td valign="top">

An API version helps you to track incompatible changes made to an existing API proxy. For example, you’re already consuming version 1 of an API proxy, now in version 2 some incompatible changes are done, like changing the data types of the properties, or removing an existing policy or a property. For such incompatible changes, the newer version is made available for consumption and you can adopt it by migrating to the newer version. Since versions are individually accessible for consumption, the version number appears on the URL as shown here: `http://host/api/v2/customers/123` 

</td>
</tr>
<tr>
<td valign="top">

Only one revision of an API proxy exists in the runtime. You can view the different revisions in the design time, and compare the contents of different revisions.

</td>
<td valign="top">

Multiple versions of an API can coexist in the runtime for consumption as every version has a different API proxy URL with the version information. In design time, a new API proxy gets created for every version.

</td>
</tr>
</table>

