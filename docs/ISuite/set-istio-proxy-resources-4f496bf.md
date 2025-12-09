<!-- loio4f496bf4f2e247b88feba1fa3f0e91c0 -->

# Set Istio Proxy Resources

Learn how to set Istio Proxy resources for worker components.



## Context

Container resources for Istio Proxies \(Istio sidecars\) come with default values. However, for worker components, you might need to increase resource limits for Istio Proxies based on actual volume.

> ### Note:  
> Resource settings will be available as runtime parameters in the Operations Cockpit in a later version.

To manually configure Istio Proxy Resources, follow this procedure:



## Procedure

1.  Check if a custom `ConfigMap worker-custom-config` already exists. To do so, use the command: `kubectl edit cm worker-custom-config -n edge-icell`.

2.  If it exists, an editor opens displaying the existing ConfigMap.

    1.  Add the following attributes in the data section, changing the values as needed:


        <table>
        <tr>
        <th valign="top">

        Attributes
        
        </th>
        <th valign="top">

        Default Values
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        ISTIO\_CPU\_LIMIT
        
        </td>
        <td valign="top">
        
        200 m
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ISTIO\_CPU\_REQUEST
        
        </td>
        <td valign="top">
        
        25 m
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ISTIO\_MEMORY\_LIMIT
        
        </td>
        <td valign="top">
        
        256 Mi
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ISTIO\_MEMORY\_REQUEST
        
        </td>
        <td valign="top">
        
        32 Mi
        
        </td>
        </tr>
        </table>
        
    2.  Save your changes and exit the editor.

    3.  To activate these parameters, open the Edge Lifecycle Management UI and choose *Modify Configuration*. For more information, see [Modifying Configuration Properties of a Solution Deployment](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/582038fb88c5435b9ffef81c70c253b0.html).


3.  If a custom ConfigMap doesn't exist:

    1.  Paste the following data into the editor, changing the values as needed \(these are the default values\):

        ```
        
        apiVersion: v1
        
        kind: ConfigMap
        
        metadata:
        
          name: worker-custom-config
        
          namespace: edge-icell
        
        data:
        
          ISTIO_CPU_LIMIT: 200m
        
          ISTIO_CPU_REQUEST: 25m
        
          ISTIO_MEMORY_LIMIT: 256Mi
        
          ISTIO_MEMORY_REQUEST: 32Mi
        ```

    2.  Save the file as `<configmap-file>` and exit the editor.

    3.  Create the ConfigMap using the command: `kubectl apply -f <configmap-file>`.

    4.  To activate these parameters, open the Edge Lifecycle Management UI and choose *Modify Configuration*. For more information, see [Modifying Configuration Properties of a Solution Deployment](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/582038fb88c5435b9ffef81c70c253b0.html).





<a name="loio4f496bf4f2e247b88feba1fa3f0e91c0__result_v2h_lls_ngc"/>

## Results

You have configured the resource limits for Istio Proxie for the worker component.

