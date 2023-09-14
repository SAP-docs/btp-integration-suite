<!-- loio72010e61b1d14d58a568b6475030a6ca -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Operating Model

An operation model clearly defines the separation of tasks between SAP and the customer during all phases of an integration project.

> ### Remember:  
> There are currently certain limitations when working in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).



SAP BTP and SAP Cloud Integration \(also known as Cloud Integration\) have been developed on the assumption that specific processes and tasks will be the responsibility of the customer. The following table contains all processes and tasks involved in operating the aforementioned services and specifies how the responsibilities are divided between SAP and the customer for each individual task. It does not include the operation of systems and devices residing at operational facilities owned by the customer or any other third party, as these are the customer's responsibility.

Changes to the operating model defined for the services in scope are published using the *What's New* \(release notes\) section of the respective product documentation on SAP Help Portal. Customers and other interested parties must review the product documentation on a regular basis. If critical changes are made to the operating model, which require action on the customer side, an explicit notification is sent by e-mail to the affected customers. If customers want to receive such notifications, they can subscribe to the relevant communication channels offered by SAP \(for example, by opening a customer incident\).

It is not the intent of this document to supplement or modify the contractual agreement between SAP and the customer for the purchase of any of the services in scope. In the event of a conflict, the contractual agreement between SAP and the customer as set out in the Order Form, the General Terms and Conditions of SAP Cloud Services, the supplemental terms and conditions, and any resources referenced by those documents always takes precedence over this document.

Responsibilities for operating the following services are listed in the table below:

-   SAP BTP \(referred to as *Platform*\)

-   SAP Cloud Integration 


**Responsibilities for Operating SAP BTP**


<table>
<tr>
<th valign="top" rowspan="2">

Activity



</th>
<th valign="top" rowspan="2">

Task



</th>
<th valign="top" colspan="2">

SAP Cloud Service



</th>
<th valign="top" colspan="2">

Responsibility



</th>
</tr>
<tr>
<th valign="top">

Platform



</th>
<th valign="top">

Cloud Integration 



</th>
<th valign="top">

SAP



</th>
<th valign="top">

Customer



</th>
</tr>
<tr>
<td valign="top" rowspan="3">

Communication Management



</td>
<td valign="top">

Appoint an English-speaking contact person and communicate the name to SAP. This is required to ensure timely processing of configuration change requests affecting the customer system, interacting with SAP for efficient incident processing, and other interaction between SAP and the customer.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Subscribe to the communication channels offered by SAP for receiving prompt information about any service disruptions, critical maintenance activities affecting the customer system, and change requests requiring action on the customer side.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Inform the customer about any service disruptions, critical maintenance activities affecting the customer system, and change requests requiring action on the customer side.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Asset Management



</td>
<td valign="top">

Management of the hardware and infrastructure resources, from acquisition through disposal. This includes the request and approval process, procurement management, life-cycle management, and disposal management.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Protect IT assets such as systems, network, and data from threats that arise from unauthorized physical access or physical influence on those assets.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Provisioning



</td>
<td valign="top">

Provisioning of resources and systems to customers in accordance with ordered package and requirements. This includes the allocation and provisioning of technical \(physical and virtual\) resources, such as storage, network, compute units, systems, and database hosts, the deployment of the application software and the proper initial configuration of quotas, service subscriptions, permissions, and trust configuration.

> ### Note:  
> Provisioning of tenants linked with global accounts is in the responsibility of the customer.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Integration Content Development



</td>
<td valign="top">

Design, build, deploy, and operate the integration content hosted in the application. This includes proper testing of the integration content under realistic conditions before its productive usage. Integration content may comprise integration flows, adapters, scripts, and so on.



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Security Material Management



</td>
<td valign="top">

Create, configure, deploy, and operate \(renew\) security material hosted in the application. This includes proper testing of the security material under realistic conditions before its productive usage. Security material may comprise user credentials, PGP key rings, certificates, known hosts files, and so on.



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Create, configure, deploy, and operate the keystore artifact hosted in the application. This includes the import of public and private keys used for certificate-based authentication when sending a message from the application.



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Message Transmission



</td>
<td valign="top">

Correct transmission of the messages within the according constraints offered by the application. SAP makes no warranty and shall have no liability for the contents of any message transmitted via the application, including the accuracy or completeness of any information contained in a message.



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark:



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top" rowspan="7">

Change Management



</td>
<td valign="top">

Apply regular product increments, as well as corrections to the application to avoid incidents with minimal possible disruption of normal operations. Ensure that all changes \(such as changes in scheduling of administrative jobs, enabling the product capabilities, and so on\) are evaluated, authorized, prioritized, planned, tested, implemented, documented, and reviewed prior to implementation.



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Perform upgrades of the application in a monthly cycle. Emergency changes, for example, triggered by Incident Management processes, have accelerated testing, approval, and implementation.



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Apply regular product increments, as well as corrections to the infrastructure, systems, and services to avoid incidents with minimal possible disruption of normal operations. Ensure that all changes \(such as updates of the Java runtime, operating system patches, and so on\) are evaluated, authorized, prioritized, planned, tested, implemented, documented, and reviewed prior to implementation.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Perform upgrades of the infrastructure, systems, and services in a bi-weekly cycle. Emergency changes, for example, triggered by Incident Management processes, have accelerated testing, approval, and implementation.



