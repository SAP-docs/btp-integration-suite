<!-- loio4c0e3b87eba541c7af8cff6034778906 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Zip Splitter

This step splits an archive \(.zip\) file into individual files.



## Context

When you have applied the Zip Splitter on a file archive, SAP Cloud Integration can process individual files from the archive in subsequent steps.



## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Message Routing\), then *Splitter* \> *Zip Splitter*.

2.  Place the *Zip Splitter* element in the integration process and define the message path.

3.  On the *General* tab, you can change the name of the *Zip Splitter* element.

4.  On the *Processing* tab, define the attributes of the element based on the descriptions in the following table.


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *File Name Pattern* 
    
    </td>
    <td valign="top">
    
    Enter a file name pattern if you like to process only specific files from the archive.

    For example, if you like to process only XML files from the archive, enter the following expression:

    `*.xml`

    If you don't enter anything, all files from the archive are processed.

    > ### Note:  
    > **Usage of file name pattern:**
    > 
    > Expressions, such as `ab*`, `a.*`, `*a*`, `?b`, and so on, are supported.
    > 
    > The expression `*` replaces no character or an arbitrary number of characters.
    > 
    > The expression `?` replaces exactly one arbitrary character.
    > 
    > Examples:
    > 
    > If you specify `file*.txt` as the *File Name Pattern*, the following files are polled by the adapter: `file1.txt`, `file2.txt`, as well as `file.txt` and `file1234.txt`, and so on.
    > 
    > If you specify `file?.txt` as the *File Name Pattern*, the following files are polled by the adapter: `file1.txt`, `file2.txt`, and so on, but **not** the files `file.txt` or `file1234.txt`.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Stop on Exception* 
    
    </td>
    <td valign="top">
    
    Select this option to stop file processing if an exception occurs.

    If you deselect this option, splitting the archive and processing of the individual files continues, even if processing one of them fails.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > -   Streaming is activated for this step. That means, the system already starts processing parts of the archive file before the archive file is fully transferred to the memory \(of the runtime component\).
    > 
    > -   If the ZIP archive contains an entry with a data descriptor, the compression method must be DEFLATED due to a limitation of the JDK.

5.  Save or deploy the configuration.


**Related Information**  


[Define Gather and Join](define-gather-and-join-94ef1f2.md "The Gather step merges messages from different routes (into a single message) with the option to define certain strategies how to combine the initial messages. The Join step is used in combination with the Gather step. It brings together the messages from different routes, but it does not affect the content of the messages.")

[Handle Exceptions When Using the Splitter Pattern](handle-exceptions-when-using-the-splitter-pattern-74e431c.md "In many integration scenarios, larger messages are split into smaller parts using a splitter pattern. The smaller chunks are then processed by SAP Integration Suite .  ")

