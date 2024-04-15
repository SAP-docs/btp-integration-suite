<!-- loio94ef1f283e624ebdae747dbad67b38dc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Gather and Join

The Gather step merges messages from different routes \(into a single message\) with the option to define certain strategies how to combine the initial messages. The Join step is used in combination with the Gather step. It brings together the messages from different routes, but it does not affect the content of the messages.



## Context

The *Gather* step allows you to define conditions based on the type of messages that are merged. You can choose to gather:

-   XML messages of different format

-   XML messages of the same format

-   Plain text messages

-   Any format


The *Join* element enables you to bring together messages from different routes before combining them into a single message. You use this step in combination with the *Gather* element. *Join* only brings together messages from different routes without affecting the content of messages.

> ### Remember:  
> -   If you want to combine messages that are transmitted to more than one route by a *Multicast* step, you need to place *Join* step before the *Gather* step.
> -   If you want to combine messages that are split using a *Splitter* step, you use only the *Gather* step.
> -   You do not introduce Gather or Join step after EDI Splitter.

Based on your requirements, you choose the strategy to combine the two messages:

-   When combining XML messages of the same format, you have the following options:

    -   Don't specify any condition \(multimapping format\).

    -   Specify the XPath to the node at which the messages have to be combined.


-   For XML messages of different formats, you can only combine the messages.

-   For plain text messages, you can only specify concatenation as the combination strategy.


For all three incoming formats, you can also choose the strategy *Zip* that allows you to merge the input into a single archive \(`.zip`\) file. In that case, you need to specify a file name pattern.

Specify a valid XPath expression that includes namespace prefixes if the incoming payload contains namespace declarations, including default namespace declarations.

If the incoming payload contains namespace declarations including default namespace, ensure that you specify the XPath with namespace prefixes. Also ensure that the namespace prefix mapping is defined in the *Runtime Configuration* of the integration flow \(in field *Namespace Mapping*\). If the XPath does not point to any element in any of the branches of the incoming XML, the scenario fails with an exception.



## Procedure

1.  To model a *Gather* step, in the palette, choose <span class="SAP-icons-V5"></span> \(Message Routing\), then *Gather*.

2.  Place the *Gather* element in the integration process and define the message path.

3.  On the *General* tab, you can change the name of the *Gather* element.

4.  On the *Aggregation Strategy* tab, define the attributes of the element based on the descriptions in the following table.


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
    
    *Incoming Format* 
    
    </td>
    <td valign="top">
    
    Specify format of incoming message.

    -   *XML \(Same Format\)*

        If messages from different routes are of the same format

    -   *XML \(Different Format\)*

        If messages from different routes are of the different format

    -   *Plain Text*

        If messages from different routes are of the plain text format

    -   *Any*

        If you want to combine any incoming messages independent of their format



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Aggregation Algorithm*
    
    </td>
    <td valign="top">
    
    There are the following options:

    -   *Combine* \(can only be selected if for *Incoming Format* you have selected *XML \(Same Format\)* or *XML \(Different Format\)*\)

        Combine the incoming messages without any conditions. The messages are combined in Multimapping format.

        > ### Note:  
        > In case you are using the mapping step to map the output of this strategy, you can have the source XSD in the LHS and specify the Occurrence as 0..Unbounded.

    -   *Combine at XPath* \(can only be selected if for *Incoming Format* you have selected *XML \(Same Format\)*\)

        Combine the incoming messages at the specified XPath.

    -   *Concatenate* \(can only be selected if for *Incoming Format* you have selected *Plain Text*\)

        Concatenate the information from the different sources one after another.

    -   *Zip* 

        Aggregates files to an archive \(`.zip`\) file.

        > ### Caution:  
        > With this option, empty messages will not be included in the generated archive files.

    -   *Tar*

        Aggregates files to an archive \(`.tar`\) file.

        > ### Caution:  
        > With this option, empty messages will not be included in the generated archive files.


    > ### Remember:  
    > Any information that is in the header or property of a previous step is not aggregated by a Gather step.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Combine from source \(XPath\)*

    \(Enabled only if for *Aggregation Algorithm* the option *Combine at XPath* is selected\)
    
    </td>
    <td valign="top">
    
    XPath of the node that you are using as reference in the source message to retrieve the information.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Combine at target \(XPath\)*

    \(Enabled only if for *Aggregation Algorithm* the option *Combine at XPath* is selected\)
    
    </td>
    <td valign="top">
    
    XPath of node that acts as the root for combined message.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *File Name*

    \(Enabled only if for *Aggregation Algorithm* the option *Zip* or *Tar* is selected\)
    
    </td>
    <td valign="top">
    
    Specify a simple expression to define unique file names within the archive.

    If not specified, header `CamelFileName` is evaluated. In case the header is not available at runtime, a unique file name will be generated.
    
    </td>
    </tr>
    </table>
    
    > ### Tip:  
    > Consider the following XML:
    > 
    > > ### Sample Code:  
    > > ```
    > > <root xmlns="http:defaultnamespace.com">
    > >                 <f:table xmlns:f="http://www.w3schools.com/furniture">
    > >                                 <f:name>African Coffee Table</f:name>
    > >                                 <f:width>80</f:width>
    > >                                 <f:length>120</f:length>
    > >                 </f:table>
    > >                 <table>
    > >                                 <name>African Coffee Table</name>
    > >                                 <width>80</width>
    > >                                 <length>120</length>
    > >                 </table>
    > > </root>
    > > ```
    > 
    > **f** and **d** are the prefixes defined in the *Namespace Mapping* field of *Runtime Configuration* and mapped to the namespaces `http://www.w3schools.com/furniture` and `http:defaultnamespace.com` respectively. Examples of valid XPath expressions for the above XML are:
    > 
    > -   `//f:table`
    > 
    > -   `/d:root/f:table`
    > 
    > -   `/d:root/d:table`

