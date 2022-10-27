<!-- loiobea14c9324df4382957366eeb403f8d3 -->

# Transporting a Key Value Map from Source to Destination

You can transport a single Key Value Map from the source API portal to the destination API portal.



<a name="loiobea14c9324df4382957366eeb403f8d3__context_htd_tvq_1pb"/>

## Context

For encrypted Key Value Maps, the Key-Value Map is transported with dummy values from the source to the destination API portal. For Non-encrypted Key Value Maps, the Key-Value Map is transported as is.

> ### Note:  
> If you transport a Key Value Map that already exists in the destination API portal, the Key Value Map doesn't get overwritten.



<a name="loiobea14c9324df4382957366eeb403f8d3__steps_cnz_rqq_1pb"/>

## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  Choose the *Key Value Map* that you want to transport on the *Key Value Maps* tab page.

4.  Choose the *Action* icon against the required Key Value Map and then select the *Transport* option. Alternatively, you can open the required Key Value Map and in the details page select the option *Transport*.

5.  On the *Transport* popup, provide a description and choose *Yes*.

    The reference number for the transport request gets generated.

    In the Transport workbench, you can search for the Key Value Map in the destination node under *Transport Description*.

6.  Go to the Transport subaccount and perform the following steps to navigate to the *Transport Nodes*.

    1.  In your web browser, log on to SAP BTP Cockpit and navigate to your Transport subaccount.

    2.  Choose *Instances and Subscriptions* from the left pane.

    3.  Go to *Subscriptions* \> *Cloud Transport Management* and choose *Go To Application*.

    4.  Choose *Transport Nodes* from the left pane.


7.  Select the destination node, which points to the destination API portal.

8.  Under the *Transport Description* column of the destination node, search for the Key Value Map for which you triggered the transport.

9.  Choose *Import Selected* to import the selected Key Value Map in the queue to the destination node.




<a name="loiobea14c9324df4382957366eeb403f8d3__result_srz_n5c_q4b"/>

## Results

Go to the API portal of the destination subaccount, and choose *Configure*. Under the *Key Value Maps* tab, look for the Key Value Map you transported. The Key Value Map appears on the list.

