<!-- loio115d1733f792409aaaf552026266bcf4 -->

# Transporting a Certificate from Source to Destination

You can choose to transport a single Key Store Certificate or a Trust Store Certificate from the source API portal to the destination API portal.



<a name="loio115d1733f792409aaaf552026266bcf4__context_hnc_n5q_1pb"/>

## Context

> ### Note:  
> Only the certificate with dummy content gets transported from the source to the destination API portal.
> 
> If you transport a Certificate that already exists in the destination API portal, the Certificate doesn't get overwritten.



<a name="loio115d1733f792409aaaf552026266bcf4__steps_cnz_rqq_1pb"/>

## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  Choose the *Certificate* that you want to transport on the *Certificates* tab page.

4.  Choose the *Action* icon against the required Certificate and then select the *Transport* option. Alternatively, you can open the required Certificate and in the details page select the option *Transport*.

5.  On the *Transport* popup, provide a description and choose *Yes*.

    The reference number for the transport request gets generated.

    In the Transport workbench, you can search for the Certificate in the destination node under *Transport Description*.

6.  Go to the Transport subaccount and perform the following steps to navigate to the *Transport Nodes*.

    1.  In your web browser, log on to SAP BTP Cockpit and navigate to your Transport subaccount.

    2.  Choose *Instances and Subscriptions* from the left pane.

    3.  Go to *Subscriptions* \> *Cloud Transport Management* and choose *Go To Application*.

    4.  Choose *Transport Nodes* from the left pane.


7.  Select the destination node, which points to the destination API portal.

8.  Under the *Transport Description* column of the destination node, search for the Certificate for which you triggered the transport.

9.  Choose *Import Selected* to import the selected Certificate in the queue to the destination node.




<a name="loio115d1733f792409aaaf552026266bcf4__result_srz_n5c_q4b"/>

## Results

Go to the API portal of the destination subaccount, and choose *Configure*. Under the *Certificates* tab, look for the Certificate you transported. The certificate with dummy content appears on the list.