5.  Save or deploy the changes.

    > ### Note:  
    > In the case of integration flows in OData API artifacts, you can save the integration flow and deploy the OData API.

    This flow element does not work directly with *Router*. It is recommended to model the flow using *Local Integration Process*.




<a name="loio94ef1f283e624ebdae747dbad67b38dc__result_ojs_kh3_cmb"/>

## Results

The output for the incoming XML of the same format is different from the output of the incoming XML of different format when using the *Combine* strategy in the *Gather* step.

> ### Sample Code:  
> ```
> 
> Payload 1: 
> <note>
>        <to>Jack</to>
>        <from>Jill</from>
>        <heading>Reminder</heading>
>        <body>Don't forget me this weekend!</body>
>  </note>
> Payload 2:
> <note>
>        <to>Chris</to>
>        <from>Benoit</from>
>        <heading>Reminder</heading>
>        <body>Don't forget me this weekend!</body>
>  </note>
> Payload 3:
> <note>
>        <to>Tove</to>
>        <from>Jani</from>
>        <heading>Reminder</heading>
>        <body>Don't forget me this weekend!</body>
>    </note>
> ```
> 
> ```
> Incoming XML: Same XML format
> Output: 
> <?xml version='1.0' encoding='UTF-8'?><multimap:Messages xmlns:multimap="http://sap.com/xi/XI/SplitAndMerge"><multimap:Message1><note>
>        <to>Jack</to>
>        <from>Jill</from>
>        <heading>Reminder</heading>
>        <body>Don't forget me this weekend!</body>
>    </note><note>
>        <to>Chris</to>
>        <from>Benoit</from>
>        <heading>Reminder</heading>
>        <body>Don't forget me this weekend!</body>
>    </note><note>
>        <to>Tove</to>
>        <from>Jani</from>
>        <heading>Reminder</heading>
>        <body>Don't forget me this weekend!</body>
>    </note></multimap:Message1></multimap:Messages>
> ```
> 
> ```
> Incoming XML: Different XML format
> Output: 
> <?xml version='1.0' encoding='UTF-8'?><multimap:Messages xmlns:multimap="http://sap.com/xi/XI/SplitAndMerge"><multimap:Message1><note>
>        <to>Jack</to>
>        <from>Jill</from>
>        <heading>Reminder</heading>
>        <body>Don't forget me this weekend!</body>
>    </note></multimap:Message1><multimap:Message2><note>
>        <to>Chris</to>
>        <from>Benoit</from>
>        <heading>Reminder</heading>
>        <body>Don't forget me this weekend!</body>
>    </note></multimap:Message2><multimap:Message3><note>
>        <to>Tove</to>
>        <from>Jani</from>
>        <heading>Reminder</heading>
>        <body>Don't forget me this weekend!</body>
>    </note></multimap:Message3></multimap:Messages>
> ```

