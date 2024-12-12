<!-- loio3572dfb79f30498d8bd4e5d356efee8c -->

# Actions and Functions

Actions and functions provide a way to introduce server-side behaviors into the otherwise data-centric model. Graph mirrors actions and functions as provided by connected business systems.

[OData](https://www.odata.org/) supports custom operations that are named *Actions* and *Functions*. Both are considered operations on the data model:

-   **Actions** are operations that modify data on the server. An action is invoked through a POST request with its arguments being passed in the request body in the [JSON](https://www.json.org/) format.
-   **Functions** are operations that only retrieve data from the server without causing side effects. A function is invoked through a GET request with its arguments being passed in the URL path.

Furthermore, OData differentiates between unbound and bound operations:

-   Bound operations have an implicit relationship to one entity. They are similar to class methods in object-oriented programming as their first implicit argument is bound to their entity's primary key.
-   Unbound operations have no implicit relationship to an entity. They are similar to functions in programming languages as they receive all arguments explicitly.

Graph supports OData operations \(actions and functions\) and automatically discovers them in the metadata of connected business systems. Discovered actions and functions are mirrored into the resulting business data graph.

-   [Actions in OData – Blog \(odata.org\)](https://www.odata.org/blog/actions-in-odata/)
-   [Functions and Actions – Basic Tutorial \(odata.org\)](https://www.odata.org/getting-started/basic-tutorial/#operation)
-   [Actions & Functions – CAP \(cap.cloud.sap\)](https://cap.cloud.sap/docs/guides/providing-services#actions-and-functions)



<a name="loio3572dfb79f30498d8bd4e5d356efee8c__section_m2l_x3b_kvb"/>

## Metadata

Actions and functions can be found in the exposed metadata of a business data graph. They are part of the metadata of any given namespace:

```
https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/<bdg>/<namespace>/$metadata
```

-   `subdomain` = The subdomain assigned to the tenant. For example, `is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef`.
-   `bdg` = The business data graph identifier as specified by the Graph configuration.
-   `namespace` = The namespace of the connected business system, for example, `sap.s4` for S/4HANA or `sap.c4c` for SAP Cloud for Customer.

Actions are represented by the following XML-schema:

```
<Action Name="<action name>" IsBound="<true or false>" ...>
  <Parameter Name="<parameter name>" Type="parameter type" ... />
  ...
  <ReturnType Type="<return type>" ... />
</Action>

```

Functions are represented by the following XML-schema:

```
<Function Name="<function name>" IsBound="<true or false>" ...>
  <Parameter Name="<parameter name>" Type="<parameter type>" ... />
  ...
  <ReturnType Type="<return type>" ... />
</Function>
```



<a name="loio3572dfb79f30498d8bd4e5d356efee8c__section_wyv_x3b_kvb"/>

## Usage

Actions and functions can be invoked by constructing the request path using the namespace, bound status, and operation name. Additionally, parameters are part of the request path for functions or the request body for actions. Abstract schema and examples for all four possible request scenarios are listed here:

-   Unbound action
-   Bound action
-   Unbound function
-   Bound function



### Unbound Action

```
POST https://<subdomain>.a.integration.cloud.sap/graph/api/<bdg>/<namespace>/<action>
{
  "<parameter name>": "<parameter value>"
  ...
}
```

> ### Sample Code:  
> ```
> POST https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.c4c/CalculateScore
> {
>   "ObjectId": "1",
>   "Simulate": "true",
>   "FinalizePhaseIndicator": "false",
>   "CalculateAllKPIsIndicator": "true"
> }
> ```



### Bound Action

```
POST https://<subdomain>.a.integration.cloud.sap/graph/api/<bdg>/<namespace>/<bound entity>/<action>
{
  "<parameter name>": "<parameter value>"
  ...
}
```

> ### Sample Code:  
> ```
> POST https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v2/sap.s4/InHouseRepair('1')/ConfirmRepairObjects
> ```



### Unbound Function

```
GET https://<subdomain>.a.integration.cloud.sap/graph/api/<bdg>/<namespace>/<function name>(<parameter name>=<parameter value>,...)
```

> ### Sample Code:  
> ```
> GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.c4c/GetServiceRequestProcessingTypes(isCustomerSupport=false,isEmployeeSupport=true)
> ```



### Bound Function

```
GET https://<subdomain>.a.integration.cloud.sap/graph/api/<bdg>/<namespace>/<bound entity>/<function name>(<parameter name>=<parameter value>,...)
```

> ### Sample Code:  
> ```
> GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v2/sap.s4/A_BillingDocument('1')/GetPDF()
> ```

**Related Information**  


[Actions in OData – Blog \(odata.org\)](https://www.odata.org/blog/actions-in-odata/)

[Functions and Actions – Basic Tutorial \(odata.org\)](https://www.odata.org/getting-started/basic-tutorial/#operation)

