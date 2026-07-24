<!-- loiob8058d2388fd40ce82c3e74d86db3b5f -->

# Fix Database Connectivity Issues

Resolve database-validator-job failures during Edge Integration Cell \(EIC\) deployment, upgrade, or service modification.



## Context

The Edge Integration Cell \(EIC\) includes a *DB Validator* job that performs an automated database connectivity check during deployment, upgrade, or service modification operations. If this check fails, the operation stops and you may encounter one of the following errors:

**Installation Error**:

`Action [Create or Update Helm Custom Resource (Deploy Component [Postgres (250465)], Deploy Solution [Edge Integration Cell Services (44253)], Deploy Solution [Edge Integration Cell (44252)])] failed: Custom Resource from kind [HelmRelease] reached FAILED state when performing [InstallFailed], due to [failed to install release: failed post-install: 1 error occurred: * job database-validator-job failed: BackoffLimitExceeded , Helm logs:]`

**Update Error**:

`Action [Create or Update Helm Custom Resource (Update Component [Postgres (250465)], Update Instance [Edge Integration Cell Services (44253)])] failed: Custom Resource from kind [HelmRelease] reached FAILED state when performing [UpdateFailed], due to [failed to update release: post-upgrade hooks failed: 1 error occurred: * job database-validator-job failed: BackoffLimitExceeded , Helm logs: preparing upgrade for edge-integration-cell-services-postgres-001;performing update for edge-integration-cell-services-postgres-001;creating upgraded release for edge-integration-cell-services-postgres-001;waiting for release edge-integration-cell-services-postgres-001 resources (created: 0 updated: 2 deleted: 0);warning: Upgrade "edge-integration-cell-services-postgres-001" failed: post-upgrade hooks failed: 1 error occurred: * job database-validator-job failed: BackoffLimitExceeded ;]`



## Procedure

1.  Look for pods named `database-validator-job-<suffix>`.

2.  If the pod status is *Error*:

    1.  Read the pod logs to find the reason for the error.

    2.  Resolve the underlying issue \(potentially modifying the EIC Services properties\).


3.  If the pod status is *StartError*: The pods failed to start and did not generate any logs.

    1.  Inspect the pod details by running `kubectl describe pod <pod-name>`. Check the Events section for an error similar to: `Warning Failed 5m34s kubelet Error: failed to create containerd task: failed to create shim task: OCI runtime create failed: runc create failed: unable to start container process: error during container init: invalid environment variable "DB_ROOT_CERT": contains nul byte (\x00).` This indicates that the database root certificate is not in the required format.

    2.  Modify the EIC Services properties to upload a database root certificate file that meets the following requirements:

        -   **Format**: PEM \(Base64 ASCII\)
        -   **Size**: Maximum 5 kB
        -   **Content**: Includes only the Root CAs necessary for the connection


4.  Retry the EIC deployment or upgrade.


