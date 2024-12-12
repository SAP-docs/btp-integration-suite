<!-- loio5e051beb51b6494f92e8a52afad23c13 -->

# Creating Assets

Create an asset and add properties in Data Space Integration.



## Context

You want to define assets, which can later be shared with other members of the data space as defined by policies. This process, as described in this topic, is available via the UI.



## Procedure

1.  To create an asset, in SAP Integration Suite, go to *Design* \> *Data Spaces*.

2.  From the header bar, select *Assets*. You can see all the assets that have already been created.

3.  Choose *Create*.

4.  In the Create dialog, for *General Information*, add the following details, and then choose *Next Step*:


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
    
    Define a name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **ID**
    
    </td>
    <td valign="top">
    
    Define a unique ID \(A-Z, a-z, 0–9, periods, underscores, and hyphens\) for your asset. If you don't define an ID, one is generated for you.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Description**
    
    </td>
    <td valign="top">
    
    Enter a description that can help you later to more easily identify the content, purpose, owner, of that asset.
    
    </td>
    </tr>
    </table>
    
5.  \(Optional\) To create properties, choose *Add*, specify the following information, and then choose *Next Step*:


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
    
    Enter a unique property name \(A-Z, a-z, 0–9, periods, underscores, and hyphens\). Example: `unique_property_name`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Value**
    
    </td>
    <td valign="top">
    
    Enter a property value \(A-Z, a-z, 0–9, periods, underscores, and hyphens\). Example: `Property_Value_01` 
    
    </td>
    </tr>
    </table>
    
6.  Enter the data address by specifying the following information, and then choose *Next Step*:


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
    
    **Data Plane**
    
    </td>
    <td valign="top">
    
    Define the data plane.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Base URL**
    
    </td>
    <td valign="top">
    
    Enter the base URL. Example: `http://www.example.com`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **URL Path**
    
    </td>
    <td valign="top">
    
    Define the incoming path type either by selecting *Use Incoming Path* or by entering the incoming path manually.

    > ### Caution:  
    > Make sure to add `https` connections only. `http` is not supported for security reasons.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Query Parameters**
    
    </td>
    <td valign="top">
    
    Define the incoming query either by selecting *Use Incoming Query* or by entering the incoming query manually.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **HTTP Method**
    
    </td>
    <td valign="top">
    
    Select the HTTP method:

    -   *GET \(default\)*

    -   *Use incoming method*

    -   *PUT*

    -   *POST* 



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Content Type**
    
    </td>
    <td valign="top">
    
    Define incoming content type either by selecting *Use Incoming Content Type* or by entering the content type manually.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Authentication Type**
    
    </td>
    <td valign="top">
    
    Choose the authentication type *Basic*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **User**
    
    </td>
    <td valign="top">
    
    Enter a user name. Example: `username@example.com`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Password**
    
    </td>
    <td valign="top">
    
    Define a password.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **HTTP Headers**
    
    </td>
    <td valign="top">
    
    If you want to transfer specific HTTP headers with certain values to the back end when fetching the asset, specify them in this field.
    
    </td>
    </tr>
    </table>
    
7.  Review your information.

    > ### Note:  
    > You can make changes later by choosing *Edit*. Except for the unique *ID*, you can edit any field. See [Editing Assets](editing-assets-5f2d07d.md).

8.  Choose *Finish*. Your asset is now listed in the table view. See [Working with Assets](working-with-assets-fa84319.md).


