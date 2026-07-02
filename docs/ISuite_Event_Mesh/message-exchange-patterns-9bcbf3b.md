<!-- loio9bcbf3b1cb0f4a66bc717ef69b67f1bc -->

# Message Exchange Patterns

Know the different message exchange patterns.

Most messaging applications use the following messaging exchange patterns:

-   Publish–subscribe

-   Point-to-point

-   Request reply


Most events use the publish-subscribe pattern.



<a name="loio9bcbf3b1cb0f4a66bc717ef69b67f1bc__section_brf_dgh_hbc"/>

## Publish–Subscribe

In a publish-subscribe exchange pattern, messages sent by the producer \(publisher\) can be processed multiple times by different consumers \(subscribers\). Each consumer receives its own copy of the message for processing.



<a name="loio9bcbf3b1cb0f4a66bc717ef69b67f1bc__section_fmm_ggh_hbc"/>

## Point-to-Point

In a point-to-point exchange pattern, messages sent by the producer are processed by a single consumer.



<a name="loio9bcbf3b1cb0f4a66bc717ef69b67f1bc__section_bf2_ngh_hbc"/>

## Request Reply

In a request reply exchange pattern, applications achieve two-way communication using separate point-to-point channels: one for requests, and another for replies.

