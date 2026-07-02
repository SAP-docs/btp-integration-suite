<!-- loio586ddaa4afab48259f1169a0ee1a49da -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Exporting Agreement List

Learn how to export a list of all agreements in your system.



## Context

You can export the list of trading partner agreements as a Microsoft Excel spreadsheet for offline analysis, sharing, or reporting purposes. The exported file contains key agreement details and is saved automatically to your default browser download location.

For agreements with multiple versions, only the **latest version** is included in the export.



## Procedure

1.  In SAP Integration Suite, go to *Design* \> *B2B Scenarios*.

2.  Navigate to the *Agreements* tab. The tab displays the list of agreements created in the system.

3.  In the table toolbar, choose <span class="SAP-icons-V5"></span> Export Spreadsheet.

    In the download dialog, you can modify the file name before saving the file. By default, the file name follows the format `AgreementList_YYYYMMDD-HHMMSS.xslx`, the suffix being the timestamp of the download.




## Results

The exported spreadsheet contains a single sheet named `AgreementsList` with the following columns:

-   **Agreement Name**: Name of the trading partner agreement
-   **Agreement Version**: Version number of the agreement
-   **Agreement Status**: Status of the agreement at the time of the download
-   **Company/Subsidiary Name**: Short name of the company or subsidiary
-   **Trading Partner Name**: Short name of the trading partner
-   **Agreement Creation Date**: Date at which the agreement was created
-   **Agreement Created By**: User who created the agreement
-   **Agreement Link**: Direct link to the agreement in the system

