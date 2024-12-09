<!-- loio86267270df794aed8329cf9d3a0c3481 -->

# Resend/Retry Interchanges

Resend or retry the failed interchanges



<a name="loio86267270df794aed8329cf9d3a0c3481__prereq_tdz_kpy_3dc"/>

## Prerequisites

You need to configure a destination to store the connection information about the reprocess integration flow.

1.  Login to SAP BTP cockpit and navigate to your subaccount.

2.  Choose *Connectivity* \> *Destinations* from the left pane.
3.  Choose *Create Destination* and provide the following information.


    <table>
    <tr>
    <th valign="top">

    Field
    
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
    
    Enter the value as `B2BTPM_Reprocess_Endpoint`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    HTTP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    You can provide a description for your reference. This field is optional.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    Provide the endpoint URL of the generic reprocess integration flow.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Internet
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    BasicAuthentication
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User
    
    </td>
    <td valign="top">
    
    Enter the user ID that is authorized to send integration flow messages
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password
    
    </td>
    <td valign="top">
    
    Enter the password/client secret of the user
    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.



<a name="loio86267270df794aed8329cf9d3a0c3481__context_vx4_wg4_hdc"/>

## Context

The B2B Monitor has a manual restart/retry function exclusively designed for failed interchanges, allowing you to re-process failed messages.

> ### Note:  
> This feature is available in generic integration flow version 2.3.7 and subsequent releases.

The *Actions* button is enabled when you select the interchanges and it consists of two options: *Resend* and *Retry*. These options appear only for interchanges with the status *Failed*.

The restart and retry options serve distinct purposes in handling failed interchanges. The primary difference between the two lies in their approach to re-processing:

**Restart**: This option resets the sender payload to integration flow *Step 1b - Write Message to Message queue*, thereby re-initiating the messaging process from the beginning. As a result, the message mapping is re-executed, making room for corrections or adjustments to be made. Restart is ideal for addressing errors related to message transformation or formatting.

**Retry**: Retry resets the receiver payload to *Step 3 - Receiver Communication Flow V2*, bypassing the message mapping step. This option is suited for resolving errors related to receiver-side processing or temporary connectivity issues, where the original message mapping remains valid.

When restarting or retrying, the original interchange ID remains unchanged, and new events are appended to the existing interchange event log. To restart or retry a failed interchange, follow the procedure below:



<a name="loio86267270df794aed8329cf9d3a0c3481__steps_hxh_xj4_hdc"/>

## Procedure

1.  Select the specific failed interchange\(s\) you want to retry or restart from the list.

2.  Choose *Actions* \> *Restart* or *Actions* \> *Retry*.

3.  In the *Confirm Restart* or *Confirm Retry* dialog, provide a reason for the action and choose *Confirm*.

    > ### Note:  
    > This action cannot be reversed and may take a while to complete.


