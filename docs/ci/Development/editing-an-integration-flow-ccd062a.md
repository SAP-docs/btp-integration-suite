<!-- loioccd062ad07e7468e9b13fa0535d5f01e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Editing an Integration Flow



## Context

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

You are editing an OData service artifact and you have created an OData model. You have provided binding information for at least one OData object in the model.

Once a function import or operation of an entity set is bound to a data source, a predefined integration flow is set up for you. Within this integration flow, the OData adapter is selected as the default for the sender channel. The data source to which the operation is bound is selected as the default adapter for the receiver channel.

You can use this procedure to update the predefined integration flow to suit your business scenario.



## Procedure

1.  Choose *Navigate to Integration Flow Editor* \(<span class="SAP-icons-V5"></span>\) for an operation or function import that is bound to a data source. The associated integration flow opens in the Integration Flow Editor.

2.  Edit the integration flow according to your requirements.

    > ### Note:  
    > The following points need to be kept in mind when editing integration flows in an OData service artifact:
    > 
    > -   The OData sender channel is not editable.
    > 
    > -   The OData sender channel, participant and start event cannot be deleted.
    > 
    > -   A new sender participant cannot be dragged and dropped into the integration flow.
    > 
    > -   If you modify the default name of the receiver adapter, you need to make sure it is unique across all integration flows in an OData service artifact.
    > 
    > -   If your service requires *Session Handling*, ensure that session handling is enabled for each integration flow in your OData service project.
    > 
    > -   You need to ensure that the Namespace Mapping entered in the runtime configuration, is consistent across all integration flows in an OData service artifact.
    > 
    >     For example, you can enter the namespace-prefix pair `xmlns:test=http://sapcd.com/testABC` in multiple integration flows in an OData service artifact. You cannot enter `xmlns:test=http://sapcd.com/testABC` in one integration flow and enter `xmlns:test=http://sapab.com` in another integration flow in the same OData service artifact. However, it is perfectly valid to enter `xmlns:test=http://sapcd.com/testABC` in one integration flow and `xmlns:test2=http://sapab.com` in another.
    > 
    > -   You can add other receiver/outbound adapters in the integration flow, but ensure that one of the following outbound adapters is present in the integration flow:
    >     -   OData V2
    > 
    >     -   ODC
    >     -   HTTPS
    >     -   SOAP

    For more information about configuring integration flow components, see [Configure Integration Flow Components](configure-integration-flow-components-3171795.md).

3.  Once you have finished editing the integration flow, choose *OK*.

4.  Choose *Back* \(<span class="SAP-icons-V5"></span>\) to get back to the Service Designer page.

5.  Choose *Save* to save your changes to the OData service artifact.

    > ### Note:  
    > To retain a copy of the current artifact, choose *Save as version*.


**Related Information**  


[Predefined Integration Flows](predefined-integration-flows-d41a54f.md "")

