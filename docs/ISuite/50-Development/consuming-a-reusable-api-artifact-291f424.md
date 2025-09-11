<!-- loio291f424e08ce431e86b2767f39f2fd68 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Consuming a Reusable API Artifact

Consuming reusable API artifacts significantly improves the consistency, efficiency, and maintainability of API development. By leveraging predefined components such as policies, mediation steps, and configurations, teams can ensure standardized behavior across APIs, reduce duplication, and simplify updates.



<a name="loio291f424e08ce431e86b2767f39f2fd68__prereq_qtk_13k_qwb"/>

## Prerequisites

-   Enable Cloud Integration and API Management capabilities.

-   Provision Edge Integration Cell runtime.




## Context

The calling API artifacts \(i.e., the API artifact that consume the reusable API artifact\) can leverage reusable API artifacts to encapsulate and invoke shared business logic or processing steps. This interaction is facilitated through the API Direct adapter, which enables seamless integration while maintaining encapsulation and reuse.

> ### Note:  
> A reusable API artifact cannot be invoked externally; it can only be called via a calling API artifact.
> 
> Reusable APIs cannot reference or call other reusable APIs. Nesting is not supported.

This section explains how a producer API consumes a reusable API artifact to integrate shared functionality within its flow.



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the integration package, then go to the *Artifacts* tab and choose the standard API artifact where you intend to consume the reusable API artifact.

4.  Navigate to the *Policies* tab. This API artifact will have a standard HTTP adapter. Now choose *Edit* to add a reusable API artifact to it. Click anywhre outside the *Policy Model* box to bring up the property sheet.

5.  In the property sheet, choose *References* \> *Global* \> *Add References* \> *API*.

6.  In the *References* dialog box, the parent package of the current API artifact is pre-selected in the *Package* dropdown. All available reusable API artifacts within this package are displayed in the list.

    You can also select a different integration package from the *Package* dropdown. This will update the list to show the reusable API artifacts available in the selected package. Choose the desired reusable API artifact from the list, then click *OK* to confirm your selection.

    This adds the reusable API artifact as the global reference to this standard API artifact.

7.  To make a call to the reusable API artifact, from the palette, choose ![](images/external_call_bfbf8b0.png) \(Call\) and then choose :envelope::gear: 

8.  Place the *Request Reply* shape in the policy model and connect it to the message path.

    To add this shape to the model, activate your pointing device somewhere inside the Policy Model box and release it. You can then further adjust the position of the shape. No further attributes are to be specified for this step type.

9.  In the palette, select *Participants* \(<span class="SAP-icons-V5"></span> icon\), select *Receiver*, and drop it outside the policy model.

10. Create a connection between the request reply step by selecting the :arrow_right:icon and connecting the arrow to the *Receiver*. Once the connection is established, configure the adapter type.

11. Select *API Direct* as the adapter type and go to the property sheet.

12. Under the *Connections* tab choose *Select*.

    The *Select Resource* dialog comes up where the list of reusable API artifacts are displayed.

13. Select the reusable API artifact and choose *OK*.

    This brings you to the *Connections* tab where you can see the address which is the base path of the reusable API artifact in read-only mode.

    Also, you can see the following checkboxes:

    -   *Send Body*: Enable this option if the original request includes a body and you want to pass that same body into the reusable flow. This is commonly used with POST, PUT, or PATCH methods where the request payload needs to be preserved and forwarded.
    -   *Retain Original Body for Next Steps*: Select this option to keep the original body available for use in the next steps.

    Additionally, fill in the following *Header Details*:

    -   *Request Header*: Enter a list of headers, separated by a pipe \(|\), that you want to send to the reusable API. By default, no custom headers are sent. Alternatively, use an \* to send all headers to the reusable API.
    -   *Response Header*: Enter a list of headers coming from the Reusable API's response, separated by a pipe \(|\), to be merged with the original request headers. Use an \* to receive all the headers from the Reusable API, which is also the default value.

    > ### Note:  
    > **Header behavior in reusable API artifact:**:
    > 
    > When a reusable API is called from another API artifact, the response headers from the reusable API are merged with the original request headers of the calling API artifact.
    > 
    > -   **Header Deletion** Let’s say a header present in the calling API is deleted using a Content Modifier inside the reusable API. When the headers from the reusable API artifact are merged with those from the calling API artifact, the deleted header will still be present in the merged result.
    > -   **Header Modification** 
    > 
    >     Let’s say a header present in the calling API is modified using a Content Modifier inside the reusable API. This applies whether a specific response header is selected or all response headers are selected \(expressed with \* in the calling API\). When the headers from the reusable API artifact are merged with those from the calling API artifact, the modified header will be reflected in the merged result.

14. Now choose *Save*.


