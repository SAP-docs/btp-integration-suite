<!-- loio3972bf80866b457bbaf4902e1dc8a554 -->

# Enabling Connection Status for Integration Flow



<a name="loio3972bf80866b457bbaf4902e1dc8a554__prereq_v2j_yhr_v5b"/>

## Prerequisites

You must have the access to Public APIs. For more information, see [SDK API](sdk-api-c5c7933.md).



## Context

You can use the public API to publish the status of the connection to the integration flow monitoring for ADK based integration adapters. For example, this can provide you more insight on consumption of integration flow connection status.

Use the below interface, which is available for the ADK based integration adapters:

> ### Source Code:  
> ```java
> package com.sap.it.api.adapter.iflowmonitoring;
> 
> import com.sap.it.api.ITApi;
> import org.apache.camel.Endpoint;
> 
> /**
> * Service to submit an event on the status of the Connection as and when necessary.
> * <p>
> * The class can be initialized via the following statement:
> * </p>
> * <code>
> * IFlowMonitorService monitorService = ITApiFactory.getService(IFlowMonitorService.class, null);
> * </code>
> * <p>
> * EndPoint and EventDetails need to be passed.<br><br>
> * </p>
> * This interface must
> * neither be extended nor implemented by clients.
> *  * @since 2.28.0
> */
> public interface IFlowMonitorService extends ITApi {
>      /**
>       * Publishes event for the integration flow
>        * @param endpoint  The camel endpoint
>       * @param eventDetails  {@link EventDetails } Contains the details of the event
>       * @throws IFlowMonitorServiceException  The exception is thrown whenever endpoint/camelContext/EventStatus is invalid or in case of any other internal error
>       */
>      void publishEvent(Endpoint endpoint, EventDetails eventDetails) throws IFlowMonitorServiceException;
> }
>  
> ```



## Procedure

1.  Invoke the `getService` method to get the integration flow monitor service API.

    > ### Source Code:  
    > ```java
    > IFlowMonitorService monitorService = ITApiFactory.getService(IFlowMonitorService.class, null);
    > ```

2.  Based on your requirement, invoke the `publishEvent` based on the event status type. You should use this API to submit an event on the integration flow.

    > ### Sample Code:  
    > Below example shows event submission in success state.
    > 
    > ```
    > EventDetails eventDetails =new EventDetails();
    > eventDetails.setEventStatus(EventStatus.OK);
    > monitorService.publishEvent(endpoint, eventDetails);
    > ```
    > 
    > > ### Sample Code:  
    > > Below example shows event submission in error state.
    > > 
    > > ```
    > > EventDetails eventDetails =new EventDetails();
    > > eventDetails.setEventStatus(EventStatus.ERROR);
    > > eventDetails.setException(exception);
    > > monitorService.publishEvent(endpoint, eventDetails);
    > >  
    > > ```


