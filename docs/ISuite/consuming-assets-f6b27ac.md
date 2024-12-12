<!-- loiof6b27ac5837349cfab087d6f399602b1 -->

# Consuming Assets

You've successfully negotiated the usage of a provider's asset, and you've triggered the transfer process. Now, you can consume the chosen asset.



<a name="loiof6b27ac5837349cfab087d6f399602b1__prereq_lvb_njd_2zb"/>

## Prerequisites

You've completed the steps described in [Triggering Contract Negotiations and Transferring Assets with EDR Management APIs](triggering-contract-negotiations-and-transferring-assets-with-edr-management-apis-eace95e.md).



## Context

This topic describes the recommended process for consuming an asset.



## Procedure

1.  Confirm that the transfer process has reached the status **COMPLETED.**

2.  Call the provider data plane and retrieve the asset. To do so, perform a GET call against the data plane URL, with the corresponding credentials provided by the provider in the endpoint data reference \(EDR\) package.

    This EDR is sent to your defined callback URL and allows you to consume your selected asset.

    > ### Note:  
    > Only HTTPS connections are supported. If the asset provider relies on HTTP connections to provide assets, the data transfer is disrupted due to security concerns.

    The following is an example EDR:

    > ### Sample Code:  
    > ```
    > {
    >     "id":"<asset ID>",
    >     "endpoint":"<data plane URL>",
    >     "authKey":"<authKey>",
    >     "authCode":"<authCode>",
    >     "properties":{
    >     }
    > }
    > ```


