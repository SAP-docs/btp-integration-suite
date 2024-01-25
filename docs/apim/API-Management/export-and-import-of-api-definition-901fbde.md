<!-- loio901fbde8415f42d49c2a12f4b42ab856 -->

# Export and Import of API Definition

You can export an API definition along with their dependencies from the source and import the same to the target system.



<a name="loio901fbde8415f42d49c2a12f4b42ab856__section_wrt_5kt_c1c"/>

## Prerequisite

The role collection *APIPortal.Administrator* should be assigned to you.

During export a zip bundle gets generated, you can use this zip bundle to import the API definition in the target system.

> ### Note:  
> During the export and import of an API definition, only the standalone API definition and its associated entities like target endpoint, proxy endpoint, and resources get exported/imported. Other dependencies like API providers, KVMs, and certificates do not get imported/exported with the API definition; you must create them manually in the target system if they don't already exist in the target.
> 
> Import and export of any other entities like products, applications, API providers, KVMs, and certificates are not supported.

To export and import multiple API definitions and their dependencies, refer the following:

