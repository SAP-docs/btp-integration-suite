<!-- loio5c76048b04594888a47e74d35a91c08a -->

# RFC Receiver Adapter

Connects an SAP Cloud Integration tenant to a remote receiver system using Remote Function Call \(RFC\).

You can use Remote Function Call \(RFC\) to integrate on-premise ABAP systems with the systems hosted on the cloud using the Cloud connector, and also with S/4 HANA Cloud system available in public internet.

RFC executes the function call using synchronous communication, which means that both systems must be available at the time the call is made. When the call is made for the function module using the RFC interface, the calling program must specify the parameters of the connection in the form of an RFC destination. RFC destinations provide the configuration needed to communicate with an on-premise ABAP and S/4 HANA cloud systems through an RFC interface.

**Prerequisites**

-   Define the required RFC destination for your application.

    To create destinations you need to either have administrator or developer role in SAP BTP cockpit. For more information on how to create RFC destinations, see [Creating an RFC Destination](creating-an-rfc-destination-3b55fa7.md).

    The RFC destination configuration settings are used by the SAP JAVA Connector \(SAP JCo\) to establish and manage the connection with on-premise and S/4 HANA cloud system available in public internet. While you configure a destination make sure to select internet as the proxy type to establish connection with an application over the internet.

-   You must have the remote function module XSD file.

    > ### Tip:  
    > Follow the steps to generate WSDL function modules for those who don’t have access to on-premise \(Process Integration\) system:
    > 
    > 1.  Identify the required function module and the backend system to where the function module is called.
    > 
    > 2.  Login to the backend system and start SICF transaction to maintain services for HTTP communication.
    > 
    > 3.  Activate the Internet Communication Framework \(ICF\) service to make it accessible.
    > 
    > 4.  Access the backend application to generate and fetch the WSDL for the desired function module.
    > 
    >     `https://<backend_host>:<backend_https_port>/sap/bc/soap/wsdl11?services=<function_module_name>`


**Prerequisites for using adapter on Edge Integration Cell runtime**

-   Create a new RFC destination with Proxy Type Local in BTP Destinations environment. For more information, see [Creating an RFC Destination](creating-an-rfc-destination-3b55fa7.md)
-   Set up SNC on Edge Integration Cell for productive use of the RFC Adapter. For more information, see [Set Up SNC on Edge Integration Cell](../60-Security/set-up-snc-on-edge-integration-cell-c2315d3.md)

> ### Remember:  
> -   The RFC adapter supports SAP NetWeaver 7.31 and higher.
> 
> -   The RFC adapter supports Synchronous RFC \(sRFC\) and transactional execution of function module \(can execute BAPI\_TRANSACTION\_COMMIT/BAPI\_TRANSACTION\_ROLLBACK\). tRFC is not supported in Cloud Foundry environment and Edge Integration Cell runtime.
> 
> -   From RFC adapter version 1.2.0, function modules that contains "/" in their names are also supported. For these function modules you need to replace "/" with "\_-" \(underscore and hyphen\) in the input XML.
> 
> -   The date provided in the input XML must be of format "YYYY-MM-DD".
> 
> -   If the parameters of the ABAP function are changed, the integration flow containing the RFC adapter must be redeployed for the new parameters to be reflected in the output XML. However, this doesn't hold good in case the RFC adapter is configured with dynamic destination. For the changed parameters to be reflected in the output, the integration flow must be redeployed with the static destination only.

Once you have created a receiver channel and selected the RFC Receiver Adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

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

*Destination* 

</td>
<td valign="top">

Enter the RFC destination configured in SAP BTP cockpit for your application.

> ### Note:  
> You can create dynamic destinations by using expressions \(header, property\) in the Content Modifier.
> 
> 1.  Select Content Modifier in the integration flow. Then, go to Message Header in Content Modifier properties and set header value as the destination name. For example, abc.
> 2.  Select your RFC adapter and. In the *Destination* field, assign dynamic destination by using the expression: $\{header/property.header/property name\}. For example $\{header.abc\} or $\{property.abc\} where abc is the value of the header or property.



</td>
</tr>
<tr>
<td valign="top">

*Send Confirm Transaction* 

</td>
<td valign="top">

\(Applicable to BAPI functions\) By default this option is disabled. You can enable this option if you want to support BAPI functions that require BAPI\_TRANSACTION\_COMMIT to be invoked implicitly by the RFC receiver adapter.

> ### Note:  
> Ensure the following ABAP functions are allowlisted in Cloud connector before using this option:
> 
> -   BAPI\_TRANSACTION\_COMMIT
> 
> -   BAPI\_TRANSACTION\_ROLLBACK

> ### Caution:  
> If you enable this option for non-BAPI functions, BAPI\_TRANSACTION\_COMMIT can still be invoked, which is redundant and hence may impact RFC function execution time.



</td>
</tr>
<tr>
<td valign="top">

*Create New Connection* 

</td>
<td valign="top">

If you enable this option, the adapter creates a new RFC connection in the backend system, every time a new call is made to the target system.

> ### Remember:  
> This option must be selected if you are using principal propagation. If you do not select this option, principal propagation will not work as expected.



</td>
</tr>
</table>

**Related Information**  


[Generating XSD/WSDL for Function Modules Using ESR \(Process Integration\)](generating-xsd-wsdl-for-function-modules-using-esr-process-integration-57a6b6e.md "Generate an XSD/WSDL file for a function module using the Enterprise Services Repository (ESR).")

[Creating an RFC Destination](creating-an-rfc-destination-3b55fa7.md "Create an RFC destination by adding necessary properties before using it in the integration flow of RFC adapter.")

