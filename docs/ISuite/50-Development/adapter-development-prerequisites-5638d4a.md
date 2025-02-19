<!-- loio5638d4a57a7a45e8aac90b95cc3f8521 -->

# Adapter Development Prerequisites

You can contribute to an Apache Camel component as Cloud Integration adapter. To integrate camel component into Cloud Integration framework, specify the detailed set of adapter attributes as component metadata. Component metadata defines the adapter attributes, dependencies between them and the structure of configuration interface for a specific adapter, which is used for user interface generation.

Following are the guidelines that you need to understand and follow while developing camel component:

-   **Protocol and Exchange Headers** - While you are specifying the protocol headers as camel headers or vice-versa from your custom integration adapter, we strongly recommend to consider these rules for security reasons:

    -   Propagate only compliant headers or the headers required by adapter protocol.
    -   Camel-specific arbitrary headers should not be used. You may still propagate the headers compliant with the adapter protocol following a naming convention conforming to adapter protocol guidelines.
    -   Provide the configuration in the custom integration adapter to allow the non-compliant exchange headers to be propagated.
    -   Include the propagated headers in the adapter documentation.

-   **Camel Component Scheme** – Make sure that you use a unique camel component scheme to avoid runtime collisions with other registered schemes. For example, the camel component scheme can be sap-dropbox.

-   This is the new content.
-   **Secure Programming** – Store secure parameters in runtime secure store and accessed through alias configured in adapter.
-   **Security Aspects** –

    -   Always scan for virus in the Adapter workspace / project before deployment.
    -   The Adapter design time content bundle shouldn’t contain any confidential information \(For example: hard-coded secrets, passwords,users, or or documents\).
    -   Perform ftify and java static code checks.

-   **Logging** – Use Slf4j logging

-   **API Consumption** 

    -   To access platform-specific features, you can use public APIs that are available with the Adapter Development Kit \(ADK\). Public APIs for the ADK are available in Cloud Integration tools page.
    -   The two maven coordinates available in the central maven for Public API consumption are:

        `com.sap.cloud.adk:generic.api`

        `com.sap.cloud.adk:adapter.api`

        Refer the central maven repository to obtain the latest version number.

    -   To consume the APIs, you need to use the code snippet `ITApiFactory.getApi(apiType, context);` wherein, apiType is the class of the requested API interface. The camel context can be null if it isn’t required for a particular API. For Example: For accessing KeystoreService, use ITApiFactory.getApi\(KeystoreService.class, context\)

    > ### Note:  
    > The Java standard libraries of Java 8 can be used.
    > 
    > Cloud Integration supports the XML Document Object Model \(DOM\) to process XML documents.

-   **Manifest.MF + Allowlisting** – Only ADK APIs, Camel core and Logging are accessible at runtime. However, if necessary you can import packages for dependent libraries bundled along with project.

-   If you want to read a resource in integration flow project at runtime, use the following code snippet:

    > ### Sample Code:  
    > ```
    > 
    >         InputStream is = ResourceHelper.resolveMandatoryResourceAsInputStream(getCamelContext().getClassResolver(), "//resources/parameters.propdef");
    > 
    > ```


