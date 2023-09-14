<!-- copy603ab8b209c0470b832cdb5581c27a86 -->

# Create a Content Modifier to Add a Header

Add a Content Modifier to your model to define a header, which will be used in a later step to filter data from the external source.

If you remember, our input message has only one field: `productIdentifier`. This field will contain a product identifier that we want to use to filter the results from the WebShop application.

To make this number available to the integration framework during message processing, SAP Cloud Integration provides the option to store the value of `productIdentifier` from the incoming message either in the message header or in a data container referred to as an exchange property.

We use the first option, and to prepare the message accordingly we use a Content Modifier.

1.  Add a second Content Modifier \(after the first one\) to the integration flow model.

2.  In the properties section of the second Content Modifier, go to the *Message Header* tab and choose *Add*.

3.  Specify the following parameters:

    -   *Name*: Enter any name, for example, `productIdentifier`. This is the name of the header that will be created by the Content Modifier step.

    -   *Type*: Select *XPath*.

        > ### Tip:  
        > In this example, you use an XML Path Language \(XPath\) expression to address a dedicated element of your inbound message. XPath allows you to address any element in an XML structure by using a well-defined syntax. The expression `//<element name>` addresses all elements with name `<element name>` in the XML document.

    -   *Data Type*: Enter `java.lang.String`.

    -   *Value*: Enter `//productIdentifier` \(which is the XPath expression that points to the `productIdentifier` field in the inbound message\).


    ![](images/Content_Modifier_Details_7d0ba30.png)

4.  Connect the first Content Modifier \(which defines the message body\) with the second one.


In other words, the Content Modifier creates a header with the name `productIdentifier`, which will contain the value of the `productIdentifier` field of the incoming message.

**Related Information**  


[Define Content Modifier](define-content-modifier-8f04a70.md "")

