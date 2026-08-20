<!-- loio7436351aa24c4781b3f9680cab9c798f -->

# Generate a Personal Access Token \(PAT\) with Required Permissions

Understand the PAT permissions based on your role and the type of Git operation you wish to perform.



## Procedure

Follow these steps for generating a personal access token with required permissions:

1.  Log in to your GitHub account.
2.  Navigate to *Settings* \> *Developer Settings* \> *Personal Access Tokens* \> *Fine- Grained Tokens or Tokens \(Classic\)*.
3.  Choose *Generate New Token*.
4.  For fine- grained tokens, in the *Permissions* section, add the required permissions for your role.

**Access Permissions for Fine- Grained Tokens**


<table>
<tr>
<th valign="top">

**Role** 

</th>
<th valign="top">

**Git Operation** 

</th>
<th valign="top">

**Required Permission & Access** 

</th>
</tr>
<tr>
<td valign="top">

Tenant Administrator

</td>
<td valign="top">

Repository Access

</td>
<td valign="top">

Metadata \(Read-only\) - default

</td>
</tr>
<tr>
<td valign="top">

Integration Developer

</td>
<td valign="top">

Git Import and Pull

</td>
<td valign="top">

Contents \(Read-only\)

</td>
</tr>
<tr>
<td valign="top">

Integration Developer

</td>
<td valign="top">

Push

</td>
<td valign="top">

Contents \(Read and Write\)

</td>
</tr>
</table>

To learn more about the Git Permissions, see [Repository Permissions](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#repository-permissions).

> ### Remember:  
> It's mandatory to enter the Personal Access Token for each operation.



## Related Information

[Git Import](import-integration-flows-from-git-repository-223f83c.md)

[Git Push](git-push-97b5594.md)

[Git Pull](git-pull-5a8fdb9.md)

