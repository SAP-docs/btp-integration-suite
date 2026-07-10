<!-- loioa92cf80214b9477ba9d55473e3bf7adc -->

# Perform Additional Tasks in API Designer

Besides creating new APIs or editing existing APIs in the API designer, you can also do the following:

-   To model Open API JSON content in the designer, choose *Paste* \> *JSON*.
-   To model an Open ODATA API, choose *Paste* \> *OData Metadata*.
-   To convert an API written in RAML to Open API, choose *Paste* \> *RAML* 
-   To import a YAML or JSON format file from your local server, choose *Import*.
-   To download the API swagger specifications, choose *Download* and select JSON or YAML format.
-   You can generate a server stub from the API definition file. The generated server stub can be used for deploying applications locally and as well as on Cloud Foundry.
    -   From the *Generate Server Stub* dropdown menu, choose the required language in which you want to generate the server stub.
    -   In the *Project Metadata* dialog window, enter the following information:

        -   **Package Name**: The name of the package.
        -   **GroupId**: The ID of the project's group.
        -   **Artifact**: The ID of the artifact \(project\).
        -   **Artifact Version**: The version of the artifact under the specified group.

    -   Choose *Generate Project*.
    -   The server stub is downloaded in a ZIP file. The generated server code contains stub methods and a README.md file with all the information required for building applications . If you have generated a server stub for Cloud Foundry deployment, then the README.md file contains instructions for deploying application on Cloud Foundry. Each language creates a different README file. Go through it to learn about how to build and deploy the application.

-   Choose *Save* to save the modeled API. You can choose to save the modeled API with a version by choosing the option *Save as Version*.

