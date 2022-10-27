<!-- loiocfb9ffbb3df24f7e9ff9d25280767e6a -->

# Kinds of Stored Data

Integration Assessment stores SAP Integration Solution Advisory Methodology \(ISA-M\) master data predefined by SAP, ISA-M master data adapted by customers, and data associated with business solution requests and interface requests.

The following is a detailed list of all of the kinds of data stored by Integration Assessment:

-   Integration domains

-   Integration styles

-   Integration Areas

-   Applications

    Software solutions independent from the deployment model \(on-premise or cloud-based\). Integration Assessment differentiates between the following entities:

    -   Application profile: Indicates the software group, for example, SAP S/4HANA.

    -   Application instance: Indicates the runtime component, for example, SAP system ID \(SID\) `XYZ` hosted in Europe.


-   Integration technologies

    Representative middleware components independent from the deployment model. Integration Assessment differentiates between the following entities:

    -   Integration technology profile: Indicates the software group, for example, SAP Integration Suite, Cloud Integration.

    -   Integration technology instance: Indicates the runtime component, for example, SAP BTP US subaccount.


-   Business solution requests: Represents the leading object for an integration requirement from a business point of view.

-   Interface request: Represents the leading object for an integration requirement from a technical point of view.




<a name="loiocfb9ffbb3df24f7e9ff9d25280767e6a__section_ijz_nsw_psb"/>

## Stored Sensitive Information

The only sensitive information stored by Integration Assessment that can be declared as person-specific is:

-   The user ID stored by Integration Assessment when you generate a business solution request.

-   The user ID stored by Integration Assessment for the locking mechanism.


