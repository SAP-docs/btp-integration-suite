<!-- loio49dffa3da5784b7bb5dd6d8bf975939c -->

# Configure the Ariba Receiver Adapter

The Ariva receiver adapter connects SAP Integration Suite to the Ariba network. Using this adapter, SAP and non-SAP cloud applications can send business-specific documents in commerce eXtensible Markup Language \(cXML\) format to the Ariba network.

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

Once you have created a receiver channel and selected the Ariba receiver adapter, you can configure the following attributes. See: [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

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

*cXML Version* 

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

