<!-- loio51fa547512ff4be9b19fcc468c32bbd6 -->

# Create and Edit Company Policies

Learn how to create, edit, copy, and delete company policies in Data Space Integration.



<a name="loio51fa547512ff4be9b19fcc468c32bbd6__prereq_xg2_rds_pcc"/>

## Prerequisites

You require the role collection `DataspaceBusinessAdmin`. See [Personas and Roles](../60-Security/identity-and-access-management-for-data-space-integration-211c66a.md#loio211c66a2f65e4bf0ad0e93e68cfff984__section_cxz_vsk_pcc).



<a name="loio51fa547512ff4be9b19fcc468c32bbd6__context_zdl_qds_pcc"/>

## Context

Use company policies to define the regulations for requesting and accepting an offer. For example, you can exclude offers with references to unknown contracts or usage purposes.

Some company policies are **predelivered by SAP**, as signified in the *Created By* column. You cannot edit or delete company policies created by SAP, but you can copy them and edit the copy. Users with the role collection `DataspaceTechnicalAdmin` can also assign company policies created by SAP.



<a name="loio51fa547512ff4be9b19fcc468c32bbd6__steps-unordered_khm_mds_pcc"/>

## Procedure

-   **Create a Company Policy**

    1.  In *Configure* \> *Data Spaces*, choose *Create*.

    2.  Enter a name and description.
    3.  Add rules to define your company policy. All rules you want to apply to one offer must belong to one company policy. You cannot split the constraints of an offer over multiple company policies.

        For more information, see the **example** section at the bottom of this page.

        For some attributes, the value is predefined, while others are free text. The following table lists the attributes that you can use to define your rules:


        <table>
        <tr>
        <th valign="top">

        Attribute
        
        </th>
        <th valign="top">

        Operators
        
        </th>
        <th valign="top">

        Value
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Business Partner Number*
        
        </td>
        <td valign="top">
        
        `is`, `is any of`
        
        </td>
        <td valign="top">
        
        Enter one \(`is`\) or multiple \(`is any of`\) business partner numbers.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Membership*
        
        </td>
        <td valign="top">
        
        `is`
        
        </td>
        <td valign="top">
        
        `active`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Framework Agreement*
        
        </td>
        <td valign="top">
        
        `is`
        
        </td>
        <td valign="top">
        
        `DataExchangeGovernance:1.0`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Usage Purpose*
        
        </td>
        <td valign="top">
        
        `is`, `is all of`
        
        </td>
        <td valign="top">
        
        Enter or select one \(`is`\) or multiple \(`is all of`\) usage purposes.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Contract Reference*
        
        </td>
        <td valign="top">
        
        `is`, `is all of`, `exists`
        
        </td>
        <td valign="top">
        
        Enter one \(`is`\) or multiple \(`is all of`\) contract references. If you're using the operator `exists`, the value is left empty to show that a contract reference must be present, no matter which.
        
        </td>
        </tr>
        </table>
        
    4.  Some rules are more important than others. If a rule must absolutely appear in the usage policy of the provider, enable the switch in the column *Required*. If a required rule is not fulfilled by the provider offer, that is, the rule isn't defined in their usage policy, you cannot accept their offer. For example, if you set a rule with a specific usage purpose to *required*, the company policy restricts you to only accept offers with that usage purpose in their usage policy.

        All other rules are considered **optional**: Optional rules are a collection of constraints that may appear in an offer, but don't have to. This means that if they don't appear in the offer, then the offer can still be consumed, provided that the remaining offer usage policy constraints are listed in the company policy. If the offer contains anything that is not listed as a company policy rule, the offer is not consumable.

    5.  Optionally, if you also have the role collection `DataspaceTechnicalAdmin`, you can also add assignees. See also [Assign Company Policies](assign-company-policies-b4c9e0b.md).

        A user can be assigned to multiple company policies, but not all of them have to allow a specific offer: it's sufficient if only one of them does so.

    6.  Choose *Create*.

        A technical administrator can now assign the company policy to clients.


-   **Edit a Company Policy**

    1.  In *Configure* \> *Data Spaces*, choose the company policy you want to edit.

        You can't edit company policies created by SAP, but you can create a copy and edit that copy.

    2.  Choose **Edit**.

    3.  You can modify the name and description of the company policy, as well as the rules. For details on the rules, see the instructions on creating a company policy.

    4.  Save your changes.


-   **Delete a Company Policy**

    Select the relevant company policy and choose *Delete*.

-   **Copy a Company Policy**

    1.  In *Configure* \> *Data Spaces*, choose the company policy you want to copy.

    2.  Choose *Copy*.

    3.  Enter a new name and description.

        Choose *Save* to create the copy and stay in the original, or *Save & Edit* to directly open the copy in edit mode.





## Example

This example illustrates the behavior of company policies in a simplified way.

The following **company policy** is assigned to every user who works at company A:

**Company Policy \(Company A\)**


<table>
<tr>
<th valign="top">

**Attribute**

</th>
<th valign="top">

**Operator**

</th>
<th valign="top">

**Value**

</th>
<th valign="top">

**Required**

</th>
</tr>
<tr>
<td valign="top">

Framework Agreement

</td>
<td valign="top">

is

</td>
<td valign="top">

DataExchangeGovernance:1.0

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Contract Reference

</td>
<td valign="top">

is

</td>
<td valign="top">

contract123

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Contract Reference

</td>
<td valign="top">

is

</td>
<td valign="top">

contract456

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Usage Purpose

</td>
<td valign="top">

is

</td>
<td valign="top">

cx.base.pcf:1

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Usage Purpose

</td>
<td valign="top">

is

</td>
<td valign="top">

cx.notifications.push:1

</td>
<td valign="top">

No

</td>
</tr>
</table>

This company policy defines the following rules for an acceptable offer:

-   it **must** contain the framework agreement `DataExchangeGovernance:1.0`
-   it **can** contain the contract references `contract123` or `contract456`, and the usage purposes `cx.base.pcf:1` or `cx.notifications.push:1`
-   it **must not** contain anything else that is not listed in the company policy

There are three **offers** available, one by company B, company C, and company D each.

The offer made by company B comes with the following rules, as defined in their own policies:

**Offer \(Company B\)**


<table>
<tr>
<th valign="top">

**Attribute**

</th>
<th valign="top">

**Operator**

</th>
<th valign="top">

**Value**

</th>
</tr>
<tr>
<td valign="top">

Framework Agreement

</td>
<td valign="top">

is

</td>
<td valign="top">

`DataExchangeGovernance:1.0`

</td>
</tr>
<tr>
<td valign="top">

Contract Reference

</td>
<td valign="top">

is

</td>
<td valign="top">

`contract123`

</td>
</tr>
<tr>
<td valign="top">

Usage Purpose

</td>
<td valign="top">

is

</td>
<td valign="top">

`hacker.evil`

</td>
</tr>
</table>

Company C has an offer that comes with the following rules, as defined in their own policies:

**Offer \(Company C\)**


<table>
<tr>
<th valign="top">

**Attribute**

</th>
<th valign="top">

**Operator**

</th>
<th valign="top">

**Value**

</th>
</tr>
<tr>
<td valign="top">

Contract Reference

</td>
<td valign="top">

is

</td>
<td valign="top">

`contract456`

</td>
</tr>
<tr>
<td valign="top">

Usage Purpose

</td>
<td valign="top">

is

</td>
<td valign="top">

`cx.base.pcf:1`

</td>
</tr>
</table>

Finally, company D's offer comes with the following rules, as defined in their own policies:

**Offer \(Company D\)**


<table>
<tr>
<th valign="top">

**Attribute**

</th>
<th valign="top">

**Operator**

</th>
<th valign="top">

**Value**

</th>
</tr>
<tr>
<td valign="top">

Framework Agreement

</td>
<td valign="top">

is

</td>
<td valign="top">

`DataExchangeGovernance:1.0`

</td>
</tr>
<tr>
<td valign="top">

Contract Reference

</td>
<td valign="top">

is

</td>
<td valign="top">

`contract456`

</td>
</tr>
<tr>
<td valign="top">

Usage Purpose

</td>
<td valign="top">

is

</td>
<td valign="top">

`cx.base.pcf:1`

</td>
</tr>
</table>

If you check the offer rules of companies B, C, and D against the company policy of company A, you notice the following:

-   **Company B**'s offer fulfills the required rule, but it contains a usage purpose, **hacker.evil**, that is not contained in company A's usage policy.

    This means that the offer by company B **cannot be accepted** by company A.

-   **Company C**'s offer looks good at first glance since its contract reference and usage purpose are both contained in company C's usage policy. However, it does not fulfill the **required rule**.

    This means that the offer by company C **cannot be accepted** by company A.

-   **Company D**'s offer fulfills the required rule , and its contract reference and usage purpose are both contained in company C's usage policy.

    This means that the offer by company D **can be accepted** by company A.


