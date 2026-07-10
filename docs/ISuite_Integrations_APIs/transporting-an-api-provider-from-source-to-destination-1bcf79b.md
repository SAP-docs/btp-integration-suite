<!-- loio1bcf79baa9c54502be3e85e9ffb83134 -->

# Transporting an API Provider from Source to Destination

You can choose to transport a single API provider from the source to the destination API portal. When you transport an API provider, it gets created in the destination.



<a name="loio1bcf79baa9c54502be3e85e9ffb83134__context_hnc_n5q_1pb"/>

## Context

> ### Note:  
> While transporting the API provider, if there are any associated certificates \(Key Store or Trust Store\), those would get transported to the destination API portal as well.
> 
> If you transport an API provider that already exists in the destination API portal, the API provider doesn't get overwritten.



<a name="loio1bcf79baa9c54502be3e85e9ffb83134__steps_cnz_rqq_1pb"/>

## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  Choose the API poviders that you want to transport to the *API Providers* tab page.

4.  Choose the *Action* icon against the required API provider and then select the *Transport* option. Alternatively, you can open the required API provider and in the details page select the option *Transport*.

5.  On the *Transport* popup, provide a description and choose *Yes*.

    The reference number for the transport request gets generated.

    In the Transport workbench, you can search for the API provider in the destination node under *Transport Description*.

6.  Go to the Transport subaccount and perform the following steps to navigate to the *Transport Nodes*.

    1.  In your web browser, log on to SAP BTP Cockpit and navigate to your Transport subaccount.

    2.  Choose *Instances and Subscriptions* from the left pane.

    3.  Go to *Subscriptions* \> *Cloud Transport Management* and choose *Go To Application*.

    4.  Choose *Transport Nodes* from the left pane.


7.  Select the destination node, which points to the destination API portal.

8.  Under the *Transport Description* column of the destination node, search for the API provider for which you triggered the transport.

9.  Choose *Import Selected* to import the selected API provider in the queue to the destination node.




<a name="loio1bcf79baa9c54502be3e85e9ffb83134__result_srz_n5c_q4b"/>

## Results

Go to the API portal of the destination subaccount, and choose *Configure* \> *APIs*. Under the *API Providers* tab, look for the API provider you transported. The API provider you transported appears on the list.

