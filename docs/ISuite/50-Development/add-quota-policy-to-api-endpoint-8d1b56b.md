<!-- loio8d1b56b225f444e7ae98c0e13a6339b6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add Quota Policy to API Endpoint

Adding quota policy to an API artifact for traffic management.



<a name="loio8d1b56b225f444e7ae98c0e13a6339b6__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Enable Cloud Integration and API Management capabilities.

-   Provision Edge Integration Cell runtime.




## Context

Define the number of request messages an application can submit to an API endpoint over a given period of time by adding a quota policy to the API artifact.



<a name="loio8d1b56b225f444e7ae98c0e13a6339b6__steps_jm4_15c_31c"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the*<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *API*.

5.  The *Create API* dialog opens.

    Create an API artifact using one of the following methods:

    -   [Create an API Artifact Using a Target URL](create-an-api-artifact-using-a-target-url-914f57e.md) 

    -   [Create an API Artifact by Importing an OpenAPI Specification](create-an-api-artifact-by-importing-an-openapi-specification-fb99a7d.md)

    -   [Create an API Artifact Using an API Specification](create-an-api-artifact-using-an-api-specification-39c2b30.md)


6.  To add a policy to the API artifact, navigate to the *Policies* tab on the details screen.

    image

    Use *Policy Model* to add a policy to the API artifact.

    > ### Note:  
    > Policies are allowed only on request flow and not on response flow.

    > ### Note:  
    > Authentication policy is a mandatory policy and is added to request flow by default. Neither you can remove this step, nor you can add another authentication policy to the flow. It is the first step in the request flow and cannot be altered in sequence. Changing the sequence of this policy would result in an error during the save or deploy process. The purpose of the Authentication policy is to verify the identity of the caller against the configured Identity Provider \(IDP\), ensuring that only valid identities are granted access.
    > 
    > The position of the authentication policy on the flow is immutable and it is the first policy on the flow.

    > ### Remember:  
    > -   All other policies can be added to the flow multiple times except authentication policy.
    > 
    > -   Only policies can be added between two policies. You can't add integration steps between two policies.
    > 
    > -   Policies must precede integration steps.

7.  Double-click on the *Authentication* policy to edit its properties. By default, only *Client Certificate* and *OAuth* are selected. Let us select the *Basic* option as well.

    image

8.  Now add the quota policy. To add the policy, click on the request flow and choose :heavy_plus_sign: .

    image

9.  Select *Quota* under *Traffic Management* from the *Add Flow Step* dialog.

    image

    Alternatively, select the <span class="BusinessSuiteInAppSymbols-V2"></span> Traffic Management policies icon from the palette and choose *Quota*

10. Double-click on the *Quota* policy, and fill in all the necessary details under the *General* and the *Policy Settings* tab.

    The quota policy provides multiple modes to work with, you can leverage them based on your need.

    **Policy Settings**


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name\*
    
    </td>
    <td valign="top">
    
    The unique name of the policy within the API artifact. Each policy in an API artifact must have a unique name to prevent naming conflicts.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    On Error
    
    </td>
    <td valign="top">
    
    Determines the behavior when an exception or an error occurs during the policy execution.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Mode
    
    </td>
    <td valign="top">
    
    Select the type of the policy that you want to configure. For example, if you want to explicitly provide a start time, select Calendar. For more information, see [Modes of the Quota Policy](modes-of-the-quota-policy-61b36a1.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Start Time \(UTC\)\*
    
    </td>
    <td valign="top">
    
    Determines the start of the quota window. This property can only be specified if the mode is set to *Calendar* or *Fixed*.

    Enter the date and time when the quota counter begins counting.

    Timestamp format in UTC format: 2015-02-09 00:00:00.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Calls\*
    
    </td>
    <td valign="top">
    
    Specify the number of calls that a client can make to an API endpoint over a duration. For example, 1000 calls over a duration of 1 hour.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Duration\*
    
    </td>
    <td valign="top">
    
    Determines the period for which the quota is allotted to the client.

    Data type: positive integer. For example, 5, 10, ..., 60, etc. that is coupled with the unit \(second, minute, hour, day, week, or month\) in the next field.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Duration Unit
    
    </td>
    <td valign="top">
    
    Represents the unit of time used along with interval.

    Supported units are second, minute, hour, day, week, or month.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Quota Identifier\*
    
    </td>
    <td valign="top">
    
    Represents a unique identifier for the client or the application against which the quota is allotted. For example, you can define that the *Quota Identifier\** is determined dynamically by reading a value from a request header such as $\{request.header.appId\}. Refer to the table for the supported expressions for the quota identifier.
    
    </td>
    </tr>
    </table>
    
    **Supported Expressions for Requestor Key**


    <table>
    <tr>
    <th valign="top">

    Expressions for Requestor Key
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    $\{request.header.<headerName\>\}
    
    </td>
    <td valign="top">
    
    This expression represents a header in the incoming request message where the name of the header is denoted by <headerName\>. For example, you can use the clientID, and username as the <headerName\>.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    $\{request.query.<queryParamName\>\}
    
    </td>
    <td valign="top">
    
    This expression represents a query parameter in the incoming request message where the name of the query parameter is denoted by <queryParamName\>. For example, you can use the clientID, or username as the <queryParamName\>.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > If you are using special characters in <headerName\> or <queryParamName\>, please ensure that you use bracket notation. For example, $\{request.header\['X-Forwarded-For'\]\}

    > ### Note:  
    > When the quota limit specified in the policy is reached, the subsequent requests to the API artifact are rejected with the response code 429 \(request limit exceeded\). The rejection period lasts until the end of the quota window. Let's illustrate this with the following example:
    > 
    > The quota window opens at 00:00 \(12 AM\) and ends at 00:05 \(12:05 AM\). Let us assume that the quota allotted is three requests in the specified period of 5 minutes. At 00:03, if the quota limit is reached, the subsequent requests post 00:03 are rejected until the window is reset at 00:05.

11. Once you’ve added and configured all the required policies for the API, you can select one of the following actions for the API:


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
    
    Deployes the API artifact.
    
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
    

**Related Information**  


[Modes of the Quota Policy](modes-of-the-quota-policy-61b36a1.md "Quota type is an attribute of the Quota policy that you define while configuring the policy.")

