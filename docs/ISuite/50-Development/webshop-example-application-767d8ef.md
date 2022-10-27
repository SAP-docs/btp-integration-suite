<!-- loio767d8ef11b0f4e04819f9fe03d76c4a2 -->

# WebShop Example Application

Various integration flows are connected to a WebShop application that contains data from a fictitious product catalog.



Certain reference integration flows read data from an external WebShop application.

This WebShop application serves training and demonstration purposes. It contains data from a fictitious product catalog and provides an API that allows remote components, such as SAP Integration Suite , to read certain data sets such as product information.

The API of the WebShop application supports the Open Data Protocol \(OData\). For our scenarios, we use the ESPM WebShop application, which is based on the Enterprise Sales and Procurement Model \(ESPM\) provided by SAP. You can access the user interface of the demo application at the following address: [https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html](https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html). You can see fictitious products on this website. Note that some example integration flows expect a *productId* value provided with the HTTP client request. You can check out this website to find the defined*productId* values a product.

SAP Integration Suite connects to this application through the OData receiver adapter.

