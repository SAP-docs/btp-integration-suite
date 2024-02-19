<!-- loio1fc41acd69034dc480cc6d6413dfe74b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Converting Externally Managed APIs to Internally Managed APIs

You can convert an external API, whose lifecycle is managed by an external API Management solution, to an internal API, which is managed by SAP Integration Suite.



## Context

After the conversion, you can create API proxies for these internally managed APIs, import, and publish them and apply policies to them. You can apply all the SAP Integration Suite capabilities to these managed APIs.



## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  Identify the externally managed API that you want to convert from the list of APIs.

    > ### Note:  
    > The externally managed API is marked with an <span class="SAP-icons-TNT-V3"></span> icon, and the *Status* column dosen't display the status of the API.

4.  Choose the <span class="SAP-icons-V5"></span> Action icon against the required API and then select the *Manage* option. Alternatively, you can open the required API, and then select the option *Manage*.

5.  You can edit the prefilled data of the externally managed API before choosing *Deploy*.

    > ### Note:  
    > You can attach policies to the API only after it’s deployed.

6.  To attach policies, navigate back to the list of APIs on the *Configure* \> *APIs* page, choose the externally managed API that you’ve converted into an internally managed API.

    You can see that the status column now shows the status of the API as Deployed.

7.  Open the required API, and choose *Policies* on the details screen. See [Create a Policy](create-a-policy-c90b895.md) for more information.




<a name="loio1fc41acd69034dc480cc6d6413dfe74b__result_rrv_twd_hpb"/>

## Results

You've converted an externally managed API into an internally managed API and have applied policies to that managed API.



<a name="loio1fc41acd69034dc480cc6d6413dfe74b__postreq_p5s_yc3_jpb"/>

## Next Steps

To import and publish the internally managed APIs, refer the following topics: [Import an API Definition](import-an-api-definition-9342a93.md) and [Publish API Proxies](publish-api-proxies-75a4a11.md) 