</td>
<td valign="top">

:heavy_check_mark:



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Consume latest version of provisioned infrastructure, systems, and services \(for example, Java runtime, operating system\) to run the application in the customer account.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Collaborate with SAP to ensure timely processing of change requests affecting the resources in the customer account.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Prompt delivery of patches for security vulnerabilities in the operating system and database hosted by the application. This includes reviewing the priority of the relevant patches, assessing the risk, and finally implementing the patch via the Change Management process.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Incident Management



</td>
<td valign="top">

Process incidents reported by the customer according to the Service Level Agreement. The incident is recorded and prioritized in the incident tracking system \(BCP\). Monitor the status and progress of the incident throughout its whole lifecycle and give regular status updates to the customer.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

In the event of incidents, make reasonable effort to support end users and manage their incidents, to explore self-help tools to find already documented solutions, and to liaise with SAP support in the event of new problems to ensure timely processing of incidents affecting the resources in the customer account.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Confirm incident resolution in the incident tracking system \(BCP\).



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Service Requests



</td>
<td valign="top">

Process service requests reported by the customer according to the Service Level Agreement. The service request is recorded and prioritized in the service request tracking system \(BCP\). Monitor the status and progress of the service request throughout its whole lifecycle and give regular status updates to the customer.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Confirm service request completion in the service request tracking system \(BCP\).



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Backup & Restore



</td>
<td valign="top">

Perform a backup of the database systems hosted in the customer account. A database log backup is done every 10 minutes and stored on the primary storage. Every 2 hours the logs are transferred from primary to secondary storage. Full data backup is done every day.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Restore previously backed-up data to recover to a consistent state. Verify the completeness of the restored data based on log files created during the recovery and smoke tests to verify the system’s consistency.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Give regular status updates to the customer throughout the entire restore procedure.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Collaborate with SAP to ensure timely processing of data restores if required.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Validate logical integrity and consistency of the restored data.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

User Access Management



</td>
<td valign="top">

Provide a proper user to SAP, to which the Account Administrator role for the customer account is to be granted by SAP as part of the provisioning process.



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Grant the Administrator role for the customer account to the user nominated by the customer.



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Manage users, permissions, and security configurations within the customer account.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

System Monitoring



</td>
<td valign="top">

Ensure availability of the customer system according to the Service Level Agreements as agreed in the contractual agreement between SAP and the customer, by active monitoring, prompt issue detection, and incident prevention.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Monitor the resource consumption \(memory, CPU, storage\) to detect issues in technical operations.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Malware Management



</td>
<td valign="top">

Ensure that the infrastructure and platform services are free of viruses, spam, spyware, and other malicious software. If malware is detected, an auto-notification is generated, which is assessed and resolved by the operator.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Application Management



</td>
<td valign="top">

Design, develop, deploy, configure, maintain, and operate the application within the customer account. This includes maintaining a staged environment for application delivery \(if required\), application resource management, and managing application availability and performance.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Provide infrastructure, tools, and application programming interfaces for the lifecycle management and operations of the application in the customer account.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Regularly adopt the latest versions of the tools for lifecycle management and operations offered at the [SAP Development Tools site](https://tools.hana.ondemand.com/).



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Network Management



</td>
<td valign="top">

Manage the network isolation of the accounts provisioned to the customer.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Operate the network infrastructure transparently for customers, ensuring elasticity, high availability, and security.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Create and manage own Web domain for the application in the customer account to ensure data isolation.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top">

Penetration Testing



</td>
<td valign="top">

Inform SAP about any penetration testing that shall be performed for the customer system and ask for their approval. Testing is not allowed on any systems or resources shared with other customers. The results, if any, from the test are to be treated strictly as the confidential information of SAP and the customer and are not to be shared with any person or entity without explicit written authorization from SAP. Customers are required to share the results with SAP and work together with SAP operations to mitigate or remedy any security issues.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Decommissioning



</td>
<td valign="top">

Ensure the secure deletion of data and/or hardware disposal. This includes the disassembling of systems along with peripherals and their removal. Before dismantling and handover for further use or return to the vendor, the data is wiped securely from the system.

> ### Note:  
> Decommissioning of tenants can be triggered by the customer for the tenants linked with global accounts.



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Perform a final export of the customer data from the service using the provided data export self services within the time stated in the Terms & Conditions document.

The following services are provided:

-   Export of Message content stored through persist flow-step in an integration flow by means of an API

-   Export of Customer data in JMS queues

-   Export of Integration Content

-   Export of Security Key Material only for public keys




</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
<td valign="top">



</td>
<td valign="top">

:heavy_check_mark: 



</td>
</tr>
</table>

