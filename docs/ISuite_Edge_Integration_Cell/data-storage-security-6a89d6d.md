<!-- loio6a89d6d62553412da89337879fb4923a -->

# Data Storage Security

Customer data can be stored by dedicated steps during message processing. Edge Integration Cell stores data in the edge environment using persistent volumes. Amazon Web Services \(AWS\) and Microsoft Azure support data encryption at rest Storage providers used for SUSE Rancher or Red Hat OpenShift need to support encryption at rest. For more information, check the documentation of the related platform.

For certain use cases, you can configure that data at rest is encrypted.

Message content can be stored encrypted. If you've configured this security measure, an encryption key is generated automatically. The encryption key is unique for each tenant and is renewed periodically.

Data storage encryption uses AES and a key length of 256 bits. The encryption key isn't stored in the same location as the encrypted data.

The following kinds of data can be stored during the execution of an integration scenario:

-   Message content

    The worker node writes message content data to the database during dedicated steps of an integration flow. You can either store message content temporarily or for a longer period of time \(the default is 30 days\). Temporarily stored message content can be used for subsequent message processing steps. Such steps can then also read message content from the database.

    You can also configure the retention period of the message content.

-   Monitoring data

    During message processing, the worker node also writes monitoring data to the database \(stored by default for 30 days\). Monitoring data comprises the message processing log \(MPL\) that records the executed processing steps of an integration flow.


