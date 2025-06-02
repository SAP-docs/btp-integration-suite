<!-- loiob0106a14f3bc4137b456228e56b04ca9 -->

# Managing Cluster Lock in Custom Adapters

Custom Integration Adapters provide a mechanism to acquire cluster-level locks, ensuring that specific actions \(e.g., message processing\) are executed by only one worker or node instance at a time. This prevents duplicate processing and maintains data consistency across distributed environments.



<a name="loiob0106a14f3bc4137b456228e56b04ca9__prereq_dyq_qh5_jfc"/>

## Prerequisites

-   You have the necessary permissions to utilize the public APIs. See [SDK API](sdk-api-c5c7933.md).
-   Your adapter should be configured to support cluster lock functionalities. See [Adapter Development Prerequisites](adapter-development-prerequisites-5638d4a.md).



<a name="loiob0106a14f3bc4137b456228e56b04ca9__context_bkf_xj5_jfc"/>

## Context

The `LockManager` interface offers following methods to acquire, release, and manage cluster-level locks.



### 

-   **newLock**: Creates a new lock with a specified expiration duration.

    > ### Source Code:  
    > ```
    > Lock lock = lockManager.newLock("vendor", "component", "lockName", Duration.ofMinutes(30));
    > ```

-   **newRuntimeLock**: Creates a runtime lock that is automatically released if the node or worker instance restarts.

    > ### Source Code:  
    > ```
    > Lock lock = lockManager.newRuntimeLock("vendor", "component", "lockName", Duration.ofMinutes(30));
    > ```

-   **getAllLocksByVendor**: Retrieves all locks associated with a specific vendor.

    > ### Source Code:  
    > ```
    > Set<LockInfo> locks = lockManager.getAllLocksByVendor("vendor");
    > ```

-   **getAllLocks**: Retrieves all locks for the current tenant.

    > ### Source Code:  
    > ```
    > Set<LockInfo> locks = lockManager.getAllLocks();
    > ```

-   **releaseLocks**: Releases a set of locks identified by their lock IDs.

    > ### Source Code:  
    > ```
    > int releasedCount = lockManager.releaseLocks(lockIds);
    > ```

-   **isLockAcquired**: Checks if a lock with a specific ID is currently held.

    > ### Source Code:  
    > ```
    > boolean isAcquired = lockManager.isLockAcquired("lockId");
    > ```




## Procedure

1.  Obtain LockManager Service.

    > ### Source Code:  
    > ```
    > LockManager lockManager = ITApiFactory.getService(LockManager.class, null);
    > ```

2.  In your adapter's metadata, define the `adpaterInstanceID` property:

    > ### Source Code:  
    > ```
    > <Metadata>
    >   <AdditionalMetadata>
    >     <Name>requiredIntegrationFlowProperties</Name>
    >     <Value>adapterInstanceID</Value>
    >     <GuiLabels>
    >       <Label language="en"/>
    >     </GuiLabels>
    >   </AdditionalMetadata>
    > </Metadata>
    > ```

    This adapterInstanceId now can be accessed in your adapter runtime using an endpoint field. You can now use this value as lockname.

3.  Use the `newLock` or `newRuntimeLock` method to create a lock.

    > ### Source Code:  
    > ```
    > Lock lock = lockManager.newLock("vendor", "component", "lockName", Duration.ofMinutes(30));
    > ```

4.  Use the `tryLock` method to attempt acquiring the lock.

    > ### Source Code:  
    > ```
    > boolean lockStatus = lock.tryLock();
    > ```

