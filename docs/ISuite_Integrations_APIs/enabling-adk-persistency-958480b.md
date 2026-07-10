<!-- loio958480b47ead4155b81056c5e4bcf85e -->

# Enabling ADK Persistency

As an integration developer you can now utilize an adapter API to store and retrieve critical information ensuring data persistence even after node restarts or crashes. This also ensures flexibility and reliability in data management.

You can also integrate this feature into your workflows to enhance system resilience and maintain seamless operations. It has following benefits:

-   Reduces event duplication, ensuring efficient and streamlined processing.

-   Avoids unnecessary costs by maintaining continuity.


To utilize this feature,

-   Add an additional metadata entry in the metadata.xml file for your adapter:

    ```xml
    
        <Metadata>
        <AdditionalMetadata>
            <Name>ADKStoreRequired</Name>
            <Value>true</Value>
            <GuiLabels>
                <Label language="en"/>
            </GuiLabels>
        </AdditionalMetadata>
    </Metadata>
    
    ```

-   Ensure to refer the adapter.api dependency in the pom.xml file. See [SDK API](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/sdk-api?version=Cloud)

-   In the endpoint class, the ADK store can be accessed by using the following getter and setter methods:

    ```xml
    
    private ADKStore adkStore;
    
    public ADKStore getAdkStore() {
       return adkStore;
    
    }
    
    public void setADKStore(ADKStore adkStore) {
       this.adkStore = adkStore;
    }
    
    ```


> ### Note:  
> This API should not be used to store any personal or sensitive information such as passwords and keys.
> 
> Frequent calls may impact the performance of the worker.

