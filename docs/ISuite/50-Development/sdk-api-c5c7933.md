<!-- loioc5c7933b77ba46dbaa9a2c1576dbb381 -->

# SDK API

SDK APIs refer to the overall set of APIs like the Generic API, Adapter API, Script API.

Application programming interfaces \(APIs\) are available for the following use cases:

-   Using a programming language \(Java Script or Groovy\), you can control how a message is being processed on a tenant.

-   Using an API, you can build your own custom adapter in the context of the Adapter Development Kit.


> ### Note:  
> The Java standard libraries of Java 8 can be used.
> 
> Cloud Integration supports the XML Document Object Model \(DOM\) to process XML documents.
> 
> You can implement logging by using Simple Logging Façade for Java \(SLF4J\) API package. We recommend using SLF4J framework over using your own logging frameworks.



<a name="loioc5c7933b77ba46dbaa9a2c1576dbb381__section_fj3_crs_1tb"/>

## Public APIs in Maven Central Repository

Some of the public APIs are available in the Maven Central Repository. Look out for the specific APIs with their associated coordinates. Also, for detailed information about these APIs, refer to their corresponding JavaDocs mentioned in the next paragraphs.



<a name="loioc5c7933b77ba46dbaa9a2c1576dbb381__section_skh_g4j_rvb"/>

## Adapter API

Use Adapter APIs if you want to develop custom adapters.

To access the Adapter API from Maven Central Repository, do the following steps:

1.  Look out for the latest public API in Maven Central Repository. The group ID is `com.sap.cloud.adk` and artifact ID is `adapter.api`.

2.  Add the maven dependency for the API in your adapter pom file. For example, the sample that follows is a way to consume the adapter API.

    > ### Sample Code:  
    > ```
    > 
    > 
    > <dependency>
    > 	<groupId>com.sap.cloud.adk</groupId>
    > 		<artifactId>adapter.api</artifactId>
    > 		<version>XX.YY.ZZ</version>
    > 		<!-- replace XX.YY.ZZ with the latest version -->
    > </dependency>
    > 
    > 
    > ```

3.  Add `com.sap.cloud.adk` to the `excludeGroupIds` section in the *Configuration Settings* of the *Maven Dependency Plugin*. For example:

    > ### Sample Code:  
    > ```
    > <excludeGroupIds>com.sap.cloud.adk,org.apache.camel,org.slf4j,log4j</excludeGroupIds>
    > ```


The [javadoc for Adapter API](https://help.sap.com/doc/11615149a5364a279cb901903794a3f8/Cloud/en-US/index.html) contains the complete set of packages and classes.

> ### Note:  
> On how to consume cluster lock feature from the package, see [Component Metadata](component-metadata-550b19e.md).



<a name="loioc5c7933b77ba46dbaa9a2c1576dbb381__section_jqf_h4j_rvb"/>

## Script API

Use the Script APIs if you want to use the Script step in your integration flow.

Look out for the latest public API in Maven Central Repository. Use the maven coordinates that follow in your project to consume the script API.

> ### Sample Code:  
> ```
> 
> 
> <dependency>
> 	<groupId>com.sap.cloud.script</groupId>
> 		<artifactId>script.api</artifactId>
> 		<version>XX.YY.ZZ</version>
> 		<!-- replace XX.YY.ZZ with the latest version -->
> </dependency>
> 
> 
> ```

The [javadoc for Script API](https://help.sap.com/doc/a56f52e1a58e4e2bac7f7adbf45b2e26/Cloud/en-US/index.html) contains the complete set of packages and classes.



<a name="loioc5c7933b77ba46dbaa9a2c1576dbb381__section_uyc_h4j_rvb"/>

## Generic API

Generic APIs are common for Script step and developing custom adapters.

To access the Generic API from Maven Central Repository, do the following steps:

1.  Look out for the latest public API in Maven Central Repository. The group ID is `com.sap.cloud.adk` and artifact ID is `generic.api`.

2.  Add the maven dependency for the API in your adapter pom file. For example, the sample that follows is a way to consume the generic API.

    > ### Sample Code:  
    > ```
    > 
    > 
    > <dependency>
    > 	<groupId>com.sap.cloud.adk</groupId>
    > 		<artifactId>generic.api</artifactId>
    > 		<version>XX.YY.ZZ</version>
    > 		<!-- replace XX.YY.ZZ with the latest version -->
    > </dependency>
    > 
    > 
    > ```

3.  Add `com.sap.cloud.adk` to the `excludeGroupIds` section in the *Configuration Settings* of the *Maven Dependency Plugin*. For example:

    > ### Sample Code:  
    > ```
    > <excludeGroupIds>com.sap.cloud.adk,org.apache.camel,org.slf4j,log4j</excludeGroupIds>
    > ```


The [javadoc for Generic API](https://help.sap.com/doc/471310fc71c94c2d913884e2ff1b4039/Cloud/en-US/index.html) contains the complete set of packages and classes.



<a name="loioc5c7933b77ba46dbaa9a2c1576dbb381__section_hwg_vqs_1tb"/>

## Mapping API

The [javadoc for Mapping API](https://help.sap.com/doc/d47441d304c14a0ab9d3986c1b553a1e/Cloud/en-US/index.html) contains the complete set of packages and classes.

**Related Information**  


[Developing Custom Adapters](developing-custom-adapters-7392cc4.md "Develop adapters tailored for your specific requirements.")

