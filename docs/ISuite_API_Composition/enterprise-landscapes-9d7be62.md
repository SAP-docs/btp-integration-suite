<!-- loio9d7be62ba49a4889b658f1497c52b465 -->

# Enterprise Landscapes

A discussion of enterprise landscapes.

Enterprises and other companies deploy a variety of business software solutions to manage their major business processes, sometimes collectively called ERP solutions. While SAP offers integrated ERP solutions, many enterprises establish a portfolio of different products, sometimes even from other vendors, to address their unique business processes.

One such process is *Lead to Cash*. This process is composed of SAP's Customer Experience suite: SAP Marketing Cloud, SAP Sales Cloud, and SAP Commerce Cloud, which are integrated with SAP S/4HANA. Revolving around functions such as marketing and lead generation, opportunity management, sales, and delivery to customers, enterprises often manage these processes in multiple solutions.



<a name="loio9d7be62ba49a4889b658f1497c52b465__section_och_qq4_zqb"/>

## Replicated Data

Managing a workflow across multiple solutions and data sources from one, or multiple, vendors, introduces common challenges. Imagine a product catalog. Where is this product catalog managed? One possibility is that one of the solutions \(the leading system\) manages the product catalog. In this situation, all other solutions refer to a product by its unique key \(ID\) and perform a query to the leading system for additional product information. To improve performance and availability, master data like the product catalog is often replicated in multiple systems to avoid these cross-system references. For example, SAP Sales Cloud has an entity `ProductCollection`. Similar information exists in the `A_Product` entity of SAP S/4HANA.

This commonly leads to a situation of different key ranges: a product appears in one system with a local key \(product ID\) of 123, while the same product is listed in the second system with a local key of AZ-456. While both copies of the same master data instance have common attributes, each business system adds its own unique details. For example, SAP S/4HANA has manufacturing information about products, while SAP Sales Cloud manages product information that is more relevant to the sales cycle.

Similarly, transactional data is copied or synchronized from one system to another. A common use case is a purchase order that crosses from the system where it was entered, for example, SAP Ariba, to the system where it’s processed, such as SAP S/4HANA. In some landscapes the keys are preserved, but it’s common that each system has its own key-range.

While it might be desirable for each unique entity, such as product and purchase order, to have a globally unique key that is the same in each system, that isn’t the case in the real world. Therefore, cross-system replications and queries, joins and other navigations, require key-mapping. A key map \(ID map\) is like a translation pair: present an entity's local key in one system, to get the local key in the other system. This isn’t a new problem; the need for key mapping of different local keys exists in every integration scenario between communicating systems with shared data, in particular shared master data. Enterprises address this problem today in multiple ways. For example, SAP NetWeaver Process Integration \(SAP PI\) supports a popular Universal Key Mapping Service \(UKMS\) and SAP Sales Cloudhas its own key mapping for integration solution. Other enterprises use SAP Cloud Integration \(CPI\) or other integration products like SAP Master Data Governance \(MDG\), and commonly add custom fields to replicated business objects, which provide a back reference to the other key in the replication-source system.



<a name="loio9d7be62ba49a4889b658f1497c52b465__section_yj4_sq4_zqb"/>

## Partitioned Data

Enterprises often deploy multiple data sources of the same type. For example, they could have one instance of SAP Sales Cloud for its North American sales operations, and another for its European sales. Another common occurrence is multiple SAP S/4HANA tenants, because of regulatory or fiscal requirements, like one financial system for the holding company, and one for its subsidiary. Sometimes enterprises separate systems by products \(for example, soap and toothpaste\).

An entity type is partitioned, or also known as horizontally partitioned, over multiple data sources of the same type, and is content dependent. Unlike the case of replicated data, in a partitioned scenario, an entity only exists in one business system.

