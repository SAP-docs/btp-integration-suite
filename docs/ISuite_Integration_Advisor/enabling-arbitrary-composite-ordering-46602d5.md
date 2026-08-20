<!-- loio46602d50d33843718bd72732f832b4b5 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Enabling Arbitrary Composite Ordering

Automatic reordering of repeating composite data elements in UN/EDIFACT segments to match your message implementation guideline sequence. Use this feature to handle business partner payloads where composite instances arrive in varying orders, eliminating the need for complex mapping logic to accommodate different positioning.



## Prerequisites

-   This feature is only available for UN/EDIFACT type systems.
-   The segment must have repeating composites, like `PIA`, `GIN`, or `GIR`.
-   All selected composite data elements must be qualified, use exactly one qualifier, and have only one qualification variant.
-   All qualifier values are unique across all composite data elements.
-   The message payloads only contain qualifier values configured in the MIG. Within one segment instance, each qualifier value is only used once.



## Context

In certain EDIFACT segments \(for example, `PIA`\), the same composite element can appear multiple times. Business partners can send these repeating composite instances in any order that's valid according to the EDIFACT standard. This variation in order can cause mapping errors when a mapping assumes a fixed position for each composite instance.

Integration Advisor can automatically reorder the repeating composite instances in the incoming payload to match the order defined in your message implementation guideline. No complex mapping logic is required.

The feature only works if you've applied **qualification** to the repeating composites. The qualifier helps distinguish, for example, buyer part number and supplier part number. Without qualification, the system can't determine the intended order.



## Procedure

1.  Go to *Design* \> *MIGs* and open the message implementation guideline you want to work with.

2.  In the *Structure* tab, choose *Edit*.

3.  Select a segment that has repeating composites. It's marked by grayed out <span class="SAP-icons-V5"></span> Arbitrary Ordering of Composites icon. All repeating composites must be qualified.

4.  In the *Details* tab, go to the *Complex Type Properties* section.

5.  Optionally, choose *Validate* to check if the selected segment fulfills the recommended usage pattern. Review the validation results, but note that the validation only serves as advice and doesn't block you from enabling the feature even if not all prerequisites are fulfilled. The feature can still work if not all prerequisites are met, but it's unlikely in cases with complex payloads.

6.  Select the checkbox *Enable Arbitrary Ordering of Composites* and save your changes.




## Results

The <span class="SAP-icons-V5"></span> Arbitrary Order of Composites icon is now blue to show that the feature is enabled.

During preprocessing, Integration Advisor now automatically sorts the composites according to the order defined in the message implementation guideline.

