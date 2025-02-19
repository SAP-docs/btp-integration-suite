<!-- loio7b65115a941143bf85e011f909b713a7 -->

# Configure in Data Spaces

Learn how to work with company policies and contract references in Data Space Integration.



<a name="loio7b65115a941143bf85e011f909b713a7__section_ih3_z3g_qcc"/>

## About Company Policies

A **company policy** is a set of rules that defines the regulations for requesting and accepting an offer. As an admin, you create a set of allowed constraints that business partners might have used in their usage policy to offer their assets in the data space. This way, you can control which offers can be accepted by the users in your organization.

If a provider creates an offer that violates the rules set in the company policy, the offer is not shown to the users requesting the catalog. Note that the user must be assigned to the company policy with their client ID for the policy to apply.

Possible attributes for rules include business partner number, membership, framework agreement, usage purpose, and contract reference. For example, you can exclude offers with references to unknown contracts or usage purposes.

For more information and an example illustrating the behavior of company policies, see [Create and Edit Company Policies](create-and-edit-company-policies-51fa547.md).

SAP predelivers company policies, but you can also create your own company policies, specific to your use case.



### Authorizations

To work with company policies, you require the following roles in your SAP BTP subaccount:

-   To **create, edit, or copy a company policy**, you require the role collection `DataspaceBusinessAdmin`.

-   To **assign a company policy**, you need the role collection `DataspaceTechnicalAdmin`.


See also [Personas and Roles](../60-Security/identity-and-access-management-for-data-space-integration-211c66a.md#loio211c66a2f65e4bf0ad0e93e68cfff984__section_cxz_vsk_pcc).



<a name="loio7b65115a941143bf85e011f909b713a7__section_hht_1jg_qcc"/>

## About Contract References

With contract references, you can keep a manual list of the contracts that exist for your company, with the respective business partners and potential use cases.

After defining contract references, you can use them to define both policies and company policies and restrict who can work with you.



### Authorizations

To work with contract references, you require the role collection `DataspaceBusinessAdmin`.

**Related Information**  


[Create and Edit Company Policies](create-and-edit-company-policies-51fa547.md "Learn how to create, edit, copy, and delete company policies in Data Space Integration.")

[Assign Company Policies](assign-company-policies-b4c9e0b.md "Learn how to assign company policies in Data Space Integration.")

[Identity and Access Management for Data Space Integration](../60-Security/identity-and-access-management-for-data-space-integration-211c66a.md "Learn about the personas and roles in Data Space Integration, as well as their typical tasks and permissions.")

[Create Contract References](create-contract-references-1b73cdc.md "Maintain contract references to keep an overview of the contracts you have with other business partners in a data space.")

