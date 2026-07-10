<!-- loio29868510f2c544219f100aace152347e -->

# Recommendations for Tasks and Permissions

Learn more about which role collections require extra consideration when assigning.

When assigning role collections, follow the principle of least privilege: Provide privileges according to the *need to know* principle.

Before assigning one of the following role collections, take extra considerations.


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Remarks

</th>
</tr>
<tr>
<td valign="top">

WorkspacePackagesEdit

PI\_Integration\_Developer

</td>
<td valign="top">

A user who is assigned one of these roles can create, modify, or delete integration content, for example, integration flows. This gives the user control over integration scenarios and, consequently, over the productive workflow of a part of a company's processes.

> ### Tip:  
> You can create access policies to restrict access to selected integration content artifacts and their data.
> 
> See:
> 
> -   [Managing Access Policies](../managing-access-policies-318d107.md)
> 
> -   [SAP Integration Suite – Access Policies for Integration Packages](https://community.sap.com/t5/technology-blogs-by-sap/sap-integration-suite-access-policies-for-integration-packages/ba-p/13648901) \(SAP Community blog\)



</td>
</tr>
<tr>
<td valign="top">

MessagePayloadsRead

DataStorePayloadsRead

</td>
<td valign="top">

A user assigned to one of these roles can access potentially sensitive information contained in messages processed by Cloud Integration.

> ### Tip:  
> You can create access policies to restrict access to selected integration content artifacts and their data.
> 
> See:
> 
> -   [Managing Access Policies](../managing-access-policies-318d107.md)
> 
> -   [SAP Integration Suite – Access Policies for Integration Packages](https://community.sap.com/t5/technology-blogs-by-sap/sap-integration-suite-access-policies-for-integration-packages/ba-p/13648901) \(SAP Community blog\)



</td>
</tr>
</table>

