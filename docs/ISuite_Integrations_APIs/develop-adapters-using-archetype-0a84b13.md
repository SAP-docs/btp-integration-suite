<!-- loio0a84b13390ba45068f75578bbce3a08a -->

# Develop Adapters Using Archetype

You can develop custom adapters using Adapter SDK in Cloud Integration.



<a name="loio0a84b13390ba45068f75578bbce3a08a__prereq_dsf_cky_csb"/>

## Prerequisites

-   You are aware of the technical details of component/domain that you have to connect withCloud Integration through the newly developed adapter type.

-   You have Java 8 version.
-   You are familiar with using Apache Camel and Java.
-   You have the Camel component and its dependencies as OSGi bundles.
-   You have the camel core runtime version 3.14.
-   You have the simple logging facade for java \(SLF4J\).



## Context

You use an adapter in an integration flow for outbound and inbound communication with different applications during runtime. In such scenario if an adapter does not support your communication requirements you use SAP ADK framework to create an adapter and deploy it in an integration flow. .

There are two types of adapter project template to create a new adapter project:

-   *Adapter Project*

    Use this template when you have a requirement to create a new SAP adapter and a new Camel component or customize an existing runtime component.

-   *Component reuse Adapter Project*

    Use this template if you want to re-use an existing runtime component without any customization.


Here we describe how to build and deploy an adapter during runtime using these two templates.



## Procedure

1.  *Adapter Project Template*

    1.  Use any IDE for creating a project from the archetype or use the generate command and enter the following:

        Use the below maven archetype artifacts:

        `com.sap.cloud.adk:com.sap.cloud.adk.archetype-adapter`

        Refer to the central maven to obtain the latest version number.

        > ### Sample Code:  
        > ```
        > 
        > mvn archetype:generate -B -DarchetypeGroupId=com.sap.cloud.adk \
        >  -DarchetypeArtifactId=com.sap.cloud.adk.archetype-adapter \
        >  -DarchetypeVersion=1.0.1 \
        >  -DcomponentName=SampleComponentName \
        >  -DadapterName=AdapterName \
        >  -DadapterId=AdapterNameId \
        >  -DadapterVendor=VendorName \
        >  -DadapterVersion=1.0.0 \
        >  -Dscheme=scheme \
        >  -DgroupId=project.group \
        >  -DartifactId=project.artifact \
        >  -Dversion=1.0-SNAPSHOT
        > ```

        **Component Description**


        <table>
        <tr>
        <th valign="top">

        Component
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        `archetypeGroupId`

        `archetypeArtifactId`

        `archetypeVersion`
        
        </td>
        <td valign="top">
        
        Artifacts of maven archetype
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `componentName`

        `scheme`
        
        </td>
        <td valign="top">
        
        Artifacts of your runtime component

        `componentName` is the name of your camel component.

        `scheme` is the scheme name of the component.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `adapterName`

        `adapterId`

        `adapterVendor`

        `adapterVersion`
        
        </td>
        <td valign="top">
        
        Artifacts of your integration adapter
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `groupId`

        `artifactId`

        `version`
        
        </td>
        <td valign="top">
        
        Artifacts of your maven project
        
        </td>
        </tr>
        </table>
        
    2.  The following table describes different components created for the custom adapter project using maven:


        <table>
        <tr>
        <th valign="top">

        Component
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        `*Component.java`
        
        </td>
        <td valign="top">
        
        Sample runtime component.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `*Consumer.java`
        
        </td>
        <td valign="top">
        
        Sample sender component.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `*Endpoint.java`
        
        </td>
        <td valign="top">
        
        Logger information is found.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `*Producer.java`
        
        </td>
        <td valign="top">
        
        Sample receiver component.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `metadata.xml`
        
        </td>
        <td valign="top">
        
        UI values are coded here.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `*ComponentTest.java`
        
        </td>
        <td valign="top">
        
        Sample JUnit test
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `pom.xml`
        
        </td>
        <td valign="top">
        
        Contains configuration details and dependencies.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `*config.adk`
        
        </td>
        <td valign="top">
        
        Contains the adapter configuration parameters.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `sap-sample`
        
        </td>
        <td valign="top">
        
        Represents the endpoint scheme.

        > ### Note:  
        > If you deploy multiple adapters make sure the filenames are unique. When you change the filename do the following:
        > 
        > -   In the endpoint class, change scheme value. For example, `@UriEndpoint(scheme = "sap-sample", syntax = "", title = "")`.
        > 
        > -   In `metadata.xml` change the attribute value. For example, `gen:RuntimeComponentBaseUri="sap-sample"`.


        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > You can update to the latest ADK version by manually changing the version in com.sap.cloud.adk.build.archive artifact found in the pom.xml file. Refer the central maven repository to get the latest ADK version.


