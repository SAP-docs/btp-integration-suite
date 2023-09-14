<!-- loio82d62320472c44849dd22b28b43eaacb -->

# Run the Integration Flow and Monitor the Message Processing

Run the integration flow and check the result of message processing.

When the integration flow has been deployed successfully, the message is processed without any further trigger \(based on the settings of the timer\).

1.  When you have saved and deployed your integration flow, check the deployment status. Go to the *Monitor* section of the Web UI and select a tile under *Manage Integration Content*.

2.  As soon as deployment has finished, the status *Started* should be displayed for your integration flow.

3.  Go back to the overview page of the Web UI *Monitor* section and select a tile under *Monitor Message Processing*.

    If your integration flow has been processed successfully, the status *Completed* should be shown.

4.  Select the integration flow and analyze the details area to the right of the integration flow list.

5.  Under *Attachments*, click *Log current Payload*.

    You should see the message content, which consists of the details of the product associated with the value of `productIdentifier` entered in the first Content Modifier.

    This shows you that the message has been processed correctly.


