<!-- loio7e52a493ba314f6a9737fe441def3810 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Custom Loggers

You can add custom loggers when creating a new custom logging task.

You can either add custom loggers individually or mass import a list of loggers. To add them individually, follow these steps:

1.  Choose the add \(:heavy_plus_sign:\) icon in the popup window that opens when you create a new logging task.
2.  Specify the *Component* and *Log Level*, and provide the *Log Location*.
3.  Choose the *Add* button to add the custom logger. You can repeat the previous steps to add all the custom loggers you need.
4.  When you're done, you can choose *Run* to initiate the diagnosis.



To mass import a list of loggers, choose the import \(<span class="SAP-icons-V5"></span>\) icon in the popup window that opens when you create a new logging task. Paste your list of loggers in the *Custom Logger* field. Make sure that you enter one log location per line and that the data follows this format: <Component\>,<Log Location\>,<Log Level\>. The system adds each new location to the custom logger and overwrites any matching existing locations.

> ### Note:  
> For mass import, the components should have an internal name, such as edge-api. The supported log levels are *TRACE*, *DEBUG*, *INFO*, *WARNING*, *ERROR*, and *OFF*.

You can edit and delete your custom loggers later by choosing the respective :pencil2: icons next to the logger you want to modify.

