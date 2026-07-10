<!-- loio8c12a8e4ff9b40e08e0c77b4784c020e -->

# Define a MIME Multipart Encoder

This step transforms the message content into a MIME multipart message.



## Context

If you want to send a message with attachments, but the protocol \(for example, HTTP or SFTP\) does not support attachments, you can send the message as a MIME multipart instead.



## Procedure

1.  Open the integration flow in the editor.

2.  From the palette, choose *Message Transformers* \> *Encoder*.

3.  Select *MIME Multipart Encoder*.

4.  Specify the attributes of the step \(in tab *Processing*\).


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

     
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Multipart Subtype*
    
    </td>
    <td valign="top">
    
    Defines how the Multipart message is related to the main message.

    For more information, check out the specification at [https://www.w3.org/Protocols/rfc1341/7\_2\_Multipart.html](https://www.w3.org/Protocols/rfc1341/7_2_Multipart.html)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Add Multipart Headers Inline*
    
    </td>
    <td valign="top">
    
    Allows you to control whether message headers are to be part of the MIME Multipart message or not.

    More information:

    [MIME Multipart Messages](mime-multipart-messages-3816537.md)

    [MIME Multipart Encoder: Handling Message Headers \(Examples\)](mime-multipart-encoder-handling-message-headers-examples-b446281.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Include Headers* \(only when *Add Multipart Headers Inline* selected\)
    
    </td>
    <td valign="top">
    
    With this attribute, you can specify which headers of the inbound message are to be treated in the specified way. You can enter a regular expression. For example, the expression`h.*` indicates headers that start with character `h`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Fold Long Headers* \(only when *Add Multipart Headers Inline* is not selected\)
    
    </td>
    <td valign="top">
    
    If set, headers will be folded by inserted line breaks.

    > ### Note:  
    > If you're using the **Mail adapter**, the folding of long headers is recommended to comply with the existing protocol guidelines regarding header formats. If you are working with the **http protocol**, do not fold headers as requests with folded headers would not comply to the http specification and could lead to errors in the receiving system.


    
    </td>
    </tr>
    </table>
    

**Related Information**  


[MIME Multipart Messages](mime-multipart-messages-3816537.md "")

[MIME Multipart Encoder: Handling Message Headers \(Examples\)](mime-multipart-encoder-handling-message-headers-examples-b446281.md "")

[Example Scenario with MIME Multipart Encoder/Decoder](example-scenario-with-mime-multipart-encoder-decoder-80baed3.md "")