5.  Once the task is completed, release the lock.

    > ### Source Code:  
    > ```
    > lock.unlock();
    > ```

    API Interface:

    > ### Sample Code:  
    > ```
    > package com.sap.it.api.clusterlock;
    > 
    > import com.sap.it.api.ITApi;
    > import com.sap.it.api.clusterlock.types.LockInfo;
    > 
    > import java.time.Duration;
    > import java.util.Set;
    > import java.util.concurrent.locks.Lock;
    > 
    > /**
    >  * LockManager helps adapter developers to acquire, release and get information related to cluster level locks
    >  * 
    >  */
    > public interface LockManager extends ITApi {
    > 
    >     /**
    >      * Gets a new {@link Lock} object which will be used for acquiring the lock
    >      * @param vendor - this should be the vendor name of the adapter. 'SAP' vendor name is reserved for internal usage. Length restricted to 20
    >      * @param component - this should be the adapter name which is used while creating the adapter. Length restricted to 20
    >      * @param lockName - a unique lockName (suggestion: Use either bundle symbolic name or the channelId)
    >      * @param expireAfter - time period after which lock expires
    >      * @return {@link Lock}
    >      */
    >     Lock newLock(String vendor, String component, String lockName, Duration expireAfter);
    > 
    >     /**
    >      * Gets a new {@link Lock} object which will be used for acquiring the lock with Runtime Scope.
    >      * This lock will be automatically released by the cleanup job if the node/worker/instance restarts due to a crash, software update, or OOM (Out of Memory) error.
    >      * @param vendor - this should be the vendor name of the adapter. 'SAP' vendor name is reserved for internal usage. Length restricted to 20
    >      * @param component - this should be the adapter name which is used while creating the adapter. Length restricted to 20
    >      * @param lockName - a unique lockName (suggestion: Use either bundle symbolic name or the channelId)
    >      * @param expireAfter - time period after which lock expires
    >      * @return {@link Lock}
    >      */
    >     Lock newRuntimeLock(String vendor, String component, String lockName, Duration expireAfter);
    > 
    >     /**
    >      * Gets all {@link LockInfo}s by vendor name for the current tenant
    >      * @param vendor - this should be the vendor name of the adapter. 'SAP' vendor name is reserved for internal usage. Length restricted to 20
    >      * @return {@link Set} of {@link LockInfo}s
    >      */
    >     Set<LockInfo> getAllLocksByVendor(String vendor);
    > 
    >     /**
    >      * Gets all {@link LockInfo}s for the current tenant
    >      * @return {@link Set} of {@link LockInfo}s
    >      */
    >     Set<LockInfo> getAllLocks();
    > 
    >     /**
    >      * Releases all the locks held with lockIds
    >      * @param lockIds - lock identifiers
    >      * @throws com.sap.it.api.clusterlock.types.LockException (is a RunTimeException)in case of failures
    >      * @return number of released locks
    >      */
    >     int releaseLocks(Set<String> lockIds);
    > 
    >     /**
    >      * Ruturns true if lock with lockId is held else false
    >      * @param lockId - lock identifier
    >      * @return true or false
    >      */
    >     boolean isLockAcquired(String lockId);
    > ```

    **Troubleshooting**


    <table>
    <tr>
    <th valign="top">

    Issue
    
    </th>
    <th valign="top">

    Impact
    
    </th>
    <th valign="top">

    Mitigation
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Database connection unavailability
    
    </td>
    <td valign="top">
    
    Inability to create or release locks.
    
    </td>
    <td valign="top">
    
    Implement retry mechanisms in the adapter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Lock deletion job failure
    
    </td>
    <td valign="top">
    
    Locks may persist beyond their expiration, preventing new lock creation.
    
    </td>
    <td valign="top">
    
    Implement retry mechanisms in the adapter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Deployment inconsistencies
    
    </td>
    <td valign="top">
    
    Potential for overload on a single node during deployment.
    
    </td>
    <td valign="top">
    
    Implement random wait times for lock acquisition to distribute load evenly.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Unreleased locks due to system failures
    
    </td>
    <td valign="top">
    
    Message processing downtime.
    
    </td>
    <td valign="top">
    
    Release the lock from monitoring manually. See [Manage Locks](../manage-locks-8871b61.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Inconsistent shutdown
    
    </td>
    <td valign="top">
    
    Potential downtime if old worker nodes fail to shut down properly.
    
    </td>
    <td valign="top">
    
    Release the lock from monitoring manually. See [Manage Locks](../manage-locks-8871b61.md).
    
    </td>
    </tr>
    </table>
    



<a name="loiob0106a14f3bc4137b456228e56b04ca9__result_wl5_snb_kfc"/>

## Results

Your custom adapters can now execute critical tasks by a single node with cluster-level locks, preventing duplicate processing and preserving system integrity.

