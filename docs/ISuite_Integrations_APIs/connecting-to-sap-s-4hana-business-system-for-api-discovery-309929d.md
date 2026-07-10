<!-- loio309929d9ce6c4e7c9b903ccb6f5b4df9 -->

# **Connecting to SAP S/4HANA Business System for API Discovery**

Create a destination in SAP BTP cockpit to enable discovery of APIs from an SAP S/4HANA Cloud system.

**Before you begin:** Ensure that an administrator has created a formation that includes an SAP Integration Suite system and one or more SAP S/4HANA Cloud systems, all assigned to a common subaccount. See, [Setting Up System Landscape for SAP Integration Suite](https://help.sap.com/docs/btp/sap-business-technology-platform/enabling-system-landscape-for-sap-integration-suite?version=Cloud).

Create a destination for the SAP S/4HANA Cloud discoverable system using one of the following methods:

-   **Using the Cloud Extensibility Service**

    You can create a destination for the consumption bundle directly in the SAP BTP cockpit using the SAP S/4HANA Cloud Extensibility service. For step-by-step instructions, see [Create an SAP S/4HANA Cloud Extensibility Service Instance in the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/create-sap-s-4hana-cloud-extensibility-service-instance-in-cloud-foundry-environment?version=Cloud).

    When configuring the communication arrangement and selecting the authentication type for API access, you can directly enter the communication scenario ID into the predefined template \(if available\). Also, be sure to follow only the steps in the *Procedure* section and skip those in the *Next Steps* section.

    This eliminates the need to define a JSON file. Additionally, ensure that the following properties are present as part of the created destination:

    -   x-correlation-id
    -   x-system-id
    -   x-system-type

    > ### Note:  
    > If destination creation fails, you can create the destination manually.

-   **Creating a Destination Manually**
    1.  Logon to the SAP BTP Cockpit and navigate to your source subaccount.
    2.  Choose the *Connectivity* \> *Destinations* tab in the left-hand pane.
    3.  Choose *Create* and in the *Create New Destination* popup, select *From Scratch* to create a new destination manually.
    4.  In *Destination Details* section, fill in all the required details:

        Provide the *Name*, *Type*, *Proxy Type*, and *Description*. In the *URL* field, enter the backend S/4HANA API endpoint.

        Fill in the *Authentication* details required to connect to S/4HANA.

        In the *Additional Properties* section, add the following:


        <table>
        <tr>
        <th valign="top">

        Additional Properties
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *x-correlation-id* 
        
        </td>
        <td valign="top">
        
        The property identifies the consumption bundle and its APIs that are exposed by the SAP S/4HANA Cloud system. The destination also provides the required credentials to consume the bundle and use it for further development in the SAP Business Application Studio.

        Use the following format:`"sap.s4:communicationScenario:" <Communication_Scenario_id>` \(For example, use the following format: `sap.s4:communicationScenario: SAP_COM_0316`\)
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *x-system-type* 
        
        </td>
        <td valign="top" rowspan="2">
        
        Properties that uniquely identify the local tenant of the registered SAP S/4HANA Cloud system.

        **Example**:

        x-system-type: SAP S/4HANA Cloud  
          
        

        x-system-id : 730291359
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *x-system-id* 
        
        </td>
        </tr>
        </table>
        
    5.  Choose *Save*.


