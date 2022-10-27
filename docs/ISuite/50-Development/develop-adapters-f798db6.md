<!-- loiof798db6491424460bb4b43d4a86ed1cf -->

# Develop Adapters

You can develop custom adapters using Adapter SDK in Cloud Integration.



## Prerequisites

> ### Note:  
> This procedure is deprecated. It is recommended to follow the procedure mentioned in [Develop Adapters Using Archetype](develop-adapters-using-archetype-0a84b13.md).

-   You are aware of the technical details of component/domain that you have to connect with Cloud Integration through the newly developed adapter type.

-   You have Java 8 version.

-   You are familiar with using Apache Camel and Java.

-   You have the Camel component and its dependencies as OSGi bundles.

-   You have the camel core runtime version 2.24.2.

-   You have the simple logging facade for java \(SLF4J\).

-   You must not use the temporary disk space to write files or store data. This helps to avoid **no disk space error** at runtime.




<a name="loiof798db6491424460bb4b43d4a86ed1cf__context_eh3_2vq_x1b"/>

## Context

You use an adapter in an integration flow for outbound and inbound communication with different applications during runtime. In such scenario if an adapter does not support your communication requirements you use SAP ADK framework to create an adapter and deploy it in an integration flow. Here we describe how to build and deploy an adapter during runtime.



## Procedure

