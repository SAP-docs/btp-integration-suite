<!-- loiod423a4bb6aa640bdbdb9a18372ecd8fa -->

# Enabling Scheduler Support for ADK Sender Adapter



## Context

Referenced scheduler component is equipped with an in-built locking feature for sender integration adapter. Also, a scheduler component comes with a standard User Interface. Follow these steps to use scheduler component in your custom adapter:



## Procedure

1.  Implement the polling sender by extending *<ScheduledPollingConsumer\>*. Other consumers aren't supported.

2.  Add the referenced component for the Sender Variant.

    > ### Source Code:  
    > ```
    > <ReferencedComponents>
    >     <ReferencedComponent>
    >         <ReferencedComponentId>ctype::ExtensionVariant/cname::sap:Scheduler/version::1.0</ReferencedComponentId>
    >         <AttributeMetadataConfiguration>
    >             <Name>scheduleKey</Name>
    >             <AttributeBehavior>Scheduler_ScheduleOnDay,Scheduler_ScheduleToRecur</AttributeBehavior>
    >         </AttributeMetadataConfiguration>
    >     </ReferencedComponent>
    > </ReferencedComponents>
    > ```

    > ### Note:  
    > Currently, only the above-listed behavior options *<Scheduler\_ScheduleOnDay\>* and *<Scheduler\_ScheduleToRecur\>* are supported.

3.  Set the variant level attribute *<useDefaultScheduler\>* as FALSE or skip it.

    > ### Source Code:  
    > ```
    > <Variant VariantName="VariantName" VariantId="ctype::AdapterVariant/cname::GreetingsDs/vendor::sap/tp::sap-sample/mp::sap-sample/direction::Sender"
    >     MetadataVersion="2.0" gen:RuntimeComponentBaseUri="sap-sample" AttachmentBehavior="Preserve"
    >     useDefaultScheduler="false">
    > ...
    > </Variant>
    > ```

4.  Ensure that all the scheduler-related references \(UI\) aren't present in CMD.


