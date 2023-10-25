<!-- loioabbb36a792c34d17a2562333060971ce -->

# Access the Event Broker

Learn how to access the Event Broker.



## Context

The event broker provides a *Broker Manager* UI. To use the Broker Manager, follow these steps.



## Procedure

1.  To display the *Broker Manager* port, use `kubectl port-forward ssb-solace-0 8080 -n edge-icell-services`.

2.  To get the admin user password, use `kubectl get secret ssbsecrets-solace--template="{{index .data.admin_password | base64decode}}" -n edge-icell-services`.

3.  Open an Internet browser using `localhost:8080` enter username `admin` and the password you retrieved before .


