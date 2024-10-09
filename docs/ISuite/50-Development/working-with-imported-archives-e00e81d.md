<!-- loioe00e81d27e1d4203bd09bd36302bc76c -->

# Working with Imported Archives

Imported Archives is a collection of multiple imported archive objects from ESR.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

Imported Archives are custom-implemented user-defined functions \(UDFs\) and saved as archives in the Enterprise Services Repository \(ESR\). For more information about what is an imported archive object and how it's created in an ESR, see [Imported Archives](https://help.sap.com/docs/SAP_NETWEAVER_750/0b9668e854374d8fa3fc8ec327ff3693/4bf40f29c0c33de4e10000000a42189e.html?version=latest).

To achieve reusability across message mappings, SAP Integration Suite supports import of archives from ESR. In SAP Integration Suite, you create an *Imported Archives* artifact and import multiple imported archive objects from ES Repository to the Imported Archives artifact. Later, you reuse the imported archive objects across multiple Function Libraries artifacts, which in turn are reused across multiple message mappings.





### Workflow

A typical workflow to rightly use Imported Archives is as follows:

1.  [Creating an Imported Archives Artifact](creating-an-imported-archives-artifact-e555caf.md) in an integration package.

2.  [Reuse Imported Archives Objects from ES Repository](reuse-imported-archives-objects-from-es-repository-4196091.md)

3.  [Consuming Imported Archives](consuming-imported-archives-e7562a7.md)


