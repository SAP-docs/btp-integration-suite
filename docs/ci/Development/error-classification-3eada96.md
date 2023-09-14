<!-- loio3eada964c2fb4d80830b2e1c5a130bb8 -->

# Error Classification



At design time of an integration project, the way how a message is to be processed is specified by a number of integration flow steps \(for example, content modifier, encryptor or routing step\). When an integration flow is being processed at runtime, errors can occur at several individual steps within the process flow \(referred to as *processing steps* to differentiate them from the integration flow steps as modelled at design time\).

Integration flow steps can specify message processing at different levels of complexity. Therefore, in general an integration flow step \(design time\) can result in multiple processing steps steps at runtime.

Each processing step gets a unique *Step ID* which is displayed in the message processing log.

For example, a content modifier step in an integration flow can \(at runtime\) be related to multiple processing steps: The content modifier step can be configured in a way that one processing step changes the message header, one the message body, and another one an exchange property.

![](images/Content_Modifier_with_three_steps_f760ad4.png)

This content modifier will get three different Step IDs at runtime, for example: `CallActivity_9`, `setBody4` and `setProperty1`.

To relate a **modelled** integration flow step \(like the content modifier mentioned above\) to an error occurring at a certain processing step at runtime, you can use an identifier which is referred to as *Model Step ID*.

To allow an integration flow developer to relate to a certain integration flow step during error handling, the runtime provides the Model Step ID of the integration flow step where the error occurred as Exchange Property `SAP_ErrorModelStepID`. The content of the property can then be evaluated in the error handling.

> ### Note:  
> You can use the property for instance in a condition definition of a Router step to choose a different error handling strategy depending on the step where the error occurred.
> 
> Example for a routing condition : `${property.SAP_ErrorModelStepID} = 'CallActivity_1'`

