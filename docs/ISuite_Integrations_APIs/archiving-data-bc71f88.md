<!-- loiobc71f883d41a44098e9a525e34d0a318 -->

# Archiving Data

The Archiving feature allows you to store message processing logs in an archiving system such as a Content Management System \(CMS\).

> ### Restriction:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

To use the archiving feature, you need to [Configure a Destination](configuring-destination-c1ac580.md), [Enable Archiving](enable-archiving-0fbbe93.md) and [Configure Archiving Settings](configuring-archiving-settings-c38760d.md).

Monitoring data are stored per default 30 days, see [Data Storage Security](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/3feb1638d1694c239061fc8604677bcd.html "Customer data can be stored in dedicated steps during message processing.") :arrow_upper_right:. If you want to store data for a longer period, you can use the archiving feature. To archive data, you need to set up an archiving system, such as a Content Management System. The archiving system must support the CMIS API standard version 1.1.

> ### Restriction:  
> Since the CMS system isn't part of the SAP delivery, you're responsible for monitoring the CMS-server. You must ensure that the CMS-Server is always accessible, and that you react on occurring issues. You can monitor the progress of the data archiving via the Monitoring API, see: [Key Performance Indicators for Archiving Runs](key-performance-indicators-for-archiving-runs-7279d38.md) 

You can archive data for **persist step content**, **adapter payloads**, and **attachments**. Sensitive data contained for example in an authorization header will be masked during archiving.

> ### Note:  
> Payload recording is currently only supported for the following adapters: AS2, ELSTER, OData, HTTPS, MAIL, HTTP; RFC, SFTP, SuccessFactors, SOAP, XI, IDoc.

A message processing log \(MPL\) is archived in the CMS by storing new entries having message processing log \(MPL\) related properties, as well a `.zip` file. The properties include values from the MPL header. The `.zip` file contains the payload of the processed messages.

For every step of an integration flow, where data of the type: persist step content, adapter payloads, and attachments are written, there's a folder named after the step-id. This folder contains the files, and the files contain the data.

Example: For attachments, the structure is: a folder named after the step-id in which the attachment is written, containing 1 file per attachment. The name of the file is the name of the attachment.

> ### Note:  
> Even though the `Persist` step is saving the data encrypted, the data isn’t encrypted when stored in the CMS for archiving.

> ### Tip:  
> If you're using the archiving feature for the first time, we recommend trying out the feature with a few testing integration flows, in order to establish a successful setup before using it for integration flows in production. We further recommend checking the zip-files uploaded for the testing integration flows to verify that all the information required for your archiving use case is contained in the zip file. Since unnecessary information puts extra load on the runtime database, we recommend that you archive only the necessary information. For example, if you use `Receiver` or `Sender Message` recording, it'sn't necessary to also archive `Persisted Messages`.

> ### Note:  
> To some extent, the performance of archiving can be tweaked with internal parameters maintained by our Operations Team only. If you find in your tests that the performance of archiving isn't sufficient for your use case, open a ticket with SAP Support. This ticket allows us to investigate whether we can reach the desired performance by tweaking the parameters.

**Related Information**  


[Configuring Destination](configuring-destination-c1ac580.md "To configure a connection to your CMS system for data archiving, you've to define a destination in the subscriber account of your tenant and follow the steps described in &quot;Enable Archiving in the Cloud Foundry Environment&quot;.")

[Enable Archiving](enable-archiving-0fbbe93.md "To enable data archiving on a tenant in the Cloud Foundry environment, use the OData API.")

[Configuring Archiving Settings](configuring-archiving-settings-c38760d.md "You can configure the archiving settings via the Integration Content Monitor for each integration flow.")

