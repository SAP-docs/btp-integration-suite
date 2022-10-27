<!-- loio08d4522ca0f54bd1bbd22d4d2449a1f3 -->

# Limitations

SAP currently only supports XAdES-BES and XAdES-EPES. There are a number of additional limitations.

-   No support for the `QualifyingPropertiesReference` element \(see section 6.3.2 of the XAdES specification at [http://uri.etsi.org/01903/v1.3.2/ts\_101903v010302p.pdf](http://uri.etsi.org/01903/v1.3.2/ts_101903v010302p.pdf)\).
-   No support for signature forms XAdES-T and XAdES-C.
-   No support for the `Transforms` element contained in the `SignaturePolicyId` element contained in the `SignaturePolicyIdentifier` element.
-   No support of the `CounterSignature` element; this implies that there is no support for the `UnsignedProperties` element.
-   At most one `DataObjectFormat` element is supported.

    More than one `DataObjectFormat` element does not make any sense in the use cases supported by the Signer step, because only one signed data object is expected \(the incoming message body to the XML signer\).

-   At most one `CommitmentTypeIndication` element is supported.

    More than one `CommitmentTypeIndicationelement` does not make any sense in the use cases supported by the Signer step, because only one signed data object is expected \(the incoming message body to the XML signer\).

-   A `CommitmentTypeIndication` element always contains the `AllSignedDataObjects` element.

    The `ObjectReference` element within a `CommitmentTypeIndication` element is not supported.

-   No support of the `AllDataObjectsTimeStamp` element \(it requires a time authority\).
-   No support of the `IndividualDataObjectsTimeStamp` element \(it requires a time authority\).