2.  *Component reuse Adapter Project Template*

    1.  Use any IDE for creating a project from the archetype or use the generate command and enter the following:

        Use the below maven archetype artifacts:

        `com.sap.cloud.adk:com.sap.cloud.adk.archetype-adapter-component-reuse`

        Refer to the central maven to obtain the latest version number.

        > ### Note:  
        > You can reuse an existing camel component in your adapter project using this template.

        > ### Sample Code:  
        > ```
        > 
        > mvn archetype:generate -B -DarchetypeGroupId=com.sap.cloud.adk \
        >  -DarchetypeArtifactId=com.sap.cloud.adk.archetype-adapter-component-reuse \
        >  -DarchetypeVersion=1.0.1 \
        >  -DadapterName=AdapterName \
        >  -DadapterId=AdapterNameId \
        >  -DadapterVendor=VendorName \
        >  -DadapterVersion=1.0.0 \
        >  -DgroupId=project.group \
        >  -DartifactId=project.reuse.artifact \
        >  -Dversion=1.0-SNAPSHOT
        > 
        > ```

        **Component Description**


        <table>
        <tr>
        <th valign="top">

        Component
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        `archetypeGroupId`

        `archetypeArtifactId`

        `archetypeVersion`
        
        </td>
        <td valign="top">
        
        Artifacts of maven archetype
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `adapterName`

        `adapterId`

        `adapterVendor`

        `adapterVersion`
        
        </td>
        <td valign="top">
        
        Artifacts of your integration adapter
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `groupId`

        `artifactId`

        `version`
        
        </td>
        <td valign="top">
        
        Artifacts of your maven project
        
        </td>
        </tr>
        </table>
        
    2.  The following table describes different components created for the custom adapter project using maven:


        <table>
        <tr>
        <th valign="top">

        Component
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        `component`
        
        </td>
        <td valign="top">
        
        A folder where runtime component JAR must be placed.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `libs`
        
        </td>
        <td valign="top">
        
        A folder where runtime component dependencies JARs must be placed.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `metadata`
        
        </td>
        <td valign="top">
        
        A folder where component and blueprint \(optional\) metadata will be generated.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `pom.xml`
        
        </td>
        <td valign="top">
        
        Contains configuration details and dependencies.
        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > You can update to the latest ADK version by manually changing the version in com.sap.cloud.adk.build.archive artifact found in the pom.xml file. Refer the central maven repository to get the latest ADK version.

    3.  Copy runtime component *JAR* into *component* folder and their dependencies into the *libs* folder.

3.  Run the command `mvn clean install` to build the adapter. This command will generate runtime component metadata and ESA with a component.

    Blueprint metadata is not generated by default with this command. To generate this metadata, refer the next step.

4.  Other maven goals that you can use are

    -   *Generate runtime component metadata*

        This will generate component metadata using the camel component.

        `mvn com.sap.cloud.adk:com.sap.cloud.adk.build.archive:generate-cmd`

    -   *Generate blueprint metadata*

        This will generate the blueprint metadata for custom generation.

        `mvn com.sap.cloud.adk:com.sap.cloud.adk.build.archive:generate-bmd`

    -   *Check adapter project*

        This is used explicitly for validation. This step is included by default in the project build step.

        `mvn com.sap.cloud.adk:com.sap.cloud.adk.build.archive:check`



