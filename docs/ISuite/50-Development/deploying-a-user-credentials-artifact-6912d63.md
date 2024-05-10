<!-- loio6912d63bbbc64aee8bbd4ff10314c60c -->

# Deploying a User Credentials Artifact

To set up a connection using basic authentication or username token authentication, you have to specify the required attributes \(for example, user name and password\).



## Context

*User Credentials* \(security artifact\) on the corresponding tenant. You can specify basic authentication either for a connected SuccessFactors system \(through the SuccessFactors adapter\) or for general SOAP connectivity or an OpenConnectors service \(through the OpenConnector adapter\). To enable basic authentication for a runtime node, you specify the user credentials and deploy the attributes.

> ### Note:  
> You can also edit and redeploy an existing artifact. To do that, select the artifact in the table under *Manage Security Material* and choose *Edit*.



## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.

2.  Select the target runtime \(*Runtime* parameter\).

    This information is only relevant for Edge Integration Cell runtime.

    For more information on how to manage security artifacts for Edge Integration Cell, see [Manage Security for Edge Integration Cell](../manage-security-for-edge-integration-cell-1783cf8.md).

3.  Select the *Security Material* tile in the *Manage Security* section.

4.  Choose *Add*.

5.  As *Type*, select *User Credentials*.

6.  Specify the following properties:


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
    
    Name
    
    </td>
    <td valign="top">
    
    A name for the artifact.

    The artifact name is used as an alias for the confidential data assigned by this parameter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    A description of the artifact \(optional\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    This allows you to configure a specific system to enable a connection with your integration flow artifact.

    If you select:

    -   *SuccessFactors*: Specify the *Company ID* \(which indicates the client instance used to connect to the SuccessFactors system\).

    -   *OpenConnectors*: Specify the *Organization* and *Element* \(value obtained from the authorization header that helps to authenticate with the specific instance\).

        See: [OpenConnectors Receiver Adapter](openconnectors-receiver-adapter-1a27cee.md)



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User
    
    </td>
    <td valign="top">
    
    The user that calls the receiver system.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password
    
    </td>
    <td valign="top">
    
    Password against which the user has to be authenticated.

    This parameter has a maximum length of 255 characters.
    
    </td>
    </tr>
    </table>
    
7.  Choose *Deploy*.




## Results

When you refresh the *Manage Security Material* page, the new artifact is displayed \(with Type *Credentials*\) in the artifact table.



<a name="loio6912d63bbbc64aee8bbd4ff10314c60c__postreq_vyg_tj5_hz"/>

## Next Steps

> ### Note:  
> When you have a User Credentials artifact, you also have to re-deploy and restart all integration flows that use this artifact.

**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

