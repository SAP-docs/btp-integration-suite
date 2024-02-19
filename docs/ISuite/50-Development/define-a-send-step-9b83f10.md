<!-- loio9b83f10c882f44988a2856ceb8515b3c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define a Send Step

You use a send step type to configure a service call to a receiver system for scenarios and adapters where no reply is expected.



## Context

To use this step makes only sense in combination with one of the following adapter types \(for the channel between the send step and the receiver\):

-   AS2 adapter

-   FTP adapter

-   JMS adapter

-   Mail adapter

-   SOAP SAP RM adapter

-   SFTP adapter

-   XI adapter \(Quality of Service „Exactly Once“\)




## Procedure

1.  Add a *Send* step to the integration process by performing the following substeps.

    1.  In the palette, choose ![](images/external_call_bfbf8b0.png) \(Call\) and then choose :envelope:. In the submenu, choose :envelope:

    2.  Place the *Send* shape in the integration process.


2.  In the palette, click *Call* \(![](images/Image_Map_Arrow_Icon_76d790c.png) icon\) and choose *External Call* \> *Send*, and drop it inside the Integration Process pool.

3.  In the palette, click *Participants* \(<span class="SAP-icons-V5"></span> icon\), select *Receiver*, and drop it outside the Integration Process pool.

4.  Create a connection between the send step and the receiver and configure the channel \(selecting one of the above mentioned adapter types\).


