<!-- loiobb4f072447104c7da2f064e20dd269cb -->

# Extend Your Business Data Graph

To extend your business data graph, you can create model extensions that describe your custom entity projections.



<a name="loiobb4f072447104c7da2f064e20dd269cb__context_bpz_xtl_lyb"/>

## Context

Once you have modeled your extension, you can add it your business data graph. For more information, see [Model](model-31f8c54.md).



<a name="loiobb4f072447104c7da2f064e20dd269cb__steps_ulm_4tl_lyb"/>

## Procedure

1.  Go to the SAP Integration Suite home page *Design* \> *Graph* \> *Model Extensions*. Choose *Create new model extension* or you can upload an existing model extension by choosing *Create from file*.

2.  Enter the name and description of your model extension, and select from which business data graph you want to use metadata. Choose *Create*.

    Once the model extension is created, it appears in the *Model Extensions* overview table. Now, you can add your model extension to a business data graph.

3.  There are two ways to extend a business data graph:

    -   Extending new Business Data Graph:
        1.  Follow the steps for creating a new business data graph. For more information, see [Create a Business Data Graph in Integration Suite](create-a-business-data-graph-in-integration-suite-42daf3b.md).

        2.  In the optional step of extending your business data graph, select your model extensions from the drop-down list. Choose *Next* and complete the rest of the steps.


    -   Extending existing Business Data Graph:

        1.  Go to the *Business Data Graphs* overview tab, select the business data graph you want to extend, and choose *Edit*.

        2.  Add your extension IDs as an array to the `extensions` attribute of your business data graph configuration file.


        > ### Note:  
        > If the `extensions` attribute does not exist in your configuration file, you can add it while you are editing your business data graph.





## Example

Example of Business Data Graph Configuration File with Extensions:

```
{
    "businessDataGraphIdentifier": "ff-example",
    "graphModelVersion": "^v3",
    "schemaVersion": "1.2.0",
    "extensions": [
        "frequent-flyer"
    ],
    "dataSources": [
        {
            "name": "s4",
            "services": [
                {
                    "destinationName": "sap-s4"
                }
            ]
        },
        {
            "name": "mycustom",
            "services": [
                {
                    "destinationName": "frequent-flyer"
                }
            ],
            "namespace": "mycustom"
        }
    ],
    "locatingPolicy": {
        "cues": [],
        "rules": [
            {
                "name": "sap.s4.*",
                "leading": "s4",
                "local": []
            },
            {
                "name": "sap.graph.*",
                "leading": "s4"
            },
            {
                "name": "mycustom.*",
                "leading": "mycustom"
            },
            {
                "name": "myextension.FrequentFlyer",
                "leading": "mycustom",
                "local": []
            },
            {
                "name": "myextension.FrequentFlyer",
                "leading": "s4",
                "local": [],
                "sourceEntity": "sap.s4.A_BusinessPartner"
            }
        ]
    }
}

```

