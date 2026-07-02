<!-- loio91458cfbeba44478bce2e5aaec7b5801 -->

# Creating Policies

Create a policy in Data Space Integration.



<a name="loio91458cfbeba44478bce2e5aaec7b5801__context_whl_lbf_2yb"/>

## Context

You want to define policies that regulate how other members of the data space can use your assets.

In a contract definition, policies can function either as **access policy** or **usage policy**, which means they either define who can use an asset \(access\) or for how long and in what manner \(usage\). You must have defined at least two policies to use them in a contract definition: one to be used as access policy, and one as usage policy.



<a name="loio91458cfbeba44478bce2e5aaec7b5801__steps_vzx_3bf_2yb"/>

## Procedure

1.  Go to *Design* \> *Data Spaces* \> *Policies* and choose *Create*.

2.  In the *Overview* section, enter a *Name* and *Description* \(optional\).

3.  In the *Rules* section, choose *Add* to create a new rule. Rules define the policy.

    -   If you want to create a policy that you want to use as an **access policy**, add the following parameters:

        ****


        <table>
        <tr>
        <th valign="top">

        Parameter
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Attribute*
        
        </td>
        <td valign="top">
        
        Select one of the following attributes to define your rule:

        -   *Membership*
        -   *Business Partner Number*
        -   *Business Partner Group*

        > ### Caution:  
        > Selecting any other attributes in an access policy can lead to consumers not being able to see your offers.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Operator*
        
        </td>
        <td valign="top">
        
        Define an operator that specifies the relationship between attribute and value.

        Select one of the following operators:

        -   *is*: Include a specific value \(applicable for all attributes\)

            If you choose this option, your value cannot be a list. Choose this option to create a 1:1 relationship between *Attribute* and *Value*.

            > ### Example:  
            > `Business Partner Number is BPN0000123`

        -   *is any of*: Include one or more values of a list \(applicable for *Business Partner Number* and *Business Partner Group*\)


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Value*
        
        </td>
        <td valign="top">
        
        Define the value that your attribute should correspond to.

        For some attributes, the value is already entered and cannot be changed. For example, the value for *Membership* is always `active`.
        
        </td>
        </tr>
        </table>
        
    -   If you want to create a policy that you want to use as a **usage policy**, add the following parameters:

        ****


        <table>
        <tr>
        <th valign="top">

        Parameter
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Attribute*
        
        </td>
        <td valign="top">
        
        Select one of the following attributes to define your rule:

        -   *Membership*
        -   *Framework Agreement*
        -   *Usage Purpose*
        -   *Contract Reference*

        > ### Caution:  
        > Don't use *Business Partner Number* and *Business Partner Group* in a policy you want to use as a **usage policy**.
        > 
        > Since consumers can see all details of a usage policy, wrong configuration of a usage policy can lead to consumers being able to gain insights into your business. For example, the business partner number constraint in a policy can point out what business partners you're working with.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Operator*
        
        </td>
        <td valign="top">
        
        Define an operator that specifies the relationship between attribute and value.

        Select one of the following operators:

        -   *is*: Include a specific value \(applicable for all attributes\)

            If you choose this option, your value cannot be a list. Choose this option to create a 1:1 relationship between *Attribute* and *Value*.

            > ### Example:  
            > `Business Partner Number is BPN0000123`

        -   *is all of*: Include all values of a list \(applicable for *Usage Purpose* and *Contract Reference*\)


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Value*
        
        </td>
        <td valign="top">
        
        Define the value that your attribute should correspond to.

        For some attributes, the value is already entered and cannot be changed. For example, the value for *Membership* is always `active`.
        
        </td>
        </tr>
        </table>
        

    Add as many rules as you need to define your policy.

4.  *Save* your changes. Your new policy appears in the list of policies.




<a name="loio91458cfbeba44478bce2e5aaec7b5801__postreq_h51_nd1_42c"/>

## Next Steps

Now that you've created policies, you can assign them to a contract definition to define the conditions under which business partners can use one of your assets. See [Working with Contract Definitions](working-with-contract-definitions-f136d72.md).

