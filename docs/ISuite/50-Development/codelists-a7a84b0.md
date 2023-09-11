<!-- loioa7a84b0fc30d439b8fd6d8406e3d387f -->

# Codelists

A codelist is a collection of acronyms and their meaningful descriptions that provide a common understanding of the code values between business partners, reducing the risks associated with business collaboration.

Codelists are developed and maintained by international Standards Developing Organizations\(SDO\). For example, the codelist ISO 3166-1 that is published by the International Organization for Standardization \(ISO\) includes values for the identification of the name of the country or other geographical entity.

Code values provide a more precise meaning to semantically generic elements in a Message Implementation Guideline \(MIG\). For example, code values can be used to qualify a generic element such as "Party" to mean either a "seller party" or a "buyer party".

You can see all the available codelists provided by a type system in the Library of Type Systems. The total number of code values appears in brackets beside any selected codelist. The complete list of code values and their descriptions are available in the Code Values tab when you select a specific codelist.

SAP Integration Suite currently supports four different types of codelists:

-   Type-system based codelists – They're provided by the type system itself and can be used only in MIGs that are based on the same type system.

-   Reusable codelists – They're provided and maintained by organizations such as ISO or United Nations - Economic Commission for Europe \(UN/ECE\). They can be used in MIGs that are based on any type system. For example, the ISO-based codelists such as country code, language code, currency code, or the UN/ECE based codelist such as measure unit code. They're represented as separate Type Systems that only contain codelists.

-   MIG codelists – They're locally defined in a MIG by the users.
-   Local codelists – They're only defined in the context of a specific element and can't be used at any other place. They're predominantly used in the context of Custom Messages.


You can identify the MIG elements that have a reference to a codelist by the corresponding checkmarks in the Codelist column. When you select an element that refers to a codelist, the Details panel opens for the selected element. The codelist tab of the Details panel shows the code values, and additional details about the codelist. You can select or deselect any code value.

