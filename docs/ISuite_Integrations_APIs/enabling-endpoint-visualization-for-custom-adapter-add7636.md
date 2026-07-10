<!-- loioadd76368f1a0484c8da96b44dbec10b3 -->

# Enabling Endpoint Visualization for Custom Adapter

Configure a custom adapter with endpoint visualization to view the adapter endpoint URL.

The following sections describe the guidelines that you need to understand and follow:



<a name="loioadd76368f1a0484c8da96b44dbec10b3__section_nrh_4xt_vdb"/>

## Adding Libraries

You can find the latest ADK API in the [Adapter Development Kit](https://tools.hana.ondemand.com/#cloudintegration) section. After downloading the `*.zip` files, add the following libraries to the *src* \> *main* \> *resources* folder that is in your ADK project:

-   `com.sap.it.public.adapter.api.jar`

-   `com.sap.it.public.generic.api.jar`

For successful code compilation, right-click the `*.jar` file and choose *Build Path* \> *Add to Build Path* to add the jar files to the `Referenced Libraries` of the adapter project.



<a name="loioadd76368f1a0484c8da96b44dbec10b3__section_vpb_yyt_vdb"/>

## Adding Dependencies

Open the `pom.xml` file and add the dependencies shown here:

> ### Source Code:  
> ```xml
> <dependency>
> <groupId>com.sap.it.public</groupId>
> <artifactId>adapter.api</artifactId>
> <version>...</version>
> <scope>system</scope>
> <systemPath>${project.basedir}/src/main/resources/adapter.api.<version of the downloaded file>.jar</systemPath>
> </dependency>
> <dependency>
> <groupId>com.sap.it.public</groupId>
> <artifactId>generic.api</artifactId>
> <version>...</version>
> <scope>system</scope>
> <systemPath>${project.basedir}/src/main/resources/generic.api.<version of the downloaded file>.jar</systemPath>
> </dependency>
> ```

> ### Note:  
> Make sure that you use the latest version of the `*.jar` files.

After adding the dependency, add the `com.sap.it.public` group ID to the `<excludeGroupIds>` tag.



<a name="loioadd76368f1a0484c8da96b44dbec10b3__section_llt_p15_vdb"/>

## Adding Endpoint Information Service

You must create a **Class** and use the following method to retrieve the list of all endpoints for all integration flows:

> ### Source Code:  
> ```java
> import java.util.List;
> 
> import com.sap.it.api.adapter.monitoring.AdapterEndpointInformation;
> import com.sap.it.api.adapter.monitoring.AdapterEndpointInformationService;
> 
> public class AdapterEndpointInfo implements AdapterEndpointInformationService{
> 	/**
>      * Gets the list of all endpoints for all IntegrationFlows used by the
>      * adapter
>      * 
>      * @return the list of endpoints
>      */
> 	@Override
> 	public List<AdapterEndpointInformation> getAdapterEndpointInformation() {
> 		// TODO Auto-generated method stub
> 		return null;
> 	}
> 
> 	@Override
> 	public List<AdapterEndpointInformation> getAdapterEndpointInformationByIFlow(String arg0) {
> 		// TODO Auto-generated method stub
> 		return null;
> 	}
> 
> }
> 
> ```

The service implementation must contain the following method, which supports the retrieval of all endpoints exposed across all integration flows:

> ### Source Code:  
> ```java
> package com.sap.it.api.adapter.monitoring;
> 
> import java.util.List;
> 
> /**
>  * Interface, which adapter developers have to implement to return the endpoints
>  * (URLs) used by their adapter
>  */
> public interface AdapterEndpointInformationService {
> 
>     /**
>      * Gets the list of all endpoints for all IntegrationFlows used by the
>      * adapter
>      * 
>      * @return the list of endpoints
>      */
>     public List<AdapterEndpointInformation> getAdapterEndpointInformationList();
> 
>     /**
>      * Gets the list of endpoints for a given IntegrationFlow. If the given
>      * Integration Flows does not use the adapter, it has to return an empty
>      * instance list.
>      * 
>      * @param integrationFlowId
>      *            the id (bundle symbolic name) of the Integration Flow
>      * @return the endpoint information for the given Integration Flow
>      */
>     public AdapterEndpointInformation getAdapterEndpointInformation(String integrationFlowId);
> }
> ```

The class describing the **adapter endpoint information** is mentioned here:

> ### Source Code:  
> ```java
> 
>    package com.sap.it.api.adapter.monitoring;
> 
> import java.util.List;
> 
> /**
>  * Class representing endpoint information for an Integration Flow
>  *
>  */
> public class AdapterEndpointInformation {
> 	[..]
> 	
>     /**
>      * Get the endpoint instance list for this Integration Flow.
>      * 
>      * @return the endpoint instance list
>      */
>     public List<AdapterEndpointInstance> getAdapterEndpointInstanceList()
> 	[..]
> 
>     /**
>      * Set the endpoint instance list for this object.
>      * 
>      * @param adapterEndpointInstanceList
>      *            the endpoint instance list
>      */
>     public void setAdapterEndpointInstanceList(List<AdapterEndpointInstance> adapterEndpointInstanceList)
> 	[..]
> 
>     /**
>      * 
>      * @return the integration flow id (bundle symbolic name)
>      */
>     public String getIntegrationFlowId()
> 	[..]
> 
>     /**
>      * sets the integration flow id
>      * 
>      * @param integrationFlowId
>      *            the integration flow id (bundle symbolic name)
>      */
>     public void setIntegrationFlowId(String integrationFlowId)
> 	[..]
> } 
> ```

The class describing the **adapter endpoint instance** is mentioned here:

> ### Source Code:  
> ```java
> 
>    package com.sap.it.api.adapter.monitoring;
> 
> /**
>  * The endpoint instance consists of an <code>endpointCategory</code> which
>  * describes the kind of endpoint and an URL relative to the worker node. It is
>  * mainly about the distinction between endpoints to which messages can be sent
>  * and API definition endpoints from which metadata about the API can be
>  * retrieved.<br/>
>  * The consumer of the API is responsible for retrieving the correct dispatcher
>  * URL for the worker node (group) on which the Integration Flow is
>  * deployed.<br/>
>  * There is also an optional attribute available to provide additional info
>  * about the character of the endpoint in case the category is not sufficient.
>  * For CXF based endpoints, the WSDL download is offered in several flavors, for
>  * instance, so the adapter can provide this information in that attribute.
>  */
> public class AdapterEndpointInstance {
> 	[..]
> 
>     /**
>      * instantiates the object
>      * 
>      * @param endpointCategory
>      *            the endpoints category, see also {@link EndpointCategory}.
>      * @param relativeEndpointUrl
>      *            the URL relative to the worker nodes dispatcher URI starting
>      *            with a forward slash ('/')
>      */
>     public AdapterEndpointInstance(EndpointCategory endpointCategory, String relativeEndpointUrl)
> 	[..]
> 
>     /**
>      * instantiates the object
>      * 
>      * @param endpointCategory
>      *            the endpoints category, see also {@link EndpointCategory}.
>      * @param relativeEndpointUrl
>      *            the URL relative to the worker nodes dispatcher URI starting
>      *            with a forward slash ('/')
>      * @param additionalInfo
>      *            additional information (optional) in order to provide more
>      *            information if the category is not self explanatory. For example, in
>      *            case the WSDLs are offered in different flavors for different
>      *            consumers
>      */
>     public AdapterEndpointInstance(EndpointCategory endpointCategory, String relativeEndpointUrl, String additionalInfo)
> 	[..]
>     /**
>      * 
>      * @return the endpoints category
>      */
>     public EndpointCategory getEndpointCategory()
> 	[..]
> 	
>     /**
>      * 
>      * @return the URL relative to the worker nodes dispatcher URI starting with
>      *         a forward slash ('/')
>      */
>     public String getRelativeEndpointUrl()
> 	[..]
> 	
>     /**
>      * 
>      * @return additional information (optional) in order to provide more
>      *         information if the category is not self explanatory. For example, in case
>      *         the WSDLs are offered in different flavors for different
>      *         consumers. Can be null
>      */
>     public String getAdditionalInfo()
> 	[..]
> } 
> ```

The `EndpointCategory` can have the following values:

> ### Source Code:  
> ```
> package com.sap.it.api.adapter.monitoring;
> 
> public enum EndpointCategory {
>     ENTRY_POINT, DEFINITION_OAS_JSON, DEFINITION_OAS_YAML, DEFINITION_RAML_JSON, DEFINITION_RAML_YAML, DEFINITION_WSDL, DEFINITION_EDMX
> }
> 
> ```



<a name="loioadd76368f1a0484c8da96b44dbec10b3__section_ccw_m4t_xdb"/>

## Binding the Service with the Implementation

Next, you link the implementation to the service by creating a `beans.xml` file in the `src/main/resources/OSGI-INF/blueprint/` path and adding the following snippet:

> ### Source Code:  
> ```
> <blueprint xmlns="http://www.osgi.org/xmlns/blueprint/v1.0.0"
> 	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
> 	xsi:schemaLocation="http://www.osgi.org/xmlns/blueprint/v1.0.0 http://www.osgi.org/xmlns/blueprint/v1.0.0/blueprint.xsd">
> 	<bean id="iAdapterEndpointInformationService" class="<add the implementation class path>"
> 		activation="eager"></bean>
> 	<service id="IAdapterEndpointInformationService" ref="iAdapterEndpointInformationService"
> 		interface="com.sap.it.api.adapter.monitoring.AdapterEndpointInformationService">
> 	</service>
> </blueprint>
> ```

To support the binding snippet, add the following dependency in the `pom.xml` file:

> ### Source Code:  
> ```
> <dependency>
> <artifactId>camel-blueprint</artifactId>
> <groupId>org.apache.camel</groupId>
> <version>${camel.version}</version>
> </dependency>
> ```



<a name="loioadd76368f1a0484c8da96b44dbec10b3__section_b2z_5xr_wdb"/>

## Updating the Dependency to Export the Service

Ensure that the following dependency version is always greater than or equal to **1.25.0.** to export this service from your subsystem.

> ### Source Code:  
> ```
> <dependency>
> <groupId>com.sap.cloud.adk</groupId>
> <artifactId>com.sap.cloud.adk.build.archive</artifactId>
> <version>1.25.0</version>
> </dependency>
> ```



<a name="loioadd76368f1a0484c8da96b44dbec10b3__section_sl4_21s_wdb"/>

## Deploying the Adapter

After completing the process, deploy the adapter and use the Cloud Integration Web application to consume the adapter in an integration flow. Now, go to the *Manage Integration Content* section to verify the endpoint information.

**Related Information**  


[Endpoint Visualization](endpoint-visualization-6c3fb22.md "You can visualize the adapter endpoints in the Manage Integration Content section.")

