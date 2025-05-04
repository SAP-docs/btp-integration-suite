<!-- loio1b52dd10f37c45feabaa1949bc80f261 -->

# Configure

An introduction to the configuration topics of Graph.

This section provides all the information you need to:

-   Configure Graph in SAP Integration Suite 

-   Connect your business systems
-   Create and extend your business data graph

As an IT administrator in charge of enterprise IT, you deploy a variety of business software solutions to manage your major business processes.

While integrated ERP solutions make this easier, like most SAP customers, you may have established a portfolio of different business systems to address your unique business processes. Many of these data sources are in cloud data centers \(SaaS\), while others are local, on-premise data sources.

You probably use specific business systems for development, staging, and production. Like many enterprises, you may also manage separate landscapes used by different lines of business, subsidiaries, or regional organizations.

Graph defines a landscape as a logical cluster of related business systems \(also known as data sources\) with a common purpose and scope, for use by extension applications. A landscape may consist of cloud subscriptions to SAP solutions like SAP Sales Cloud or SAP SuccessFactors, or one or more on-premise SAP S/4HANA systems. Most companies have separate landscapes for development, QA, staging, training, and so forth. While some companies manage only a few landscapes, it is not uncommon for an enterprise to have as many as 20 different landscapes.

The data sources in a landscape are related. Sales quotes and purchase orders refer to products, and are ordered or sold by employees, who relate to cost centers. All of this data might be maintained in different systems, often with different keys, requiring replications with key mapping and other processes to keep all the data consistent and synchronized.

Now, consider the needs of the different developers of custom applications who require access to data in your IT architecture. Developers need to know:

-   Where the data is.

-   Which data sources \(business systems\) there are.

-   What APIs are available or must be configured.

-   How everything is connected, and

-   How to access everything.

-   Which is the leading system for certain types of data.

-   How to overcome firewalls and enable VPNs.

-   How to deal with different authentications; which usernames work in which system.

-   ... and more.


Providing all this information to developers, particularly partners, is complex, and results in additional fragile and repetitive custom-developed code. And if you ever change your architecture in the future, the change may break the assumptions made by some of these applications.

Graph changes all of this. As the owner of enterprise data, you configure a set of secure connections to the APIs of your landscapes, and grant Graph exclusive access to these connections. Then, by specifying how the landscape is to be used, and where the data is located in the different business systems, the landscape is abstracted, and the developers see a business data graph, connecting all the data. You grant your trusted developer or partner applications access to a specific business data graph and enable users to use these applications. They focus on the data itself – without having any awareness of the landscape configuration. Even if you change the landscape in the future, you won't affect their extension applications.

For more information, see:

-   [Enterprise Landscapes](enterprise-landscapes-9d7be62.md): understand how data replication and partitioning determines how your data is accessed

-   [Data Locating Policy](data-locating-policy-28d2c2c.md): learn how Graph locates data

-   [Configuration Strategies - Use Cases](configuration-strategies-use-cases-3652dcb.md): study examples to understand the configuration of business data graphs

-   [Role of the Administrator](role-of-the-administrator-7b44365.md) for detailed step-by-step setup and configuration instructions


