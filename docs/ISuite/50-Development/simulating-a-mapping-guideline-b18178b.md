<!-- loiob18178b02cca4c129d8706192a3f5b62 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Simulating a Mapping Guideline

Learn how to simulate a mapping guideline.



## Procedure

1.  Open your mapping guideline and navigate to the *Mapping* tab.

2.  Expand all nodes to see if the mapping is finalized and choose *Simulate* to perform an embedded simulation in the MAG itself. There are two different ways to simulate the MAG:

    1.  *Simulate with MIG Example Data*: This simulates the MAG with the existing sample MIG data.

    2.  *Simulate with Payload Data...*: This prompts you to upload a sample payload file \(XML or EDI flat file\) as *Source Payload* for the MAG simulation. For more information, see the blog [Integration Advisor – direct support of EDI payloads](https://community.sap.com/t5/technology-blog-posts-by-sap/integration-advisor-direct-support-of-edi-payloads/ba-p/13779418).

        Optionally, you can also upload an *Expected Target Payload* \(XML or EDI flat file\). After the simulation, you can use this file to compare the simulated and expected values.

        > ### Note:  
        > The EDI flat file is supported only for EDI-based type systems such as ASC X12, Odette, TRADACOMS, and UN/EDIFACT and its subsets.


    > ### Note:  
    > If there are errors in the simulation, the *Error* dialog displays the error with the specific node and a direct link to access the node for easy resolution.

3.  A new field *Simulation Data* appears above the source structure displaying the type of simulation that was carried out.

    If you've uploaded an expected target payload, there's an additional field for *Expected Data*, as well as the number of differences that come up during the comparison of the two datasets.

    You can re-run the simulation based on the option you chose by using the <span class="SAP-icons-V5"></span> Rerun simulation button that appears next to this field.

4.  A new column *Simulation Data* appears in the *Source* and *Target* structure populated with data related to the mapping for each node:

    -   The rows with values on the source structure are the input values from the source MIG.
    -   The values found in the target structure are the transformed input values.
    -   If there are more than one instance of a leaf node in the simulation data, they are denoted by the navigation buttons <span class="SAP-icons-V5"></span> <span class="SAP-icons-V5"></span>. These buttons allow you to navigate to the other occurrences of the payload values.
    -   The navigation button <span class="SAP-icons-V5"></span><span class="SAP-icons-V5"></span> is also displayed for a group node if it occurs at least once in the simulation data.
    -   The <span class="BusinessSuiteInAppSymbols-V2"></span> icon denotes the input value on the source message or the transformed value on the target message is empty.

    -   The <span class="BusinessSuiteInAppSymbols-V2"></span> icon denotes that the leaf node doesn't exist in the simulated data.

5.  **If you've uploaded an expected target payload**, the additional column *Expected Data* appears in the target structure. The target MIG tree expands automatically, and the nodes show the comparison status for group node instances \(based on instance count\) and leaf node data \(based on value\).

    Use the buttons <span class="SAP-icons-V5"></span> Previous Difference and <span class="SAP-icons-V5"></span> Next Difference to navigate through the differences that were found in the comparison of the simulation data and the expected data.

6.  Choose a mapping entity in the source or the target structure to view the mapping after simulation.

7.  If you've added any conditions on a source leaf node to control the instances of a target group node, you can view the following details of that conditional mapping under the *Condition* tab of that mapping entity.

    -   The nodes that are involved in the conditional mapping

    -   The status of the creation of a target node based on the input provided in the mapping

        The target nodes that are not created due to the conditional mapping are also denoted with the <span class="BusinessSuiteInAppSymbols-V2"></span> icon in the mapping structure.


    > ### Note:  
    > Wherever conditional mapping is involved, the creation of the target node instances depends solely on the condition defined under the conditional mapping.

8.  For target group nodes with conditional mapping, the *Simulation Data* column only displays the instances of the node which fulfills the condition criteria. If you want to see all the instances of the node, irrespective of whether they fulfill the condition or not, choose <span class="BusinessSuiteInAppSymbols-V2"></span>.

    If you've uploaded an expected target payload, the comparison results are hidden in this case.

9.  After a MAG simulation has run, choose <span class="SAP-icons-V5"></span> Download simulation result to save the target payload resulting from the simulation. The default option is *Download as XML*, in the Cloud Integration XML format without qualifier suffixes from Integration Advisor.

    If the target message is an EDI message from one of the type systems ASC X12, Odette, TRADACOMS, UN/EDIFACT or one of its subsets, you can also choose *Download as EDI Flat File*, as an alternative to the XML file. For more information, see the blog [Integration Advisor – Download MAG Simulation Result as EDI Payload](https://community.sap.com/t5/technology-blog-posts-by-sap/integration-advisor-download-mag-simulation-result-as-edi-payload/ba-p/14177249).

10. If you don't need the simulation data anymore, you can clear it by choosing :x:. The data from any expected target payloads is cleared as well.


