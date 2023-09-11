<!-- loio03e69592b8f04bf5aa350966802f994b -->

# How to Work with the Example Integration Flows

For each guideline, one or more example integration flows are provided that help you to quickly understand the topic. These integration flows are kept as simple as possible and can be set up and executed quickly.



<a name="loio03e69592b8f04bf5aa350966802f994b__section_fww_m5k_wjb"/>

## Integration Packages

The integration flows are contained in a set of dedicated integration packages published on SAP Business Accelerator Hub. To learn how to access the integration packages and deploy the integration flows, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).



<a name="loio03e69592b8f04bf5aa350966802f994b__section_il4_54w_sjb"/>

## HTTP Client as Sender Component

Many integration flows are triggered by an HTTP call.

You can use any HTTP client software to execute these integration flows, for example, Postman. To facilitate running the scenario when using Postman, we provide Postman collections that allow you to run the HTTP requests with minimal effort.

The Postman collections associated with the example integration flows are contained in the integration packages. To learn how such a Postman collection can be downloaded, imported into Postman, and executed, see [Working with Postman Collections](working-with-postman-collections-1d11aa6.md).



<a name="loio03e69592b8f04bf5aa350966802f994b__section_z2r_v4w_sjb"/>

## Generic Receiver

For the example integration flows, we provide a generic receiver. This measure saves you the effort of configuring a receiver system. The generic receiver is implemented with a separate integration flow \(with name *GenericReceiver*\) that creates a data store entry for each receiver call.

Each integration package \(as listed under [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md)\) has its own *Generic Receiver* integration flow with an integration package-specific address.

As a prerequiste to run an example integration flow, you also need to deploy the *Generic Receiver* integration flow contained in the same integration package as the example integration flow.

For more information about this integration flow, see [Generic Receiver](generic-receiver-83a6970.md).



<a name="loio03e69592b8f04bf5aa350966802f994b__section_swt_v4w_sjb"/>

## OData Calls to an External Component

Certain reference integration flows read data from an external WebShop application.

These integration flows are connected to a WebShop application that we provide for training and demonstration purposes.

For more information, see [WebShop Example Application](webshop-example-application-767d8ef.md)

