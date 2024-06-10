<!-- loioe60f7061fe4b45d69d028b24d5a76901 -->

# Developing Script and Script Collection

Cloud Integration lets you create and upload scripts, assemble them into script collection artifacts, and reuse them across different integration artifacts.



<a name="loioe60f7061fe4b45d69d028b24d5a76901__section_m2m_mcr_mpb"/>

## Script

At times, when you need capabilities beyond native functions of Cloud Integration, you can use your own custom scripts in your integration artifacts. For example, you can use scripts for complex transformations, handle exceptions, or to read or modify headers in adapters. See [Script Use Cases](script-use-cases-148851b.md). Cloud Integration supports the scripting languages like Groovy and JavaScript.



### How to Use Scripts

You can create and consume script in different methods:

-   Create a script step in an integration artifact that is specific to that artifact. See [Define a Local Script Step](define-a-local-script-step-03b32eb.md).

-   Create a reusable bundle of script collection and refer a script from the collection in the script step of an integration artifact. [Creating a Script Collection](creating-a-script-collection-824bff0.md).




<a name="loioe60f7061fe4b45d69d028b24d5a76901__section_brv_ncr_mpb"/>

## Script Collection

Script Collection is an artifact in itself that is a bundle of scripts. Create a script collection within an integration package so that you create scripts in it and then reuse the bundle of scripts across any number of integration artifacts within that package. The supported resources are Groovy scripts, JavaScripts, and Jar files.



### Workflow

A typical workflow to rightly use a script collection is as follows:

1.  [Creating a Script Collection](creating-a-script-collection-824bff0.md) in an integration package.

2.  [Creating Scripts in a Script Collection](creating-scripts-in-a-script-collection-ed9b52c.md)

3.  [Consuming a Script Collection](consuming-a-script-collection-1b801fa.md)

4.  [Deploying a Script Collection](deploying-a-script-collection-95cb2d9.md)

5.  [Save and Deploy the Integration Flow](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/33a5123e424c431bbe55bcfba971c230.html "Save and deploy the integration flow on the tenant to process it.") :arrow_upper_right:.




<a name="loioe60f7061fe4b45d69d028b24d5a76901__section_izl_glr_4pb"/>

## Why Use a Script Collection

Make an informed decision before you use locally defined scripts and script collections.

-   **Reusability** – Without a script collection, you manually upload the same script resource in multiple integration artifacts to achieve a simple goal. Using script collection, you deploy the scripts and refer them in multiple integration artifacts instead of manually uploading every time.

-   **Reduce Maintenance Efforts** – Now that you only refer the script from a single place, you only have to edit the script once if there are changes needed.

-   **Reduce File Size and Memory Usage** – By avoiding multiple instances of upload, you reduce the file size of large integration flows, and reduce the storage space.

-   **Avoid Duplicates** – Hassle-free access to the script files by avoiding multiple duplicate copies of the same script, which can cause confusion.


