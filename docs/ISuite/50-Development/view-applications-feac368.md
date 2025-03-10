<!-- loiofeac3687b4d842cb903bdbd9e13ace54 -->

# View Applications

In the context of API Management, an application is the unit of API consumption.



## Context

API Management enables the creation of secure API proxies for your APIs. These proxies are protected using "Appkey" and "Secret". Application developers are required to acquire these credentials in order to utilize the API proxies exposed through the various products. They need to declare the usage of these products by creating an application from Developer Hub.

As an admin, you can view the list of applications that the application developers have created in the Developer Hub, along with the developer details, associated products and AppKey and secret.



## Procedure

1.  Log on to SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Engage*.

3.  Navigate to the *Applications* tab page.

    A list of Applications appears. If you have logged on to SAP Integration Suite with the role APIPortal.Administrator, then you can view the Application key and secret.

    You can view the number of calls made for all APIs in an application for the current month. The data is visible for each application in the *Calls* column and also in the details screen of individual application.

    You can click on the refresh icon to obtain the latest data.

    > ### Note:  
    > There is some delay in reflecting the latest data.

    Notion used to display the data is as per metric specifications, for example:

    -   999 shows as 999 and 1000 shows as 1k
    -   999000 shows as 999K and 1000000 shows as 1M
    -   1500000 shows as 1.5M and 1000000000 shows as 1G


**Related Information**  


[Create an Application](create-an-application-a501a6d.md "Create an Application to consume the required APIs.")

