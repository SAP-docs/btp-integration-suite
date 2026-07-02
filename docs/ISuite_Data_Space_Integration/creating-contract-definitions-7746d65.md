<!-- loio7746d65034844c57b6245c55ce65bef8 -->

# Creating Contract Definitions

Learn how to create a contract definition.



<a name="loio7746d65034844c57b6245c55ce65bef8__prereq_p1n_n3m_2yb"/>

## Prerequisites

-   You've created at least one asset. See [Creating Assets](creating-assets-5e051be.md).

-   You've created at least two policies. See [Creating Policies](creating-policies-91458cf.md).




<a name="loio7746d65034844c57b6245c55ce65bef8__context_mqt_53m_2yb"/>

## Context

You want to create a contract definition. Contract definitions consist of assets and policies.



<a name="loio7746d65034844c57b6245c55ce65bef8__steps_l3l_v3m_2yb"/>

## Procedure

1.  In SAP Integration Suite, go to *Design* \> *Data Spaces*.

2.  From the header bar, select *Contract Definitions*.

3.  If this is your first visit, you won't see any contract definitions. Choose *Create*.

4.  In the *General* section, enter a *Name* and *Description* \(optional\) and choose *Next Step*.

5.  In the *Select Policy* section, select an *Access Policy* defining who can interact with your assets, and a *Usage Policy* defining how they can interact with your assets. Since you can't select the same policy as both access and usage policy, you must have created at least two policies. See [Working with Policies](working-with-policies-c930aed.md).

    > ### Caution:  
    > Be aware that **consumers can see all details of a usage policy**. Wrong configuration of a usage policy can lead to consumers being able to gain insights into your business. For example, the business partner number constraint in a policy can point out what business partners you're working with. As a provider, pay attention to your policy usage.

6.  Confirm your selection by choosing *Next Step*.

7.  In the *Select Assets* section, select all of the assets that you want to include in the contract definition. See [Working with Assets](working-with-assets-fa84319.md).

8.  Confirm your selection by choosing *Next Step*.

9.  Review your information.

    You can edit contract definitions as long as they are not in use. See [Editing Contract Definitions](editing-contract-definitions-38d141b.md).

10. Finish the process by choosing *Finish*. Your new contract definition appears in the overview list. See [Working with Contract Definitions](working-with-contract-definitions-f136d72.md).


