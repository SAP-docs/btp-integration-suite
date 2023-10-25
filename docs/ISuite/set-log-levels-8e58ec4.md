<!-- loio8e58ec4174764c94adb86ccbaa14af5d -->

# Set Log Levels

Learn how to set log levels for Java-based solution components.



## Context

To set the log levels for Java-based solution components, follow the steps described in [Changing Logging Severity Levels](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/1ce54d8bd96340c9b018ac80494a06af.html?q=Changing%20Logging%20Severity%20Levels) of the Edge Lifecyle Management guide. As a preparation, you've to retrieve the initial logging configuration.



## Procedure

1.  To retrieve the logging configuration, use the command: `kubectl get cm -n egde-icell edge-icell-loggers -o yaml >edge-icell-loggers.yaml`, to create a file: `edge-icell-loggers.yaml`.

2.  Open this file and edit log levels as needed or requested by SAP support

    Example for logger `com.sap.it.op`:

    `<logger name="com.sap.it.op" level="WARN"/>` change this line to:

    `<logger name="com.sap.it.op" level="DEBUG”/>` and save the file.

    Possible log severity levels: DEBUG, INFO, WARN, ERROR

3.  Open Edge Lifecycle Management.

4.  Go to the *Edge Nodes* tab.

5.  Select the Edge Node for which you want to edit the logging severity level of the solution deployment.

6.  Select solution Edge Integration Cell in the *Deployments*section.

7.  Choose*Edit* in the *Logging* section and upload the new configuration file `edge-icell-loggers.yaml`.

8.  Save you entries.




<a name="loio8e58ec4174764c94adb86ccbaa14af5d__result_jkw_dnm_fvb"/>

## Results

Log settings are changed. You can always revert log severity levels to default.

