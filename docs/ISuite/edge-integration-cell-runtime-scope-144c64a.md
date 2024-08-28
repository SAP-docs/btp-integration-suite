<!-- loio144c64af999f4cda8c9b1912ac1edb92 -->

# Edge Integration Cell Runtime Scope



<a name="loio144c64af999f4cda8c9b1912ac1edb92__section_rlx_rmq_lvb"/>

## Runtime Scope

This section describes the scope when working with Edge Integration Cell. Refer to the SAP Note [3391207](https://me.sap.com/notes/3391207), to know more about the out of scope actions for Edge Integration Cell.


<table>
<tr>
<th valign="top">

Resource

</th>
<th valign="top">

Scope

</th>
</tr>
<tr>
<td valign="top">

Integration content

</td>
<td valign="top">

500 MB

Refer to the SAP Community blog: [Content Size Limits](https://blogs.sap.com/2020/08/02/cloud-integration-content-size-limits/)

</td>
</tr>
<tr>
<td valign="top">

X.509 keystores

</td>
<td valign="top">

max. 20

</td>
</tr>
<tr>
<td valign="top">

Number of runtimes associated with a credential or X.509 keystore

</td>
<td valign="top">

max. 20

</td>
</tr>
<tr>
<td valign="top">

Message processing log \(MPL\) persistence

</td>
<td valign="top">

Depends on database storage size.

See: [Cloud Integration – Setting the Log Level for Message Processing](https://blogs.sap.com/2017/06/22/cloud-integration-setting-the-log-level-for-message-processing/)

</td>
</tr>
<tr>
<td valign="top">

Data store message persistence

</td>
<td valign="top">

Depends on database storage size.

See: [Optimize Performance](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/491c80d16c3547c3b124cf38857f1332.html)

</td>
</tr>
<tr>
<td valign="top">

Disk space

</td>
<td valign="top">

Depends on cluster node storage size.

See: SAP Note [2648415](https://me.sap.com/notes/2648415) to learn how to optimize the integration flow development in such a way that the integration flow doesn't run into the `No More Space left on Disk` error.

</td>
</tr>
<tr>
<td valign="top">

X.509 keystore

</td>
<td valign="top">

1 MB

</td>
</tr>
<tr>
<td valign="top">

PGP keyrings \(secring & pubring\)

</td>
<td valign="top">

1 MB

</td>
</tr>
<tr>
<td valign="top">

Known Host file

</td>
<td valign="top">

1 MB

</td>
</tr>
<tr>
<td valign="top">

JDBC data sources

</td>
<td valign="top">

500 per edge runtime

</td>
</tr>
<tr>
<td valign="top">

Max. number of credentials for the following four credential types combined:

-   User Credential

-   Secure Parameter

-   OAuth2 Client Credentials

-   OAuth2 SAML Bearer Assertion


> ### Note:  
> OAuth2 Authorization Code credential isn't supported in Edge runtime.



</td>
<td valign="top">

500 per runtime

</td>
</tr>
<tr>
<td valign="top">

JMS resources

</td>
<td valign="top">

Depends on cluster node storage size.

See: [JMS Resource Limits for Edge Integration Cell](50-Development/jms-resource-limits-for-edge-integration-cell-17366b3.md)

</td>
</tr>
</table>

> ### Note:  
> *Delay Software Update*
> 
> The Delay Software Update feature isn't available for Edge Integration Cell, because customers manage the edge nodes themselves.

