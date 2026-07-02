<!-- loio84c68827509147e1b24d769d5eb517a5 -->

# Test Messaging

Test messaging on queues and topics you've created in Event Mesh capability.



<a name="loio84c68827509147e1b24d769d5eb517a5__prereq_ggp_d2q_32c"/>

## Prerequisites

-   You have the EventMeshDeveloper or EventMeshAdmin role assigned to you.
-   You have created a messaging client. See [Configure A Message Client](configure-a-message-client-867c517.md).
-   You've created queues and topics for the messaging client. See [Create A Queue](create-a-queue-95357fa.md).



## Procedure

1.  Login to SAP Integration Suite

2.  From the left panel, navigate to *Test* \> *Event Mesh*

3.  Choose if you want to *Publish Messages* to a queue or topic or *Consume Messages* from a queue.


    <table>
    <tr>
    <th valign="top">

    Publish Messages
    
    </th>
    <th valign="top">

    Consume Messages
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    1.  Choose the *Queue* or *Topic* radio button depending on where you want to test publishing messages from.
    2.  Choose the messaging client.
    3.  Choose the queue or topic.
    4.  Set the *Content-Type* and enter a message.

        > ### Example:  
        > Publish to <queue name or topic name\>

    5.  Choose *Publish*.


    
    </td>
    <td valign="top">
    
    1.  The *Queue*radio button is pre-selected.
    2.  Choose the required messaging client.
    3.  Choose *Consume*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    A confirmation is shown when you publish a message to the queue or topic.
    
    </td>
    <td valign="top">
    
    A confirmation is shown and you can view the properties of the consumed message under *Message Properties*.
    
    </td>
    </tr>
    </table>
    

