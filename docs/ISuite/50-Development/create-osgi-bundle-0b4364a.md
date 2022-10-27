<!-- loio0b4364a961874ea8b98b89f7d4838914 -->

# Create OSGi Bundle

OSGi bundles are normal jar components with extra manifest headers, which you use to develop adapters.



## Prerequisites

-   You have the required jar file.

-   You have setup the eclipse with plug-in development enabled.



## Context

To integrate camel component into Cloud Integration framework, camel component and its dependencies should be in a OSGi bundle. To convert the jar file to OSGi bundle, execute the following steps:



## Procedure

1.  In Eclipse, go to *File* \> *New* \> *Project*.

2.  In the *New Project* wizard, search for *Plug-in Development* and select *Plug-in from Existing JAR Archives*.

3.  Choose *Next*.

4.  If you have the JAR in the current workspace, then choose *Add* and select the JAR file from the JAR selection dialog.

5.  If you don't have the JAR in your current workspace, then choose *Add External* and select the required JAR file from your local system.

6.  Choose *Next*.

7.  In the *Plug-in Project Properties* dialog, specify a name in the *Project name* field.

8.  In the *Execution Environment* drop-down list box, select java version JavaSE-1.7 or lower.

9.  In the *Target Platform*, select *an OSGi framework* option.

10. Choose *Finish*.

11. Select the ***MANIFEST.MF*** file of your project, and go to *Runtime* tab.

12. Choose *Add*.

13. Select the required export packages.

14. Choose *OK* and save the MANIFEST.MF file.

15. Right click on the project and choose *Export*.

16. In the *Export* wizard search for *plug-in Development* and choose *Deployable plug-ins and fragments*.

17. Choose *Next*.

18. Choose *Browse* and select the directory where you want to generate the the plug-in.

19. Choose *Finish*.




## Results

In the directory, you can see the plug-ins folder with the OSGi bundle of jar file.

