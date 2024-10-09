<!-- loio52dba2095dda48c9bc8bc8ca989c51b4 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Enable Garbage Collection Logging

Learn how to enable Garbage Collection \(GC\) logging for worker pods.



## Context

You can enable GC logging by extending the runtime parameter JAVA\_OPTS.



<a name="loio52dba2095dda48c9bc8bc8ca989c51b4__steps_arm_ypj_pcc"/>

## Procedure

1.  Go to *Runtime Parameters* and select the *Worker* component.

2.  Choose :pencil2: to set a custom value for the JAVA\_OPTS parameter.

3.  Enter the custom value `-Xlog:gc*:file=log/gc.log:time` and choose *Apply*.

    > ### Note:  
    > Applying changes restarts all worker pods.


