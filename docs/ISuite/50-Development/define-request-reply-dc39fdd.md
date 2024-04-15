<!-- loiodc39fdd4a44d4b9a9eabb56f49434250 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Request Reply

You use this step to call an external receiver system in a synchronous step and get back a response.



## Context

Certain integration scenarios might require that the Cloud Integration tenant communicates with an external service, retrieves data from it, and further processes the data. In such cases, you can use the request reply step as an *exit* to connect to the external service.

For example, in your integration scenario the tenant needs to retrieve data on electronic products from a product catalog \(the external service\) and to further process the data. If the external service exposes the data through a REST API, you can use the request reply step to connect to the service via the HTTP or OData receiver adapter.

In the integration flow model, you design the external service as a receiver shape and to connect the request reply step with the receiver shape with a receiver channel.

> ### Caution:  
> The request reply step does not work with all available adapter types.
> 
> Adapters that can be used with the following receiver adapter types:
> 
> -   AMQP
> 
> -   Ariba
> 
> -   AS2
> 
> -   AS4
> 
> -   AzureStorage
> 
> -   Dropbox
> 
> -   Elster
> 
> -   Facebook
> 
> -   FTP
> 
> -   OData
> 
> -   HTTP
> 
> -   IDoc
> 
> -   JDBC
> 
> -   JMS
> 
> -   Kafka
> 
> -   LDAP
> 
> -   Mail
> 
> -   MDI
> 
> -   Microsoft Sharepoint
> 
> -   ODC
> 
> -   OpenConnectors
> 
> -   ProcessDirect
> 
> -   RabbitMQ
> 
> -   RFC
> 
> -   ServiceNow
> 
> -   SFTP
> 
> -   Slack
> 
> -   SOAP
> 
> -   Splunk
> 
> -   SuccessFactors
> 
> -   Twitter
> 
> -   Workday
> 
> -   XI



## Procedure

1.  If you want to add a *Request Reply* step to the integration process, perform the following substeps.

    1.  In the palette, choose ![](images/external_call_bfbf8b0.png) \(Call\) and then choose :envelope:In the submenu, choose :gear:

    2.  Place the *Request Reply* shape in the integration process and define message path.


2.  To add this shape to the model, activate your pointing device somewhere inside the *Integration Process* box of the integration flow model.

    No further attributes are to be specified for this step type.

3.  In the palette, select *Participants* \(<span class="SAP-icons-V5"></span> icon\), select *Receiver*, and drop it outside the Integration Process pool.

4.  Create a connection between the request reply step and the receiver and configure the channel.


