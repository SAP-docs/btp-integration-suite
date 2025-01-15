<!-- loiob18178b02cca4c129d8706192a3f5b62 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Simulating a Mapping Guideline

This chapter shows you how to simulate a mapping guideline.

1.  Open your mapping guideline and navigate to the *Mapping* tab.

2.  Expand all nodes to see if the mapping is finalized and choose *Simulate* to perform an embedded simulation in the MAG itself. There are two different ways to simulate the MAG:

    1.  *Simulate with MIG Example Data*: This simulates the MAG with the existing sample MIG data.

    2.  *Simulate with Payload Data...*: This prompts you to upload a sample payload file \(XML or EDI flat file\) for the MAG simulation.

        > ### Note:  
        > The EDI flat file is supported only for EDI based type systems such as ASC X12, Odette, TRADACOMS, and UN/EDIFACT and its subsets.


    > ### Note:  
    > If there are errors in the simulation, the *Error* dialog displays the error with the specific node and a direct link to access the node for easy resolution.

3.  A new field *Simulation Data* appears above the source structure displaying the type of simulation that was carried out.

    You can also re-run the simulation based on the option you chose using the <span class="SAP-icons-V5"></span> button that appears next to this field.

4.  A new column *Simulation Data* appears in the *Source* and *Target* structure populated with data related to the mapping for each node:
    -   The rows with values on the source structure are the input values from the source MIG.
    -   The values found in the target structure are the transformed input values.
    -   If there are more than one instance of a leaf node in the simulation data, they are denoted by the navigation buttons <span class="SAP-icons-V5"></span> <span class="SAP-icons-V5"></span>. These buttons allow you to navigate to the other occurences of the payload values.
    -   The navigation button <span class="SAP-icons-V5"></span><span class="SAP-icons-V5"></span> is also displayed for a group node if it occurs atleast once in the simulation data.
    -   The <span class="BusinessSuiteInAppSymbols-V2"></span> icon denotes the input value on the source message or the transformed value on the target message is empty.

    -   The <span class="BusinessSuiteInAppSymbols-V2"></span> icon denotes that the leaf node does not exist in the simulated data.

5.  Choose a mapping entity in the source or the target structure to view the mapping after simulation.
6.  If you have added any conditions on a source leaf node to control the instances of a target group node, you can view the following details of that conditional mapping under the *Condition* tab of that mapping entity.

    -   The nodes that are involved in the conditional mapping

    -   The status of the creation of a target node based on the input provided in the mapping.

        The target nodes that are not created due to the conditional mapping are also denoted with the <span class="BusinessSuiteInAppSymbols-V2"></span> icon in the mapping structure.


    > ### Note:  
    > Wherever conditional mapping is involved, the creation of the target node instances depends solely on the condition defined under the conditional mapping.

7.  For target group nodes with conditional mapping, the *Simulation Data* column only displays the instances of the node which fulfills the condition criteria. If you want to see all the instances of the node, irrespective of whether they fulfill the condition or not, choose <span class="BusinessSuiteInAppSymbols-V2"></span>

