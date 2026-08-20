<!-- loio883b3ee83a3b4669bee0a47bb5990053 -->

# Understanding the ProcessDirect Adapter

The application allows you to use your custom integration flow for the B2B scenario using ProcessDirect adapter. This chapter explains how the process works.



## What is a ProcessDirect Adapter

Let's say that you have two integration flows in your tenant and you want to establish communication between them without any network overhead. The ProcessDirect adapter helps you achieve fast and direct communication between integration flows of the same tenant without routing through the load balancer.

A ProcessDirect adapter can be a sender or receiver adapter depending on the direction of the message flow.

The interchange processing flow in our package uses this adapter to enable the customization of your integration flows, as shown in the following image:

![Process flow diagram showing sender to receiver interchange with validation and processing steps.](images/ProcessDirect_Adapter_in_Interchange_Processing_Flow_95e4747.jpg)

Now, when you enable the *Custom Integration Flow* in your agreement, another integration flow is picked up by the ProcessDirect adapter instead of this generic integration flow. Once you enable this option, you also need to provide the name of your integration flow that has to be connected with using the adapter. This name is then picked up by the ProcessDirect adapter during runtime and the corresponding integration flow is called. This connection is established through the address mentioned in the *Connection* tab of the adapter. The option to use a custom integration flow is provided in the following steps:

1.  Pre-Processing
2.  Main Mapping
3.  Post-Processing

The custom integration flows are used in the intermediate step of the entire process. This means that the adapter sends a message to the custom integration flow and in turn receives a response from that integration flow which is then used in the next step of the process. To meet this requirement, we use *Request-Reply*.

The request-reply flow step sends a message to the custom integration flow and waits for a reply. The custom integration flow performs its own integration process and then sends the resulting message to the request-reply step. The request-reply step then sends this message to the next step of the interchange process flow.

To learn more about the ProcessDirect adapter, see the documentation on the [ProcessDirect Adapter](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/74457187451f431298355fbbf807d086.html) and the blog [ProcessDirect Adapter](https://blogs.sap.com/2018/02/14/processdirect-adapter/)



<a name="loio883b3ee83a3b4669bee0a47bb5990053__section_bft_3sx_lyb"/>

## Use Case for the Process Direct Adapter

You've now understood how the ProcessDirect adapter works. The application also allows you to configure dynamic parameters in your agreement. These parameters are later consumed by the custom integration flow. This use case might pave the way to the following questions:

-   From which PID/ID can one read the dynamic parameters from Partner Directory?

-   After fetching the dynamic parameters from PD, how can I convert it into a readable string \(because dynamic parameters are stored in binary format in PD\) and then use it in a Groovy script?

Consider the following sample code:

> ### Sample Code:  
> ```
> 
> import com.sap.gateway.ip.core.customdev.util.Message;
> import com.sap.it.api.pd.PartnerDirectoryService;
> import com.sap.it.api.ITApiFactory;
> import com.sap.it.api.pd.BinaryData;
> import groovy.json.JsonSlurper;
> 
> def Message processData(Message message) {
>     def headers = message.getHeaders();
>     def partnerId = headers.get("SAP_TPM_ACTIVITYPARTNERID");
>     def service = ITApiFactory.getApi(PartnerDirectoryService.class, null);
>     def customActivityParams = service.getParameter("SAP_TPM_CustomActivityParams", partnerId, BinaryData.class);
>     if (customActivityParams != null){
>         def jsonRoot = new JsonSlurper().parseText(new String(customActivityParams.getData()));
>         message.setProperty("CustomKey", jsonRoot.MyTest1);
>     }
>     return message;
> }
> 
> ```

Here, `"SAP_TPM_ACTIVITYPARTNERID"` is the header that maintains the PID and `"SAP_TPM_CustomActivityParams"` is the ID. Both values are fixed strings.

The code contains the dynamic parameter key `”MyTest1”` and the corresponding value `“val23”`. To apply the previous Groovy script to a custom integration flow, store the value `“val23”` to an exchange property named `“CustomKey”`.

To learn more about such use cases, see [Script Use Cases](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/script-use-cases).

To learn more about script APIs, see [Script API](https://help.sap.com/doc/a56f52e1a58e4e2bac7f7adbf45b2e26/Cloud/en-US/index.html).



<a name="loio883b3ee83a3b4669bee0a47bb5990053__section_xtc_43r_zyb"/>

## Pointers to Consider

When using this ProcessDirect adapter for your sender and receiver scenarios, consider the following:

-   The Groovy scripts in the package aren't public to customers. Use caution while applying the Groovy code to your custom integration flows.

-   The step *1b* is used for internal purposes. It's not recommended to call the ProcessDirect in step 1b, but you can use the adapter in step *1a* which is *Step 1 - Sender Process Direct Communication Flow V2*.
-   You can transfer all the camel header properties that you define in your custom integration flows to ProcessDirect Step 1a. But if your camel header property name is the same as SAP's camel header property \(with prefix *SAP\_*\), the property value might be overwritten by the generic integration flow. To avoid this, use a different property name in the camel header.
-   The computed PID can be used not only in Step 2 ProcessDirect, but also in Step 3 ProcessDirect of the integration flow.

