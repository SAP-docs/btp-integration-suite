<!-- loiofe81049e51af492bbd30c4591e2aa6f8 -->

# Mass Create/Change/Delete Operations in One Transaction for StringParameter, BinaryParameter, AlternativePartner, and AuthorizedUser

You can perform mass processing through an OData batch. Batch processing allows you to group multiple operations. Batch requests with one change set are allowed. One change set is treated as an atomic operation \(transaction\). Create/change/delete operations can be executed in one change set for the entity types `StringParameter`, `BinaryParameter`, `AlternativePartner`, and `AuthorizedUser`. The following example shows how.

```
POST https://<host address>/api/v1/$batch
Accept: application/json
Content-type: multipart/mixed; boundary=batch_34fcd829-64e4-4139-b880-f24aa4ee9235
--batch_34fcd829-64e4-4139-b880-f24aa4ee9235
Content-Type: multipart/mixed; boundary=changeset_845b320f-7f06-423d-b10a-a24048a27b1c
--changeset_845b320f-7f06-423d-b10a-a24048a27b1c
Content-Type: application/http
Content-Transfer-Encoding: binary

POST StringParameters?user=userAbc HTTP/1.1
Content-Length: 46
Accept: application/json
content-type: application/json

{"Pid":"partner7","Id":"sp11","Value":"sp11v"}
--changeset_845b320f-7f06-423d-b10a-a24048a27b1c
Content-Type: application/http
Content-Transfer-Encoding: binary

POST StringParameters?user=userAbc HTTP/1.1
Content-Length: 46
Accept: application/json
content-type: application/json

{"Pid":"partner7","Id":"sp12","Value":"sp12v"}
--changeset_845b320f-7f06-423d-b10a-a24048a27b1c
Content-Type: application/http
Content-Transfer-Encoding: binary

PUT StringParameters(Pid='partner2',Id='sp3')?user=AriabaUserId HTTP/1.1
Content-Length: 53
Accept: application/json
content-type: application/json

{"Value":"sp3v_modified"}
--changeset_845b320f-7f06-423d-b10a-a24048a27b1c--
--batch_34fcd829-64e4-4139-b880-f24aa4ee9235--
Batch response:
--batch_46440294-4efe-4c78-8d38-6414e44382d0
Content-Type: multipart/mixed; boundary=changeset_8a1989b1-9382-446c-8479-f9330108b1f4
--changeset_8a1989b1-9382-446c-8479-f9330108b1f4
Content-Type: application/http
Content-Transfer-Encoding: binary
HTTP/1.1 201 Created
DataServiceVersion: 2.0
Location: https://<host address>/api/v1/StringParameters(Pid='partner7',Id='sp11')
Content-Type: application/json
Content-Length: 328

{"d":{"__metadata":{"id":"https://<host address>/api/v1/StringParameters(Pid='partner7',Id='sp11')","uri":"https://<host address>/api/v1/StringParameters(Pid='partner7',Id='sp11')","type":"pd.StringParameter"},"Pid":"partner7","Id":"sp11","LastModifiedBy":"userAbc","LastModifiedTime":null,"CreatedBy":"userAbc","CreatedTime":null,"Value":"sp11v"}}
--changeset_8a1989b1-9382-446c-8479-f9330108b1f4
Content-Type: application/http
Content-Transfer-Encoding: binary
HTTP/1.1 201 Created
DataServiceVersion: 2.0
Location: https://<host address>/api/v1/StringParameters(Pid='partner7',Id='sp12')
Content-Type: application/json
Content-Length: 328

{"d":{"__metadata":{"id":"https://<host address>/api/v1/StringParameters(Pid='partner7',Id='sp12')","uri":"https://<host address>/api/v1/StringParameters(Pid='partner7',Id='sp12')","type":"pd.StringParameter"},"Pid":"partner7","Id":"sp12","LastModifiedBy":"userAbc","LastModifiedTime":null,"CreatedBy":"userAbc","CreatedTime":null,"Value":"sp12v"}}
--changeset_8a1989b1-9382-446c-8479-f9330108b1f4
Content-Type: application/http
Content-Transfer-Encoding: binary
HTTP/1.1 204 No Content
DataServiceVersion: 2.0
--changeset_8a1989b1-9382-446c-8479-f9330108b1f4--
--batch_46440294-4efe-4c78-8d38-6414e44382d0-- 
```

For more information, check out the following SAP Community blog: [Cloud Integration – Partner Directory – Mass Configuration](https://blogs.sap.com/2017/08/25/cloud-integration-partner-directory-mass-configuration/).

