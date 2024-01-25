<!-- loio503a3aa8d9b142629a709d8860443431 -->

# Configuring Load Balancing

You can configure load-balancing functionality for an API proxy from the API Management, API Portal.



## Procedure

1.  Log on to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Design* \> *APIs*.

    A list of APIs appears in the catalog.

3.  Browse for an API proxy, which is already linked to an API provider.

4.  Choose the slide button to enable the *Load-Balancing* functionality.

5.  Select additional API providers from the *API Provider* dropdown menu.

    The *FallBack Server* field appears once the additional API providers are selected.

    Select one of the additional API providers as the *FallBack Server* from the dropdown menu.

    When the load balancer determines that the additional API providers are unavailable, all traffic is routed to the fallback server.

6.  Choose the slide button to enable *Retry*.

    If retry is enabled, a request is sent again whenever a response failure occurs, for example I/O error, or HTTP timeout. A request is also sent whenever the response received matches a value set by the Response Code.

7.  By default *Round Robin* algorithm is selected. But you can also select *Weighted* and *Least Connection* algorithms.

    The **Round Robin** algorithm forwards a request to each API provider in the order in which the API providers are listed in the target endpoint HTTP connection.

    The **Weighted** load-balancing algorithm enables you to configure proportional traffic loads for your API providers. The weighted load-balancer distributes request to your API providers in direct proportion to each API provider's weight. Therefore, the weighted algorithm requires you to set a weight attribute for each API provider.

    You can also configure the load-balancer to use the *Least Connection* algorithm. This algorithm routes outbound requests to the API providers with fewest open HTTP connections.

8.  Choose the slide button to enable *Maximum Failure*.

    When enabled, it checks for the number of failed requests from the API proxy to the API provider that results in the request being redirected to another API provider.

    *Maximum Failure Value*: Enter the maximum number of failed requests from the API proxy to the API provider. Set the maximum failure value greater than 0 when using the Health Monitor. When the value is configured as 0, the Load Balancer tries to connect to the API provider for each request and never removes the API provider from the rotation.

    > ### Note:  
    > The provider is removed from load balancer configuration, if the maximum number of failed requests is reached.

    *Response Code*: Enter the HTTP response codes that are expected to be received from the polled API providers.

9.  Choose *Save*.




<a name="loio503a3aa8d9b142629a709d8860443431__result_phc_t53_x4b"/>

## Results

You have configured load balancing for the API proxy.

**Related Information**  


[Configure Load Balancing During Import](configure-load-balancing-during-import-2cd47e2.md "You can apply load-balancing functionality to an API proxy, by including the load balancer, and health monitor attributes in a .zip file along with the API proxy content.")

