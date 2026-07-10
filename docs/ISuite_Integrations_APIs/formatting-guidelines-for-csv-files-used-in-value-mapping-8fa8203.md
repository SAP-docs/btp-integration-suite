<!-- loio8fa8203aff104e938bd7f51dd9daa3e1 -->

# Formatting Guidelines for CSV Files used in Value Mapping

SAP Cloud Integration supports importing of CSV files exported from process integration \(PI\) systems into value mapping. This allows you to reuse the value mappings from your PI system and save time.

The CSV files that can be imported to the value mapping should adhere to the same formatting guidelines as the CSV exported from PI systems. Here's a typical example of a valid CSV file that can be imported into value mapping:

> ### Sample Code:  
> ```
> ,Country1|Receiver1,Country1|Code1
> Receiver_US,N75_AAEX_FileSystem_XiPattern2|,US
> Receiver_DE,N75_AAEX_FileSystem_XiPattern1|,DE
> Receiver_DE,N75_AAEX_FileSystem_XiPattern3|,UK
> ```

From the example above, we can infer the following guidelines for a CSV file that can be imported in value mapping:

-   Only comma \(**,**\) can be used as the delimiter.
-   The *Agency ← → Identifier* is separated by the pipe \(**|**\) character.
-   Only UTF-8 encoded CSV files are supported.


