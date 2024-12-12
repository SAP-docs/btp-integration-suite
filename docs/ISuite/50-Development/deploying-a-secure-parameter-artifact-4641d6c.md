<!-- loio4641d6c531d34cf7aef94ba5a873bf6e -->

# Deploying a Secure Parameter Artifact

Use the secure parameter artifact to deploy confidential data, for example, for custom adapters.



## Context

You can store secure data like passwords in a secure store and use an alias name to access this data in an integration flow. The secure parameter artifact contains this alias name and confidential data.



## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.

2.  Select the target runtime \(*Runtime* parameter\).

    This information is only relevant for Edge Integration Cell runtime.

    For more information on how to manage security artifacts for Edge Integration Cell, see [Manage Security for Edge Integration Cell](../manage-security-for-edge-integration-cell-1783cf8.md).

3.  Click the *Security Material* tile in the *Manage Security* section.

4.  Choose *Add*.

5.  As *Type*, select *Secure Parameter*.

6.  Specify the following attributes.


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Name**
    
    </td>
    <td valign="top">
    
    Provide a name for the artifact.

    The artifact name is used as an alias for the confidential data assigned by this parameter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Description**
    
    </td>
    <td valign="top">
    
    Provide a more detailed description of the artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Secure Parameter**
    
    </td>
    <td valign="top">
    
    Enter the confidential value of the attribute.

    > ### Note:  
    > The possible length of the secure parameter varies:
    > 
    > -   for **Cloud Foundry: 4096 characters max. \(including spaces\)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Repeat Secure Parameter**
    
    </td>
    <td valign="top">
    
    Repeat the confidential value of the attribute.
    
    </td>
    </tr>
    </table>
    
7.  Choose *Deploy*.




## Results

When you refresh the *Manage Security Material* page, the new artifact is displayed in the table.

**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

