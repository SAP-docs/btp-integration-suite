<!-- loioc94b8902d3104d51b897a0312e8d05a2 -->

# Accessing On-Premise Application using Cloud Connector

Follow the steps here to extend the connectivity of Cloud Integration with remote on-premise application.



<a name="loioc94b8902d3104d51b897a0312e8d05a2__prereq_jgn_1ds_c5b"/>

## Prerequisites

You must have the access to Public APIs. For more information, see [SDK API](sdk-api-c5c7933.md).



<a name="loioc94b8902d3104d51b897a0312e8d05a2__context_nb4_rrq_mjb"/>

## Context

You can prepare an Adapter Development Kit \(ADK\) project to access any on-premise application using Cloud Connector.



## Procedure

1.  Depending on your requirements, add the code below to either the `*Producer.java` \(receiver adapter\) or `*Consumer.java` \(sender adapter\) file. This is for connecting to on-premise application.

    1.  For HTTP

        > ### Source Code:  
        > Use the below code to fetch the proxy details and additional headers.
        > 
        > ```java
        > CloudConnectorContext context = new CloudConnectorContext();
        > context.setConnectionType(ConnectionType.HTTP);
        > CloudConnectorProperties props = ITApiFactory.getService(CloudConnectorProperties.class, context);
        > String proxyHost = props.getProxyHost();
        > String proxyPort = props.getProxyPort();
        > Map<String, String> additionalHeaders = props.getAdditionalHeaders();
        > ```

        Add the following import declarations:

        > ### Source Code:  
        > ```java
        > import com.sap.it.api.ITApiFactory;
        > import com.sap.it.api.ccs.adapter.CloudConnectorContext;
        > import com.sap.it.api.ccs.adapter.CloudConnectorProperties;
        > import com.sap.it.api.ccs.adapter.ConnectionType;
        > 
        > ```

        > ### Sample Code:  
        > The example here shows how you can use the above proxy details in HTTP client. Ensure to provide the location ID of the Cloud Connector using the header `SAP-Connectivity-SCC-Location_ID`.
        > 
        > ```java
        > DefaultHttpClient httpclient = new DefaultHttpClient();
        > HttpGet httpGet = new HttpGet(address);
        > HttpHost proxy = new HttpHost(proxyHost, proxyPort);
        > httpclient.getParams().setParameter(ConnRoutePNames.DEFAULT_PROXY, proxy);
        > httpGet.setHeader("SAP-Connectivity-SCC-Location_ID", locationId);
        > if (additionalHeaders != null && !additionalHeaders.isEmpty()) {
        > 	for (Entry<String, String> header : additionalHeaders.entrySet()) {
        >      	httpGet.setHeader(header.getKey(), header.getValue());
        > 	}
        > }
        > HttpResponse response = httpclient.execute(httpGet);
        >  
        > ```

    2.  For TCP

        > ### Source Code:  
        > Depending on the environment type there are two types of proxy authentication; via JWT access token and via Username and password. The simplest way to determine the type to be used is to look at cloud connector properties.
        > 
        > ```java
        > CloudConnectorContext context = new CloudConnectorContext();
        > context.setConnectionType(ConnectionType.TCP);
        >  
        > CloudConnectorProperties cloudConnectorProperties = ITApiFactory.getService(CloudConnectorProperties.class, context);
        > AuthType authType = cloudConnectorProperties.getAuthType();
        > ```

        > ### Source Code:  
        > Proxy host and proxy port of the cloud connector can be accessed using the below API:
        > 
        > ```java
        > cloudConnectorProperties.getProxyPort();
        > cloudConnectorProperties.getProxyHost();
        > ```

        The following are intended to use with appropriate authentication methods only.

        > ### Source Code:  
        > For use with AuthType.PasswordAuthentication
        > 
        > ```java
        > cloudConnectorProperties.getUserName(locationId)
        > 									
        > ```

        For more information, see [Username Password Authentication](https://help.sap.com/docs/CP_CONNECTIVITY/b865ed651e414196b39f8922db2122c7/c2461c31761b488c828e15b71263f3fd.html?locale=en-US&version=Cloud) 

        > ### Source Code:  
        > For use with AuthType.JWTTokenAuthentication
        > 
        > ```java
        > cloudConnectorProperties.getJWTToken()
        > 										
        > ```

        For more information, see [JWT Access Token Authentication](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/cd1583775afa43f0bb9ec69d9dbcc880.html?locale=en-US&version=Cloud) 


2.  Save the changes.


