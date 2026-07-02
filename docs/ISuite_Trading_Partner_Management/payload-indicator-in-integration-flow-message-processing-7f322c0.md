<!-- loio7f322c0480e84ce390a130c50a8a18cb -->

# Payload Indicator in Integration Flow Message Processing

Monitor the message processing of the integration flows.

The *Monitor* tab of the Cloud Integration tenant allows you to monitor the message processing of the integration flows. To know more, see [Monitoring](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/05446d0616d44e1daf821c273b69fcc6.html).

1.  Log on to SAP Integration Suite.
2.  Choose *Monitor* \> *Integrations*.
3.  Choose *All Integration Flows* tile under the *Monitor Message Processing* section.

4.  Select the integration flow for which you want to check the processing information and choose *Trace* link provided next to the *Log Level* field on the right side.
5.  In the resulting screen, select the step for which you want to check the message content. Choose *Send Receiver Interchange* to review the payload.
6.  Choose *Message Content* on the right side and select the *Payload* tab.
7.  This will display the payload of the agreement transaction. Depending on the purpose type configured in the company/trading partner profile, an indicator is set in the payload to display if the transaction is of type test, dev or prod.

    > ### Note:  
    > For those agreements that were activated before the introduction of this indicator feature, you need to reactivate your agreement again to get the indicator in the payload.
    > 
    > And if you have modified the System Purpose of an active agreement, you need to reactivate the agreement to see the corresponding indicator in the payload.

    The following table lists the receiver type system and the corresponding purpose indicator:

    To help you understand, if the agreement has a trading partner system with the ASC-X12 type system as the receiver system, and the configured purpose is "Test", then the indicator value in the converted ASC-X12 payload will be "T".

    **ASC X12**


    <table>
    <tr>
    <th valign="top">

    Purpose
    
    </th>
    <th valign="top">

    Indicator
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Production
    
    </td>
    <td valign="top">
    
    P
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Development
    
    </td>
    <td valign="top">
    
    I
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Test
    
    </td>
    <td valign="top">
    
    T
    
    </td>
    </tr>
    </table>
    
    **UN/EDIFACT**


    <table>
    <tr>
    <th valign="top">

    Purpose
    
    </th>
    <th valign="top">

    Indicator
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Production
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Development
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Test
    
    </td>
    <td valign="top">
    
    1
    
    </td>
    </tr>
    </table>
    
    **IDOC**


    <table>
    <tr>
    <th valign="top">

    Purpose
    
    </th>
    <th valign="top">

    Indicator
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Production
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Development
    
    </td>
    <td valign="top">
    
    X
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Test
    
    </td>
    <td valign="top">
    
    X
    
    </td>
    </tr>
    </table>
    

