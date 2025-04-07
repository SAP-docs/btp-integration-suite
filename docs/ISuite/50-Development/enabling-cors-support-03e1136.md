<!-- loio03e11361b5734b99ad4dea78ea1527fd -->

# Enabling CORS Support

CORS \(Cross-origin resource sharing\) allows JavaScript XMLHttpRequest \(XHR\) calls executed on a web page to interact with resources from a domain that is different from the domain serving the web page.



<a name="loio03e11361b5734b99ad4dea78ea1527fd__steps_kgl_x12_xyb"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the*<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

5.  The *Create API* dialog opens.

    Create an API artifact using one of the following methods:

    -   [Creating an API Artifact Using URL](creating-an-api-artifact-using-url-914f57e.md) 

    -   [Creating an API Using an Imported API Definition](creating-an-api-using-an-imported-api-definition-fb99a7d.md)

    -   [Creating an API Using API Specification](creating-an-api-using-api-specification-39c2b30.md)


6.  To enable the CORS supports for the API artifact, navigate to *Policies* tab on the details screen and choose *Edit*.

7.  Scroll down to the API properties section, choose *CORS*, and fill in the following details.


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
    
    Enable CORS
    
    </td>
    <td valign="top">
    
    Select the checkbox to enable the CORS settings at the API level.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Allow Origin
    
    </td>
    <td valign="top">
    
    List of origins from which resource can be accessed. For example, https://developer.mozilla.org
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Allow Headers
    
    </td>
    <td valign="top">
    
    Determines the Request-Headers to indicate which HTTP headers can be used during the actual request. This is used in response to a preflight request. For example, X-Custom-Header.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Expose Headers
    
    </td>
    <td valign="top">
    
    Headers that allows the server to indicate which response headers should be made available to scripts running in the browser, in response to a cross-origin request. For example, Content-Type, Last-Modified, etc.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Allow Methods
    
    </td>
    <td valign="top">
    
    Methods allowed when accessing a resource in response to a preflight request. For example, GET, POST, PUT, etc.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Access Control Max Age \(in sec\)
    
    </td>
    <td valign="top">
    
    The time taken for the results of a pre-flight request \(that is, the information contained in the Allow-Methods and Allow-Headers\) to be cached. For example, enter 600 if the cache results of a preflight request are 10 minutes.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Access Control Allow Credentials
    
    </td>
    <td valign="top">
    
    The Access-Control-Allow-Credentials response header tells the browsers whether to expose the response to the front-end JavaScript code when the request's credentials mode \(Request.credentials\) is included. Select the check box to set the "Allow Credentials" value to true.
    
    </td>
    </tr>
    </table>
    
8.  Once you’ve added and configured all the required policy steps for the API, you can select one of the following actions for the API:


    <table>
    <tr>
    <th valign="top">

    Action
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Save* 
    
    </td>
    <td valign="top">
    
    Saves the artifact as *Draft* version.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Save as version* 
    
    </td>
    <td valign="top">
    
    Creates a new version of the artifact.

    Specify the version in the *Version Information* dialog. In the *Comment* section, you can add additional information specific to the artifact for later reference. This helps you determine the purpose of each version.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Deploy* 
    
    </td>
    <td valign="top">
    
    Deploys the API artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Delete* 
    
    </td>
    <td valign="top">
    
    Deletes the API artifact from the package.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Cancel* 
    
    </td>
    <td valign="top">
    
    Ends your edit session without saving any of the changes you have made.
    
    </td>
    </tr>
    </table>
    

