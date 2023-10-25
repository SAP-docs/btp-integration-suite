<!-- loio3a4cdd2fc576481ca91f3e6f26f446bd -->

# Transporting a Product from Source to Destination

You can choose to transport a single product from the source to the destination API portal. When you transport a product, it gets created in the destination.



<a name="loio3a4cdd2fc576481ca91f3e6f26f446bd__context_eyj_2wq_1pb"/>

## Context

APIs, Permissions, and custom attributes, that are associated with the product get transported along with the product and get created in the destination API portal. However, the Rate Plan associated with the product dosen't get transported.

> ### Note:  
> If the product and its associated entities \(APIs, Permissions, and Custom Attributes\) already exist in the destination API portal, they get overwritten during the transport. Additionally, the APIs attached to the product get imported to the destination API portal in the deployed state. However, the artifacts of the APIs associated to the product \(such as API Provider, Key Store Certificate, Trust Store, and Key-Value Maps\) remain unaffected if they already exist in the destination API portal.
> 
> Also, transporting a product from the source to the destination API portal in a draft state is not allowed if the product already exists in the destination API portal in a published state and vice versa.
> 
> While transporting a product that already exists in the destination portal, ensure that the product is in the same state in both the source and the destination API portal. If the product is in the same state, it gets overwritten in the destination during the transport.



<a name="loio3a4cdd2fc576481ca91f3e6f26f446bd__steps_cnz_rqq_1pb"/>

## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  Choose the *Product* that you want to transport on the *Products* tab page.

4.  Choose the *Action* icon against the required product and then select the *Transport* option. Alternatively, you can open the required product and in the details page select the option *Transport*.

5.  On the *Transport* popup, provide a description and choose *Yes*.

    The reference number for the transport request gets generated.

    In the Transport workbench, you can search for this product in the destination node under the *Transport Description*.

6.  Go to the Transport subaccount and perform the following steps to navigate to the *Transport Nodes*.

    1.  In your web browser, log on to SAP BTP Cockpit and navigate to your Transport subaccount.

    2.  Choose *Instances and Subscriptions* from the left pane.

    3.  Go to *Subscriptions* \> *Cloud Transport Management* and choose *Go To Application*.

    4.  Choose *Transport Nodes* from the left pane.


7.  Select the destination node, which points to the destination API portal.

8.  Under the *Transport Description* column of the destination node, search for the product for which you triggered the transport.

9.  Choose *Import Selected* to import the selected product in the queue to the destination node.




<a name="loio3a4cdd2fc576481ca91f3e6f26f446bd__result_srz_n5c_q4b"/>

## Results

The product from the source API portal is transported to the destination API portal.



<a name="loio3a4cdd2fc576481ca91f3e6f26f446bd__postreq_h52_dvj_t4b"/>

## Next Steps

Once the product is transported to the destination API portal, you must ensure that the dummy security values that got imported along with the API entity associated with the product must be replaced with the actual values. For more information, see [Editing the Security Fields for the Imported API Entities](editing-the-security-fields-for-the-imported-api-entities-0c184e3.md).

