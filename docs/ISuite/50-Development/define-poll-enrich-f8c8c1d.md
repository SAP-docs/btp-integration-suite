<!-- loiof8c8c1d5396b4cc780e91df826810f95 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Poll Enrich

Poll content from an external component and enrich the original message with it.



## Context

You can use the *Poll Enrich* to read \(poll\) messages from an external component and add the content to the original message in the middle of the message processing sequence.

> ### Note:  
> Currently, you can use the *Poll Enrich* step only to read content from an SFTP server.



## Procedure

1.  Add a *Sender* shape to the integration flow model or select an existing one.

    See: [Assign Sender and Receiver Components](assign-sender-and-receiver-components-f0eb056.md).

2.  Add a *Poll Enrich* step to the integration process:

    1.  In the palette, choose ![](images/external_call_bfbf8b0.png) \(Call\) and then choose :envelope: from the menu. From the submenu, choose <span class="SAP-icons-V5"></span> \(Poll Enrich\).

    2.  Place the *Poll Enrich* shape in the integration process.


3.  Add a connection from the *Sender* shape to the *Poll Enrich* shape by dragging and dropping.

    When used with a polling sender adapter such as the *SFTP* sender adapter, the *Poll Enrich* step actively polls message from an external component. Therefore, the connection goes from the *Sender* shape to the *Poll Enrich* shape.

4.  As *Adapter Type*, select *SFTP*.

    > ### Note:  
    > Currently, only a variant of the *SFTP* sender adapter type can be used together with the *Poll Enrich* step. Note that only a subset of features is supported when compared with the feature set of the SFTP sender adapter used with a Message Start event.
    > 
    > See: [Configure the SFTP Sender Adapter Used with the Poll Enrich Step](configure-the-sftp-sender-adapter-used-with-the-poll-enrich-step-1f15fe2.md).

5.  Select the connection line between the *Sender* shape and the *Poll Enrich* step and specify the settings of the SFTP sender adapter.

    See: [Configure the SFTP Sender Adapter](configure-the-sftp-sender-adapter-2de9ee5.md).

6.  Select the *Poll Enrich* step in the integration flow model.

7.  In the *Processing* tab, define the following parameters.

    **Processing Tab**


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Aggregation Algorithm*
    
    </td>
    <td valign="top">
    
    This parameter determines how the system merges the reply from the external component into a single message.

    There are the following options.

    -   *Combine XML:* Combines the message polled from the external component with the original message without any conditions. The messages are combined in multimapping format.

    -   *Concatenate:* The message polled from the external component is added to the existing message.

    -   *Replace:* The existing message is replaced with the message polled from the external component.

    > ### Note:  
    > If for *Aggregation Algorithm* you've selected *Combine XML* or *Concatenate*, headers and properties from the original message \(before the *Poll Enrich* step\) are preserved. That means, after the *Poll Enrich* step has been processed, the message contains both the original headers and the headers from the polled message. If there's a conflict with a header of the polled message, the latter one replaces the header of the original message. For example, the value of header `CamelFileName` is overridden by the one from the polled message.
    > 
    > If for *Aggregation Algorithm* you've selected *Replace*, this rule applies for properties only. In this case, the payload and headers of the original message are removed.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Throw Exception if no Message Found* 
    
    </td>
    <td valign="top">
    
    Select this option to throw an exception in the message processing if no message is found. By default, this option is disabled.

    If you keep this option disabled, the header `SAP_PollEnrichMessageFound` is set to false and processing continues even if there’s no message.
    
    </td>
    </tr>
    </table>
    
8.  Save the integration flow.


