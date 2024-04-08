<!-- loio05b95690df574d759baeee19dace2f23 -->

# Operation Mapping

Operation mapping is used to relate an outbound service interface operation with an inbound service interface operation. You can also relate IDoc and RFC interfaces with entities of the same type or with service interface operations.

To know more, see [Operation Mapping](https://help.sap.com/viewer/bbd7c67c5eb14835843976b790024ec6/7.5.14/en-US/eaab902f36eb404497cf69db7d07ac40.html).

> ### Note:  
> -   You can only assign an operation mapping to an integration flow, creation of an operation mapping is not supported.
> 
> -   Operation mapping can only be used with SOAP sender adapter.



Assigning Operation Mapping



1.  Open your integration flow and choose *Edit*.

2.  Choose *Operation Mapping* from the palette under *Mapping Components*.

3.  In the *General* tab enter details for *Name* field.

4.  In the *Processing* tab, choose *Select* and assign the resource \(**.opmap** file\) to the operation mapping step.

    > ### Note:  
    > To know more about importing the mapping content into an integration flow, see [Importing Mapping Content from ES Repository](IntegrationSettings/importing-mapping-content-from-es-repository-e18fc05.md).


