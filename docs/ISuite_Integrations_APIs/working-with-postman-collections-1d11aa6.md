<!-- loio1d11aa6aa72441c4b578130cdff5cf1b -->

# Working with Postman Collections

Each guideline or pattern has associated example integration flows and 1 Postman collection, which can be used to trigger the example.

The integration flows, as well as the associated Postman collections, are contained in the related integration package.



<a name="loio1d11aa6aa72441c4b578130cdff5cf1b__section_iym_ctk_wjb"/>

## Downloading the Postman Collection

The name of the Postman collection starts with the name of the guideline and ends with the suffix *\_PostmanCollection*. You can find it in the *Documents* tab of the integration package. Download the compressed file and unpack it to any folder. After that, import the unpacked `.json` file into your Postman by clicking *Import* in the Postman user interface.



<a name="loio1d11aa6aa72441c4b578130cdff5cf1b__section_xf3_mtk_wjb"/>

## Executing a Postman Collection

After having imported the Postman collection, you must first define an environment that contains the connection parameters of your tenant. In the upper-right corner of the Postman user interface, select *Manage Environments* and add a new environment with an arbitrary name. Add the following 3 variables with their corresponding values to this environment:

*username*: The name of your user

*password*: Your password

*host*: The fully qualified hostname of your Cloud Integration tenant

After you've performed this task, you can start the Postman runner. On the *Collection Runner* user interface, choose your collection, select the environment, and start the run. Now, all requests of the collection are sent and the tests, if any, are executed.

> ### Note:  
> When the example integration flow is protected against Cross-Site-Request-Forgery \(CSRF\) and the associated setting is activated in the HTTPS sender adapter, note the following: If the Postman collection contains an HTTP Post request, typically 2 requests are necessary:
> 
> -   A GET request where the X-CSRF-Token is fetched from the target system
> 
> -   Another POST request using the value of the fetched X-CSRF-Token
> 
> 
> In such cases, the Postman collection contains both requests.
> 
> More information:
> 
> [HTTPS Sender Adapter](https-sender-adapter-0ae4a78.md)
> 
> [Send the HTTP Request and Process the Integration Flow](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/f08cca6af4fd48b687d3f86c329efaed.html "Set up an HTTP client using Postman and send the HTTP request.") :arrow_upper_right:

> ### Note:  
> Some integration flows are triggered by a Timer event. In that case, the body of the message that represents the inbound call is created initially within the integration flow in a Content Modifier step. No HTTP request is required to start the integration flow. The integration flow is started on deployment.

