<!-- loio23d824a89dd44c8bbb51d1d838fc7a75 -->

# Deploying a Secure Parameter Artifact

Use the secure parameter artifact to deploy confidential data for custom adapters.



## Prerequisites

In the Node Explorer you have selected a tenant, in the context menu you have selected *Deploy Artifacts*, and you have specified *Secure Parameter* as the artifact type.



## Context

You can store secure data like passwords in a secure store and use an alias name to access this data in an integration flow. The secure parameter artifact contains this alias name and confidential data.

You can deploy the artifact on the tenant by following the procedure below.



<a name="loio23d824a89dd44c8bbb51d1d838fc7a75__steps_w4b_4wn_np"/>

## Procedure

1.  Specify the attributes on the wizard page.


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
    
2.  Choose *Finish*.

    > ### Note:  
    > If correct alias is configured in the integration flow, then the runtime framework passes the secured artifact value to the component at runtime from the secure store.


