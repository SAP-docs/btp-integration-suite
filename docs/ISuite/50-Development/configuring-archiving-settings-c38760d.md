<!-- loioc38760d0e66e41d9a356ee6bb22a4328 -->

# Configuring Archiving Settings

You can configure the archiving settings via the *Integration Content Monitor* for each integration flow.

![](images/ArchivingDataConfig_4ec649e.png)

**Prerequisites**

The archiving feature is enabled.

> ### Note:  
> To be able to read and set the archiving configuration, you must either be an `Integration Developer` , a `Tenant Administrator`, or a `Business Expert` or have the role `TraceConfigurationEdit` assigned.

Use *Configure* to modify the current settings. Once done, save or discard your changes.

Archiving is available for the following options:

-   `Sender Channel Messages`: Messages received from Sender and responses returned to Sender.

-   `Receiver Channel Messages`: Messages sent to Receiver and responses returned by Receiver.
-   `Persisted Messages`: Messages stored via `Persist` flow step.
-   `Log Attachments`: Message Processing Log attachments.

Carefully consider the integration flows you want to activate the archiving for, and the configuration needed for these integration flows. With each additional setting, the system gathers more data in the `.zip` file to be uploaded, and increases the volume of data stored in the CMS. Also consider that `Sender Channel Messages` and `Receiver Channel Messages` are stored in the database in addition to the data already stored for the MPL.

Use payload recording to record incoming and outgoing payloads. Since the same message can exist multiple times for sender and receiver channels, it's sufficient to record them once at one of the channels for archiving purposes. JMS and ProcessDirect Adapter payloads are only used within SAP environments, enabling payload recording for these adapters isn't recommended.

**Additional Recommendations**

-   If you've integration flows calling each other, then carefully decide on recording payloads of sender and receiver adapter to avoid storing too much data.

-   If you archive adapter payloads, review your integration flow design, to check if you can remove any attachments writings or use `Persist Step` components.
-   To be able to record the incoming and outgoing payloads in the integration flow as early as possible, enable the Sender and Receiver Chanel recording.

**Conditions for Archiving Message Processing Logs**

To be archived, all the MPLs have to fulfill the following conditions:

1.  The MPLs are defined as "relevant for archiving". This condition is true, if a least one the archiving configuration settings were active for the integration flow producing the MPL, at the execution time of the integration flow.

2.  The MPLs are at least `x` days old. `x` is the number of days after which an MPL is to be archived. The age of an MPL is determined by its log end date. The default value for `x` is 7.
3.  The MPLs aren't in status `DISCARDED`. MPLs in status `DISCARDED` aren't relevant for archiving.

    > ### Note:  
    > Message Processing Logs with all other status values are archived if they fulfill conditions 1 and 2.

    > ### Caution:  
    > If you've selected the optional parameter `ArchiveCompletedMessagesOnly`, and set its value to `TRUE`, or `true`, only archiving relevant MPLs with status COMPLETED is archived. See: [Configuring Destination](configuring-destination-c1ac580.md)


