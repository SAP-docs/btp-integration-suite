<!-- loio0629b58d4a764a0b8bcf9aa884503e78 -->

# Configure the Ariba Sender Adapter

The Ariba sender adapter connects SAP Integration Suite to the Ariba Network. Using this adapter, SAP and non-SAP cloud applications can receive business-specific documents in commerce eXtensible Markup Language \(cXML\) format from the Ariba network. The sender adapter allows you to define a schedule for polling data from Ariba.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a sender channel and selected the Ariba sender adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the *General* tab and provide values in the fields as follows.

**General**


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

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Processing**


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

*Ariba Network ID* 

</td>
<td valign="top">

Enter the ID associated with the Ariba Network. The default value is set to AN01000000001.

</td>
</tr>
<tr>
<td valign="top">

*cXML version* 

</td>
<td valign="top">

Default value provided by SAP is 1.2.025. If you are entering the version, it must be above 1.2.018.

</td>
</tr>
<tr>
<td valign="top">

*User Agent* 

</td>
<td valign="top">

Enter the user agent details. The convention is a textual string representing the client system conducting the cXML conversation. It must consist of the software company name and the product name.

</td>
</tr>
<tr>
<td valign="top">

*Language* 

</td>
<td valign="top">

Language used for constructing the cXML conversation. The only language supported is EN.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


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

*Ariba Network URL*

</td>
<td valign="top">

Specify the URL to which the cXML requests are posted, or from where the cXMLs are polled.

</td>
</tr>
<tr>
<td valign="top">

*Connection Mode*

</td>
<td valign="top">

Select one of the options based on the description given next:

-   *Production*: If you select this option, the Ariba Network processes the messages. This connection mode is set as the default deployment mode.

-   *Test*: If you select this option, the Ariba Network will not process the messages, and treats the messages as test data.




</td>
</tr>
<tr>
<td valign="top">

*Account Type*

</td>
<td valign="top">

Select one of the options based on the description given next:

-   *Buyer*: Select this option, if you hold a buyer account on the Ariba Network.

-   *Supplier*: Select this option, if you hold a supplier account on the Ariba Network.




</td>
</tr>
<tr>
<td valign="top">

*Request Type*

</td>
<td valign="top">

Select one of the options based on the request types of buyer/supplier that you want to poll.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Messages*

</td>
<td valign="top">

Enter the number of messages to be polled from the Ariba Network for the above-selected *Request Type*. The maximum allowed value is 200.

</td>
</tr>
<tr>
<td valign="top">

*System ID*

</td>
<td valign="top">

Provide the *System ID* for receiving the requests from a specific ERP system belonging to a supplier. If the system ID is not provided, then the adapter fetches all requests from every ERP systems belonging to that specific supplier.

> ### Note:  
> If the buyers’ account is enabled with multi-ERP. It is mandatory to provide the system ID for multi-ERP systems belonging to the buyer.



</td>
</tr>
<tr>
<td valign="top">

*Authentication Domain*

</td>
<td valign="top">

Select one of the options based on the description given next:

-   *Network ID*: A unique alphanumeric value assigned to every organization registered on Ariba SN; for example, AN01000000001.

-   *Network User ID*: A login name of an Ariba SN user. These names typically have the format of an e-mail address; for example, xyz@abc.com.




</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select one of the options based on the description given next:

-   *Shared Key*: If you have set the shared key in your Ariba account.

-   *Client Certificate*: If you have configured your certificate from a trusted certificate authority in the Ariba account.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Enter a name. This name is treated as an alias to the secure store where the user credentials are deployed. This value should be set according to the Authentication selected above. If you have selected *Client Certificate*, then enter the alias details in the *Private Key Alias* field.

This alias is used to identify the keystore credentials deployed on the SAP Cloud Integration account.

</td>
</tr>
</table>

Select the *Scheduler* tab and provide values in the fields as follows.

**Scheduler**


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

*Schedule on Day*

</td>
<td valign="top">

Specify a date and time or interval for executing the data polling.

</td>
</tr>
<tr>
<td valign="top">

*Schedule to Recur*

</td>
<td valign="top">

Specify a recurring pattern for consistently running the polling process. It can be scheduled on daily, weekly, or monthly basis.

-   *Daily*: Run message polling every day to fetch data from the Ariba system.

-   *Weekly*: Run the message polling every week on specified days of the week to fetch data from the Ariba system.

-   *Monthly*: Execute the message polling every month on the specified date to fetch data from the Ariba server.

    > ### Note:  
    > If the specified date is not applicable in a particular month, the data polling is not executed in that month. For example, if the 30th day is selected, polling will not be executed in the month of February, as 30th is not a valid day for February.




</td>
</tr>
<tr>
<td valign="top">

*On Date* \(only if *Schedule on Day* is selected\)

</td>
<td valign="top">

Specific date on which the data polling process has to be initiated to fetch data from the Ariba system.

</td>
</tr>
<tr>
<td valign="top">

*On Time*

</td>
<td valign="top">

The time at which the data polling cycle has to be initiated. For example, if you want the data polling to be started at 4:10 p.m., enter 16:10. Note that the time must be entered in 24-hour format.

</td>
</tr>
<tr>
<td valign="top">

Every `xx` minutes between `HH` hours and `HH` hours

</td>
<td valign="top">

The connector fetches data from the Ariba system every ‘xx’ minutes between HH hours and HH hours.

> ### Note:  
> If you want the polling to run for the entire day, enter 1 and 59.



</td>
</tr>
<tr>
<td valign="top">

*Time Zone*

</td>
<td valign="top">

Select the time zone you want to use as reference for scheduling the data polling cycle.

</td>
</tr>
</table>

