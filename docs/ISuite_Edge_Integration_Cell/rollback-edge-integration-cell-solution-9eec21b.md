<!-- loio9eec21b251224d26bc04a27cc985da88 -->

# Rollback Edge Integration Cell Solution

Use Edge Lifecycle Management \(Edge LM\) to rollback deployment of Edge Integration Cell solution to the last suceessful deployed version when an upgrade or modify configuration operation fails.



<a name="loio9eec21b251224d26bc04a27cc985da88__prereq_slw_yxm_1bc"/>

## Prerequisites

The upgrade or modify configuration operation failed on the deployed Edge Integration Cell solution.



## Context

You can rollback only to the last successfully deployed solution version.



## Procedure

1.  Open the *Edge Lifecycle Management* UI.

2.  Go to the *Edge Nodes* tab.

3.  Choose the Edge Node where upgrade or modify operation failed.

4.  Select the solution where you want to perform the rollback operation.

5.  From the *Operations* context menu, choose *Rollback*.

    > ### Note:  
    > When rolling back a solution version with dependencies, those dependencies will not be rolled back or modified. If any parent dependencies can't be satisfied with rollback, the operation may not be permitted. In this case, you will see a warning message.




<a name="loio9eec21b251224d26bc04a27cc985da88__result_izl_fgn_1bc"/>

## Results

-   The solution is rolled back to its last successfully deployed version.
-   If the Rollback operation is unsuccessful, you can choose *Retry* from the *Operations* context menu to attempt rollback operation again.

