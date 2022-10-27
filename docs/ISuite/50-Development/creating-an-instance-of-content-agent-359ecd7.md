<!-- loio359ecd74d940417699081e662d4b5c1c -->

# Creating an Instance of Content Agent

Create a service instance and a service key of content agent in your source subaccount. The service key details are needed while creating the **ContentAssemblyService** destination.



<a name="loio359ecd74d940417699081e662d4b5c1c__context_wyp_t5q_v4b"/>

## Context

Content Agent allows you to assemble the content of different content providers, and export it to the transport queue.



## Procedure

1.  Create a service instance of Content Agent. To create the service instance, follow the steps described in [Create Instance](https://help.sap.com/viewer/ae1a4f2d150d468d9ff56e13f9898e07/Latest/en-US/1f45ddc3d6194886802924068724b59f.html).

2.  Create a service key of Content Agent. For more information, see [Create Service Key](https://help.sap.com/viewer/ae1a4f2d150d468d9ff56e13f9898e07/Latest/en-US/c0ec2ba3016644a19cd6322fbc72ea2a.html).

    Once the service key is created, make a note of the url, clientid, and clientsecret as these details would be needed while creating HTTP destination ContentAssemblyService for Content Agent. To copy the details, perform the following steps:

    1.  Choose the Content Agent service instance that you recently created to expand the right-pane.

    2.  To view the credentials, choose the Content Agent *<Service Key Name\>*.

    3.  Choose the *JSON* tab and copy the URL.





<a name="loio359ecd74d940417699081e662d4b5c1c__result_ksq_fgv_n4b"/>

## Results

You've created an instance of Content Assembly Service and its corresponding service key in the source subaccount.

