<!-- loio901fbde8415f42d49c2a12f4b42ab856 -->

# Export and Import of API Proxy

You can export API proxies along with their dependencies from the source and import the same to the target system.

During export a zip bundle gets generated, you can use this zip bundle to import the API proxies in the target system.

> ### Note:  
> During the export and import of an API proxy, only the standalone API proxy and its associated entities like target endpoint, proxy endpoint, and resources get exported/imported along with the API proxy. Other dependencies like API providers, KVMs, and certificates do not get imported/exported with the API proxy; you must create them manually in the target system if they don't already exist in the target.
> 
> Import and export of any other entities like products, applications, API providers, KVMs, and certificates are not supported.

To export and import multiple API proxies and their dependencies, refer:

