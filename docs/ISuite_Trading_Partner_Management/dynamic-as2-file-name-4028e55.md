<!-- loio4028e55469c6406ca93f3e0faa0c861a -->

# Dynamic AS2 File Name

Define a custom AS2 file name for your integration flow.



## Context

When utilizing the generic integration flow for AS2 Receiver, you may need to define the AS2 file name manually. This can be achieved using the custom integration flow. To know more, follow the procedure below.



## Procedure

1.  **Create Custom Integration Flow**

    1.  **Sender Side Configuration**

        1.  On the Sender side, set your adapter type to *ProcessDirect*.

        2.  Maintain your connection address as `/as2_custom_iflow`.

    2.  **Groovy Script Configuration**

        1.  In the Groovy script, parse your payload and generate a file name.

        2.  Additionally, save the file name in the property `SAP_AS2_REC_File_Name`.

    3.  **Receiver Side Configuration**

        1.  On the Receiver side, set the adapter type to AS2.

        2.  Configure the necessary AS2 parameters.
        3.  Under the *Process* tab, set the *File Name* with the expression `${property.SAP_AS2_REC_File_Name}`.

            > ### Remember:  
            > -   Ensure that this step is configured accurately, as it is crucial for the custom integration flow.
            > 
            > -   The property `SAP_AS2_REC_File_Name` must be used to store the generated file name.
            > -   The expression `${property.SAP_AS2_REC_File_Name}` must be used to set the File Name under the *Process* tab.



2.  **Configure Communication Channel**

    1.  In your partner profile, create a communication channel for the receiver and set the adapter type to *Process\_Direct*. To know how to configure the communication channel, see [Systems](systems-912c3d3.md).

    2.  In the *Connection* tab, enter the custom integration flow address `/as2_custom_iflow` in the *Address* field.

    3.  Save your changes.


3.  **Groovy Script Configuration**

    1.  You can also use a groovy script to set the filename based on the message type and timestamp. Here is a sample grooy script that achieves this:

        > ### Sample Code:  
        > ```
        > 
        > import com.sap.gateway.ip.core.customdev.util.Message;
        > import java.time.LocalDateTime;
        > import java.time.format.DateTimeFormatter;
        > 
        > def Message processData(Message message) {
        >     def body = message.getBody(java.lang.String) as String;
        > 
        >     // Use the regular expression to capture the message type from the UNH segment
        >     def pattern = /UNH\+\d+\+([A-Z]+):/;
        >     def matcher = (body =~ pattern);
        >     def messageType = "";
        >     if (matcher.find()) {
        >         messageType = matcher.group(1);
        >     } else {
        >         throw new IllegalStateException("Message type not found.");
        >     }
        >     def timestamp = LocalDateTime.now().format(DateTimeFormatter.ofPattern("yyyyMMddHHmmss"))
        >     
        >     message.setProperty("SAP_AS2_REC_File_Name", messageType + "_" + timestamp + ".edi");
        >     return message;
        > }
        > ```

    2.  If the above groovy script is used to generate the filename, the SAP\_AS2Filename would look like this: `ORDERS_20240618062033.edi`.


