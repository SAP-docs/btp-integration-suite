<!-- loiodd8c30d1c103437298f173fa5d06e96c -->

# Working with Function Libraries

Function Libraries is a collection of multiple Function Library objects.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

In addition to the standard functions, as mapping developers, you can create your own user-defined functions \(UDF\) that are local to a message mapping step.

To achieve reusability across message mappings, a function library comes handy. A function library is an object type in the ES Repository. In SAP Integration Suite, you create a *Function Libraries* artifact and import multiple function library objects from ES Repository to a Function Libraries artifact. Later, you reuse each imported function library object as user-defined functions across multiple message mappings.

For more information about what is a function library object and how is it created in an ES Repository, see [User-Defined Functions and Function Libraries](https://help.sap.com/docs/SAP_NETWEAVER_750/bbd7c67c5eb14835843976b790024ec6/b2faea728f1847a69f74dbf2b427ee6f.html?version=latest).





### Workflow

A typical workflow to rightly use Function Libraries is as follows:

1.  [Creating a Function Libraries Artifact](creating-a-function-libraries-artifact-950b897.md) in an integration package.

2.  [Import Function Library from ES Repository](import-function-library-from-es-repository-d6e7585.md)

3.  [Consuming Function Library in Message Mapping](consuming-function-library-in-message-mapping-d4dcb4a.md)


