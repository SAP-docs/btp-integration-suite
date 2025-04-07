<!-- loio94057be5cf784617b104eaeab20e4fba -->

# Creating HTTP Destinations and Transport Route

Create destinations, transport nodes, and transport route to configure the content transport landscape.



<a name="loio94057be5cf784617b104eaeab20e4fba__prereq_g1d_cqb_jmb"/>

## Prerequisites

-   Complete the tasks mentioned in [Enabling Content Transport, Cloud Foundry Environment](enabling-content-transport-cloud-foundry-environment-452c677.md).

-   To use Cloud Transport Management as your transport option, complete the initial setup. See [Cloud Transport Management Setup](https://help.sap.com/docs/TRANSPORT_MANAGEMENT_SERVICE/7f7160ec0d8546c6b3eab72fb5ad6fd8/66fd7283c62f48adb23c56fb48c84a60.html).


<a name="topic_jw2_4pl_vvb"/>

<!-- topic\_jw2\_4pl\_vvb -->

## Creating HTTP Destinations for Cloud Transport Management

Create four HTTP destinations in the SAP BTP subaccount where your source SAP Integration Suite tenant is hosted. Later, create transport nodes and route in Cloud Transport Management.





### 

1.  Create a destination for Content Agent Service. See [Create SAP Content Agent Service Destination](https://help.sap.com/docs/CONTENT_AGENT_SERVICE/ae1a4f2d150d468d9ff56e13f9898e07/a4da0c26ced74bbfbc60e7f607dc05ab.html).

    > ### Note:  
    > Skip creating this destination if you want to use the Content Agent Service's web UI to trigger the transport.

2.  Create a destination for source SAP Integration Suite tenant. See [Create SAP Cloud Integration Destination](https://help.sap.com/docs/CONTENT_AGENT_SERVICE/ae1a4f2d150d468d9ff56e13f9898e07/c17c4004049d4d9dba373d72ce5610cd.html).

3.  Create a destination for Cloud Transport Management. See [Create Cloud Transport Management Destination](https://help.sap.com/docs/CONTENT_AGENT_SERVICE/ae1a4f2d150d468d9ff56e13f9898e07/eed66f35f9d148c8ae5b2d46ff097d8c.html).

4.  In Cloud Transport Management service, create the source and target transport nodes. The name for the source node must be the same as the property you defined in *sourceSystemId* of the destination created for Cloud Transport Management service in the previous step. See: [Create Transport Nodes](https://help.sap.com/docs/TRANSPORT_MANAGEMENT_SERVICE/7f7160ec0d8546c6b3eab72fb5ad6fd8/f71a4d5550cd453ea824d5b5c677969d.html).

5.  In Cloud Transport Management service, create a transport route using the preceding nodes. See: [Create Transport Routes](https://help.sap.com/docs/TRANSPORT_MANAGEMENT_SERVICE/7f7160ec0d8546c6b3eab72fb5ad6fd8/dddb74937a014aea8d3d76d740180597.html).

6.  Create a destination for Cloud Transport Management for the target SAP Integration Suite tenant. You use this destination in Cloud Transport Management to configure your transport landscape. See [Create Transport Destinations](https://help.sap.com/docs/cloud-transport-management/sap-cloud-transport-management/creating-destinations-using-sap-cloud-deployment-service-with-basic-authentication).


