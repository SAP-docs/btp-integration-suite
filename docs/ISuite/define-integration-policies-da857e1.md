<!-- loioda857e1df2b7464983ec7e16398fd0c4 -->

# Define Integration Policies

Rule that describes how to use an integration technology in a dedicated context.

You can use SAP standard integration technologies \(for example, SAP Integration Suite, Cloud Integration\), or you can adjust the configuration to use your own integration technologies.

By defining the individual attributes through the definitions of policies, a ranking between technologies is established. According to a given style and domain, the polices are ranked according to their recommendation degrees.

Based on the recommendations provided by the policies for the usage in certain domains, styles and with certain applications, the technology that is ranked first is selected.

> ### Example:  
> A policy with a recommendation degree of *General Recommendation* for a specific application, which is used in that scenario, is ranked higher than a policy with the same attributes without an application. A policy with recommendation *Reasonable Alternative* is ranked lower than a policy with *General Recommendation*.



<a name="loioda857e1df2b7464983ec7e16398fd0c4__section_uff_2ts_vvb"/>

## Creating Integration Policy

1.  Go to *Configure* \> *Integration Policies*. In the Integration Technology tab, you will be able to see the list of existing integration technologies. You can either choose from the existing SAP standard content or create and customise your own integration policy.

2.  Choose \(*Create*\) to add a new integration policy.

3.  Under *Create Integration Policy*, specify the following attributes:

    ****


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Style
    
    </td>
    <td valign="top">
    
    Specify the basic integration category or type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Domain
    
    </td>
    <td valign="top">
    
    Specify the area in a hybrid landscape where integration is needed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Recommendation Degree
    
    </td>
    <td valign="top">
    
    Specify the degree of recommendation.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Rule
    
    </td>
    <td valign="top">
    
    Specify a description of the scenario of the usage of the technology.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Applications
    
    </td>
    <td valign="top">
    
    Specify the list of supported applications.
    
    </td>
    </tr>
    </table>
    
4.  Select *Create*.

> ### Note:  
> You can see the order of technology preference when selecting *Select Technology*. It shows you the selected technologies in order of their corresponding integration policies. For more information on technology selection, refer to [Decide on an Integration Technology](decide-on-an-integration-technology-fb4bc24.md).

