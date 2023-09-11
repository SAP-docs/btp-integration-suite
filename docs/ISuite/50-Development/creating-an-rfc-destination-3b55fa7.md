<!-- loio3b55fa7b83874b5ca3b6b6b5998a73f6 -->

# Creating an RFC Destination

Create an RFC destination by adding necessary properties before using it in the integration flow of RFC adapter.



## Context

> ### Note:  
> SAP System Identification \(SID\) code must be unique for RFC backend, see: SAP Note [1405466](https://launchpad.support.sap.com/#/notes/1405466).



## Procedure

1.  Log into the SAP BTP cockpit and navigate to your subaccount.

2.  Choose *Connectivity* \> *Destinations*.

3.  Choose *New Destination* and enter destination name.

4.  Enter the details for the parameters *<Name\>*, *<URL\>*, *<User\>*, *<Password\>*, and select *<Type\>* as *RFC*.

    > ### Note:  
    > For setting up an RFC connectivity for ABAP environment using principal propagation. Select *OnPremise* from the value help and then for *<Authentication\>*, select *PrincipalPropagation*.

5.  Add the following properties \(first four properties are mandatory\) and assign appropriate values:

    -   *jco.client.ashost*

        > ### Note:  
        > The value provided for application server host \(ashost\) property is the access control value created in the Cloud connector.

    -   *jco.client.client*
    -   *jco.client.lang*
    -   *jco.client.sysnr*
    -   \(optional\) *jco.destination.pool\_capacity*
    -   *jco.destination.auth\_type* \(while configuring for principal propagation the value for the property is "`jco.destination.auth_type = PrincipalPropagation`"\)

    **WebSocket Connection**

    -   *jco.client.client*
    -   *jco.client.tls\_trust\_all*
    -   *jco.client.wshost*
    -   *jco.client.wsport*
    -   *jco.destination.repository\_roundtrip\_optimization*

        > ### Note:  
        > Set the value to `0` that helps you to minimizes the number of roundtrip calls made to the server


    > ### Note:  
    > -   If you’re using principal propagation for authentication, for the property *jco.destination.auth\_type*, specify the value as `PrincipalPropagation`. Don’t specify any additional credentials in the destination.
    > 
    > -   *Location ID* should correspond to the cloud connector name found in the master instance.

6.  Verify and save the destination, and do a connection check.

    To know more about creating and configuring connectivity destinations, see [Create and Delete Destinations on the Cloud](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/94dddf7d9e56401ba1719b7e836d8ee9.html).


