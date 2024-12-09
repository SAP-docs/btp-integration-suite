<!-- loio5a3ec6d3663343ff95cfa6f78c6e7149 -->

# Log the Behavior of an Integration Flow

Log the behavior of an integration flow to collect data for later troubleshooting.

In addition to the default logging provided by SAP Integration Suite , you might need to log additional custom data to allow efficient root-cause analysis.



<a name="loio5a3ec6d3663343ff95cfa6f78c6e7149__section_l5y_hmr_tjb"/>

## Implementation

SAP Integration Suite provides an API that allows you to write additional data to the message processing log. Properties in the form of name-value pairs, and attachments to the complete log can be written. For example, to identify the message processing log of a certain execution of the business process, it can help to write additional identifiers, such as a purchase order ID, to the message processing log.

> ### Tip:  
> In general, to reduce the data volume to a bare minimum; additional log data must only be written to the message processing log if message processing fails.

To act on errors that occur during message processing, you might need to notify someone about the error situation. You can extend an integration flow with such custom alerting. You can use a Mail adapter to send the error details to a recipient for further processing.

**Related Information**  


[Define a Local Script Step](define-a-local-script-step-03b32eb.md "Learn how to use a script step that’s specific to an integration artifact to create custom scripts (JavaScript or Groovy Script).")

