<!-- copy78d524ce94f44c259b417bc14d93f32c -->

# Create a Content Modifier to Define the Message Body

Add a Content Modifier step to create the message body.

As the integration flow has no sender, we use a Content Modifier to create a message from scratch.

1.  To add a Content Modifier, go to the palette, choose the *Message Transformers* icon, and select the *Content Modifier* icon.

    ![](images/Content_Modifier_in_Palette_9c9bbd0.png)

2.  Place the Content Modifier in the model after the Timer Start event.

3.  In the Content Modifier properties section, go to the *Message Body* tab and enter the following string sequence in the entry field:

    > ### Sample Code:  
    > ```
    > <root>
    > <productIdentifier>HT-1080</productIdentifier>
    > </root>
    > ```

    This simulates the inbound XML message.

    ![](images/Getting_Started_Content_Modifier_Message_Body_4c41b73.png)

4.  Connect the Timer event with the Content Modifier. To do this, select the Timer event, click the arrow icon, and drag and drop the cursor to the Content Modifier.

    ![](images/Getting_Started_Timer_Start_03_381d676.png)


**Related Information**  


[Define Content Modifier](define-content-modifier-8f04a70.md "")

