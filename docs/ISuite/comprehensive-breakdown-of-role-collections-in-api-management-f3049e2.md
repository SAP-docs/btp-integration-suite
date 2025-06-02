<!-- loiof3049e2b70e748c5bca9e383b039e4e0 -->

# Comprehensive Breakdown of Role Collections in API Management

This comprehensive breakdown of API Management role collections provides a detailed overview of the various roles, their associated permissions, and how these roles contribute to the effective management and security of APIs.

The following table outlines these role collections, offering clarity on the responsibilities and access levels within an API Management environment:

****


<table>
<tr>
<th valign="top">

Entity

</th>
<th valign="top">

APIPortal.Administrator

</th>
<th valign="top">

APIPortal.Configurator

</th>
<th valign="top">

APIPortal.Developer

</th>
<th valign="top">

APIPortal.Tester

</th>
<th valign="top">

Notes

</th>
</tr>
<tr>
<td valign="top">

API proxies and policy templates

</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Copy
-   Import/Export
-   Discover
-   Debug
-   Transport



</td>
<td valign="top">

Can perform:

-   Read
-   Export
-   Transport



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Copy
-   Import/Export
-   Discover
-   Debug



</td>
<td valign="top">

Can perform:

-   Read
-   Debug



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Products

</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Publish
-   Transport



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Publish
-   Transport



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Publish



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Applications

</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

> ### Note:  
> Application read access is granted to all role combination, except for application key and secret information. The application key and secret information are considered sensitive or critical data, and access to this information is restricted.



</td>
</tr>
<tr>
<td valign="top">

API providers

</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Test Connection
-   Transport



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Test Connection
-   Transport



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Certificates

</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Transport



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Transport



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

> ### Note:  
> Security details of Certificates are not visible in read privilege.



</td>
</tr>
<tr>
<td valign="top">

Key value maps

</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Transport



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete
-   Transport



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Rate plan

</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Bills

</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Test Console

</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Settings

</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Virtual hosts

</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Cache Resources

</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Analytics

</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete



</td>
<td valign="top">

Can perform:

-   Create
-   Read
-   Update
-   Delete



</td>
<td valign="top">

Can perform:

-   Read



</td>
<td valign="top">

 

</td>
</tr>
</table>

