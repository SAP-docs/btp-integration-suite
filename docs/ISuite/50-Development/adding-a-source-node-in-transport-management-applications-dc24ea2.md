<!-- loiodc24ea24ff4f4f9aa34479acd03241df -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Adding a Source Node in Transport Management Applications

The Transport Management Application contains the transported content, so you need a Source node to represent the source endpoint.



<a name="loiodc24ea24ff4f4f9aa34479acd03241df__context_gtc_y43_v4b"/>

## Context

To add a Source node in the Transport Management Applications, execute the following steps:



<a name="loiodc24ea24ff4f4f9aa34479acd03241df__steps_wrf_j44_bpb"/>

## Procedure

1.  In your web browser, log on to SAP BTP Cockpit and navigate to your Transport subaccount.

2.  Choose *Instances and Subscriptions* from the left pane.

3.  Go to *Subscriptions* \> *Cloud Transport Management* and choose *Go To Application*.

4.  Choose *Transport Nodes* from the left pane.

5.  Choose :heavy_plus_sign: to add a source node.

    > ### Note:  
    > If the user has a Cloud Integration subscription in the same source subaccount and is opting for SAP Cloud Transport Management service for transporting the content, then the source node can be reused for the Integration suite.
    > 
    > If Cloud Integration and API Management capabilities are activated under Integration suite subscription, then both the capabilities can use the same source node and the destination node.

6.  In the *Create Node* dialog box, enter a node name that is unique, for example `Source_node1`, and enable the *Allow Upload to Node* option.

7.  Choose *OK*.




<a name="loiodc24ea24ff4f4f9aa34479acd03241df__result_qj5_mp4_bpb"/>

## Results

You've added a Source node in the Cloud Transport Management Applications.

