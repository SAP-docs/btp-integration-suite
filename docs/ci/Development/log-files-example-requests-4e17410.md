<!-- loio4e17410cfa164fc2b3a6f97181678412 -->

# Log Files Example Requests



You find various example requests on SAP Business Accelerator Hub at:

[https://api.sap.com/api/LogFiles/](https://api.sap.com/api/LogFiles/)

For more specific example requests, see the following list:



-   HTTP access files

    -   `https<tmn>/api/v1/LogFileArchives(Scope='all',LogFileType='http',NodeScope='worker')/$value`

        Downloads a log file \(zip\) archive that contains all existing HTTP access log files \(specified by `Scope='all'`

    -   `https://<tmn>/api/v1/LogFileArchives(Scope='latest',LogFileType='http',NodeScope='worker')/$value`

        Downloads a log file \(zip\) archive that contains the latest HTTP access log file per runtime node \(specified by `Scope='latest'`\). The zip archive for the scope `latest` contains only a single log file for each runtime node. Nevertheless, if some runtime nodes have been restarted and appropriate log files still exist for the previous instances of runtime notes, these files are also downloaded.

    -   `https://<tmn>/api/v1/LogFileArchives(Scope='all',LogFileType='http',NodeScope='worker')/$value?modifiedAfter=2017-03-25T13:54:51Z`

        Downloads a log file \(zip\) archive that contains all HTTP access log files created after the indicated time \(specified by the `modifiedAfter` attribute\).

        > ### Note:  
        > When filtering using `modifiedAfter`, the API checks if access log files have been modified after the specified time. This means that the files contain entries that were created after the specified time and can contain entries that were already written before the specified time. It doesn't reflect the time when the file has been created.


-   Default trace log files

    -   `https://<tmn>/api/v1/LogFiles(Name='ljs_trace_a40a97f_2017-12-15.log ',Application='krt01iflmap')`

        Returns the metadata of a single default trace log file.

    -   `https://<tmn>/api/v1/LogFiles(Name='ljs_trace_a40a97f_2017-12-15.log ',Application='krt01iflmap')/$value`

        Downloads a single default trace log file \(as gzip file\).

    -   `https://<tmn>/api/v1/LogFileArchives(Scope='all',LogFileType=’trace’,NodeScope='worker')/$value`

        Download a log file \(zip\) archive that contains all existing default trace log files \(specified by `Scope='all'`\).

    -   `https://<tmn>/api/v1/LogFileArchives(Scope='latest',LogFileType='trace',NodeScope='worker')/$value`

        Downloads a log file \(zip\) archive that contains the latest default trace log file per runtime node \(specified by `Scope='latest'`\).



