<!-- loio681bb1a232eb436db8df75c6f73485ee -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Adding a Destination Node in Cloud Transport Management Applications

The Transport Management Application contains the transported content, so you need a Destination node to represent the target endpoint.



<a name="loio681bb1a232eb436db8df75c6f73485ee__context_gtc_y43_v4b"/>

## Context

To add a Destination node in the Cloud Transport Management Applications, execute the following steps:



<a name="loio681bb1a232eb436db8df75c6f73485ee__steps_wrf_j44_bpb"/>

## Procedure

1.  In your web browser, log on to SAP BTP Cockpit and navigate to your Transport subaccount.

2.  Choose *Instances and Subscriptions* from the left pane.

3.  Go to *Subscriptions* \> *Cloud Transport Management* and choose *Go To Application*.

4.  Choose *Transport Nodes* from the left pane.

5.  Choose :heavy_plus_sign: to add a destination node.

    > ### Note:  
    > If the user has a Cloud Integration subscription in the same source subaccount and is opting for SAP Cloud Transport Management service for transporting the content, then the destination node can be reused for the Integration suite.
    > 
    > If Cloud Integration and API Management capabilities are activated under Integration suite subscription, then both the capabilities can use the same source node and the destination node.

6.  In the *Create Node* dialog box, enter a node name that is unique, for example `Destination_node1`, and enable the *Allow Upload to Node* option.

7.  Choose `Multi-Target Application` from the *Content Type* dropdown.

8.  Choose the destination `TMSDeploy` you created in the Transport subaccount from the *Destination* dropdown. This destination contains the details of the destination subaccount's org and space name. Refer [Create a Deploy Service Destination in Cloud Transport Management Service Subaccount](create-a-deploy-service-destination-in-cloud-transport-management-service-subaccount-09b1eec.md) for the Destination name.

9.  Choose *OK*.




<a name="loio681bb1a232eb436db8df75c6f73485ee__result_qj5_mp4_bpb"/>

## Results

You've added a Destination node in the Transport Management Applications.