1.  Install the Adapter SDK for Cloud Integration. For more information, see [Installation Instructions](https://tools.hana.ondemand.com/#hci).

2.  Open Eclipse.

3.  Create a new adapter project **\(with maven\)** using the following substeps:

    1.  Select *File* \> *New* \> *Project*.

    2.  Choose *SAP Cloud Integration* \> *Adapter Project* in the *New Project* wizard.

    3.  Choose *Next*.

    4.  Enter details in the *New Adapter Project* wizard.

        > ### Note:  
        > If you are entering value in *Version* field, then you must enter the major, minor and macro versions. Currently, the tool supports only 1.0.0 version, which is also the default value.

    5.  The *Enable Maven* is selected by default that identifies this project is of type Maven. You can change the component details as per your requirement.

        > ### Note:  
        > Deselect the *Enable Maven* option if you do not want to create a non-maven based custom adapter.

    6.  Choose *Finish* to create a custom project.

    7.  The following table describes different components created for the custom adapter project using maven:

        > ### Note:  
        > The advantage here is that you can develop UI and runtime components.


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
        > You can update to the latest ADK version by manually changing the version in `com.sap.cloud.adk.build.archive` artifact found in the `pom.xml` file. Refer the central maven repository to get the latest ADK version.

    8.  To run maven clean install right click-on the project, choose *Run As* \> *Maven Build*.

    9.  In the *Goals* field, type ***clean install*** and *Run* the project.

        > ### Note:  
        > To deploy the adapter project right click-on the adapter project, and choose *Deploy Adapter Project*.


4.  Create a new adapter project **\(without maven\)** using the following substeps:

    1.  Select *File* \> *New* \> *Project*.

    2.  Choose *SAP Cloud Integration* \> *Adapter Project*in the *New Project* wizard.

    3.  Choose *Next*.

    4.  Enter details in the *New Adapter Project* wizard.

        > ### Note:  
        > If you are entering value in *Version* field, then you must enter the major, minor and macro versions. Currently, the tool supports only 1.0.0 version, which is also the default value.

    5.  Deselect the *Enable Maven* option if you do not want to build a custom adapter with maven.

    6.  Choose *Finish* to create the custom project.

    7.  Develop camel component.

        > ### Note:  
        > *createProducer\(\)* or *createConsumer\(\)* method, will throw *UnsupportedOperationException*, *RuntimeCamelException*, *OperationNotSupportedException* exceptions. You can prevent the generation of producer or consumer components by throwing *UnsupportedOperationException* exception.

    8.  Add one \(mandatory\) camel component `.jar` file in `component` folder and other additional \(optional\) dependent `.jar` files in `libs` folder.

        > ### Note:  
        > You must add only those jar files that are valid OSGi bundles. Component jar is a camel based component bundle. Dependent jars are the osgi bundles that are required by camel component.

    9.  Adapt the component metadata file according to the requirements of the new adapter type.


5.  Right click on the new adapter project or the component folder and select *Generate Metadata* \> *Component Metadata* to generate a sample component metadata.

    > ### Note:  
    > Generate component metadata works only if annotations are marked in the camel bundle on endpoint class variables.
    > 
    > **Annotations**:
    > 
    > @Required : used to make the field mandatory and belongs to the package org.apache.camel.spi.Required
    > 
    > **For example**: @UriParam
    > 
    > @Required
    > 
    > private String testField;
    > 
    > Attribute behavior is set as *SecureAlias* if the variable name has ***password***, ***key***, ***secret*** or ***token*** keywords.

    Follow the substeps to introduce custom classes using blueprint metadata that allows you to extend the runtime capabilities of the adapter:

    1.  Right click-on the new adapter project or the component folder and select*Generate Metadata* \> *Blueprint Metadata* to generate a sample blueprint metadata.

    2.  Update the ***<ReferencedComponents\>*** tag in `metadata.xml` to provide a reference to `bpMetadata.xml`.

        > ### Note:  
        > The value provided here is variant specific, for multiple variants fetch appropriate URL and update the `metadata.xml` in the matching variant. For example, a variant can be either Receiver or Sender.


6.  You can define the following additional property values in `metadata.xml` file, for retrieving specific information on an adapter during runtime.


    <table>
    <tr>
    <th valign="top">

    Value


    
    </th>
    <th valign="top">

    Data Type


    
    </th>
    <th valign="top">

    Endpoint Variable and Setter


    
    </th>
    <th valign="top">

    Refers to...


    
    </th>
    </tr>
    <tr>
    <td valign="top">

     ***adapterInstanceID*** 


    
    </td>
    <td valign="top">

    String


    
    </td>
    <td valign="top">

     ***adapterInstanceID\(string\)*** 


    
    </td>
    <td valign="top">

    Participant ID, which helps to identify log error details.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

     ***adapterVersion*** 


    
    </td>
    <td valign="top">

    String


    
    </td>
    <td valign="top">

     ***adapterVersion\(string\)*** 


    
    </td>
    <td valign="top">

    The adapter version.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

     ***projectID*** 


    
    </td>
    <td valign="top">

    String


    
    </td>
    <td valign="top">

     ***projectID\(string\)*** 


    
    </td>
    <td valign="top">

    The integration flow project ID.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

     ***userDefinedNamespaces*** 


    
    </td>
    <td valign="top">

    Java.util.Map


    
    </td>
    <td valign="top">

     ***userDefinedNamespaces\(map<string,string\>\)*** 


    
    </td>
    <td valign="top">

    A namespace mapping generated at runtime for an integration flow model. It contains a namespace-prefix pair with a format ***xmlns:<prefix\>=<namespace\>*** .


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Use the ***<AdditionalMetadata\>*** attribute, to include additional properties in the URI. You must place the attribute as an immediate child of any variant in the metadata file.
    > 
    > > ### Sample Code:  
    > > ```
    > > <Metadata>
    > >               <AdditionalMetadata>
    > >                     <Name>requiredIntegrationFlowProperties</Name>
    > >                     <Value>adapterInstanceID,  adapterVersion  , projectID, userDefinedNamespaces </Value>
    > >                     <GuiLabels>
    > >                         <Label language="en"/>
    > >                     </GuiLabels>
    > >               </AdditionalMetadata>
    > >     </Metadata>
    > > ```

7.  If you want to verify if the adapter project has valid contents such as component metadata in metadata folder and jar files in the libs and component folder, right click on the project and choose *Execute Checks*.

8.  If you want to build your project locally, right click-on the project and choose *Deploy Adapter Project*.

    > ### Note:  
    > Once you build locally, the system creates *target.build* directory, where you can find a new adapter runtime archive.

9.  To configure the Operations Server to connect your local Eclipse tooling to the tenant, execute the following substeps:

    1.  Select *Window* \> *Preferences* \> *SAP Cloud Integration* \> *Operations Server*.

    2.  Enter the server URL.

    3.  Enter your user and password.


10. Deploy the adapter project.

    > ### Note:  
    > IFL worker node does not support ADK.

11. Check the status of your deployed project by executing the following substeps:

    1.  In *Node Explorer*, choose worker node.

        > ### Note:  
        > You can construct an application URL in the following format ***https://<IFLMAP URL\>/<web context path\>/*** to call the servlet.

    2.  Select the *Component Status View* tab and check the status of the adapter project.

        > ### Note:  
        > -   If you do not delete an adapter but some other user deletes the adapter and still the metadata is available in integration flow, then you must restart the system.
        > -   You must undeploy the integration flows using the relevant adapter before undeploying adapter.


    > ### Note:  
    > You can implement logging in ADK framework by using Simple Logging Facade for Java \(SLF4J\) API package. Use the following maven coordinates in component bundle:
    > 
    > > ### Sample Code:  
    > > ```
    > > <dependency>
    > >       <groupId>org.slf4j</groupId>
    > >       <artifactId>slf4j-api</artifactId>
    > >       <version>[1.0,)</version>
    > > </dependency>
    > > 
    > > ```
    > 
    > Based on the log level configuration the log is visible only in the tail log.


**Related Information**  


[Component Metadata](component-metadata-550b19e.md "Component metadata specifies the attributes of sender and receiver adapters used to define the UI. Each tab can contain multiple attributes. You can group the attributes into multiple attribute groups within the tabs. You can use the same attribute across the sender and receiver adapters by using attribute reference.")

[Blueprint Metadata](blueprint-metadata-ab38cc8.md "")

