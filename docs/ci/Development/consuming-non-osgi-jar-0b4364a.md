<!-- loio0b4364a961874ea8b98b89f7d4838914 -->

# Consuming Non-OSGi Jar

OSGi bundles are normal jar components with extra manifest headers, which you use to develop adapters. In OSGi environment, every service we use must be an OSGi bundle.



## Prerequisites

-   You have created a simple adapter.
-   The adapter is an OSGi esa file with type as Composite. The dependencies are bundled within this esa.
-   You are aware of Java development.



## Context

To integrate camel component into Cloud Integration framework, camel component and its dependencies should be in a OSGi bundle. To convert the jar file to OSGi bundle, refer to the blog, [here](https://community.sap.com/t5/technology-blogs-by-sap/sap-cpi-adapter-development-consuming-an-external-jar-into-an-adapter/ba-p/13382631).



## Results

The consumed non-osgi jar is available inside the component jar as bundle classpath.

