<!-- loio6a060ffd345a4c4ab545d5c31cb24119 -->

# Modify Edge Integration Cell Solution Deployment Properties



## Context

Use Edge Lifecycle Management \(Edge LM\) to modify the solution deployment properties of Edge Integration Cell solution.

During the upgrade the service keys for connectivity with SAP Integration Suite and BTP services are rotated as needed. For key rotation, the `modify` operation can be used even without changing specific solution properties.

> ### Note:  
> You must modify the Edge Integration Cell deployment solution properties \(without changing any parameter\) with every new solution release if an upgrade is skipped by SAP or delayed by you. Else, deployment and undeployment of content will be blocked.

To modify the Edge Integration Cell deployment solution properties, proceed as follows:



## Procedure

1.  Open the *Edge Lifecyle Management* UI.

2.  Go to the *Edges Nodes* tab.

3.  Select the Edge Node where you want to update the solution properties.

4.  Select the solution where you want to update the solution properties.

5.  From the *Operations* context menu, choose *Modify Configuration*.

    The system opens a dialog box where you can update solution deployment properties.

6.  Choose *Update*.




<a name="loio6a060ffd345a4c4ab545d5c31cb24119__result_fjz_kyc_2vb"/>

## Results

The solution is updated based on modified helm charts.

