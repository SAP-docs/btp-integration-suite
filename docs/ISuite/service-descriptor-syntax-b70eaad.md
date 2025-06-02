<!-- loiob70eaadbc5aa4660ac79ca7f9d0c9a04 -->

# Service Descriptor Syntax

The guidelines and syntax for the service descriptor JSON file that can be used to describe the attributes of the service instance created for Event Mesh.



<a name="loiob70eaadbc5aa4660ac79ca7f9d0c9a04__section_dnm_bnr_s2c"/>

## Context

Service instance creation in Event Mesh is needed for access to the message client. Creation can happen:

-   In SAP BTP cockpit. See [Configure A Message Client](configure-a-message-client-867c517.md)
-   Using the Cloud Foundry Command Line Interface. See [Creating an Event Mesh Message Client Using the Cloud Foundry Command Line Interface](creating-an-event-mesh-message-client-using-the-cloud-foundry-command-line-interface-23df43b.md)

You can maintain a JSON file with parameters describing the attributes of this service instance. The JSON file is called service descriptor. In the service descriptor, you need to enter your message client name, the namespace, and maintain the options to define the access channel and rules for your message client.



<a name="loiob70eaadbc5aa4660ac79ca7f9d0c9a04__section_jzz_jml_3nb"/>

## General Guidelines

-   Maintain rules in your service descriptor. A message client can't publish or consume messages if rules aren't defined in the service descriptor.
-   Use semantically relevant namespaces when defining your service descriptor.
-   It's recommended that you publish to topics and not to queues directly.
-   Publish to your own namespace only. For example, `rules.topicRules.publishFilter` entries must always start with $\{namespace\}/...
-   Consume from your own queues only. For example, rules.queueRules.subscribeFilter entries must always start with $\{namespace\}/...
-   Publish to your own queues only. Ensure you remain in your own namespace for end-to-end business scenarios. For example, rules.queueRules.publishFilter entries must always start with $\{namespace\}/...
-   Avoid using queues with foreign namespaces.



You can use the following attributes in your service descriptor:

> ### Sample Code:  
> ```
> {
>     "rules": {
>         "topicRules": {
>             "publishFilter": [
>                 "${namespace}/*"
>             ],
>             "subscribeFilter": [
>                 "${namespace}/*"
>             ]
>         },
>         "queueRules": {
>             "publishFilter": [
>                 "${namespace}/*"
>             ],
>             "subscribeFilter": [
>                 "${namespace}/*"
>             ]
>         }
>     },
>     "resources": {
>         "units": 10
>     },
>     "version": "1.1.0",
>     "emname": "em-healthcheck",
>     "namespace": "sap/em/opshealthcheck"
> }
> 
> ```



### emname

Specifies the name of the message client and is used to easily identify message clients. It must be unique for a subaccount. It's recommended that you use the same value for service instance name and emname.

The syntax for emname is:

-   Type: attribute
-   Allowed characters: \[a-zA-Z0-9\_-\]
-   Max Length: 100
-   Required: true



### version

It specifies the version of the service descriptor.

The syntax for the version is:

-   Type: attribute
-   Allowed versions: 1.1.0
-   Required: true

> ### Note:  
> If you're using the new syntax for rules, the field `"version": 1.1.0` is required. The version field is optional when you use the deprecated syntax.



### namespace

A namespace ensures that every message client within a subaccount is unique. The queues managed by the message client and topics used to publish by the message client must have the namespace as prefix.

If a message client is used in a business scenario as a reuse service, the namespace must be globally unique.

Instead of a technical client ID, it's recommended to use a namespace that ends with `-` or `svc` in the last segment, for example, `default/sap.myapp/-` for provider instances. Consumer instances aren't allowed to use namespaces that end with `-` or `svc`.

The syntax for namespace is:

-   Type: attribute
-   Segments: exactly three \(firstSegment/secondSegment/thirdSegment\)
-   Allowed characters:
    -   First segment: \[a-zA-Z0-9\]
        -   Don't use hyphens and dots.
        -   Recommended value: default

    -   Second segment: \[a-zA-Z0-9-.\]
        -   Starts with a character or number
        -   Followed by . or -
        -   Must contain at least 1 character or number before or after the period or hyphen.

    -   Third segment: \[a-zA-Z0-9-.\]
        -   Starts with a character or number
        -   Followed by . or -
        -   Must contain at least one character or number before or after the period or hyphen.
        -   For provider scenarios, use a hyphen.


-   Max Length: 63
-   Required: true

A namespace must:

-   be unique within a subaccount
-   contain exactly 3 segments, for example, a/b/c
-   follow the construction rule <region\>/<applicationNamespace\>/<instanceId\>. The following values are recommended:
    -   Region: default
    -   Application namespace: <vendor.<application\>\>, for example, `mycompany.myapp.mysubapp` without the top-level domain, in sap.com remove the .com.
    -   Instance ID: a fixed number, for example, default/sap.myapp/1. For multiple instances or message clients of the same type, use <region\>/<applicationNamespace\>/\*

-   be prefixed for each queue name handled by the message client.



### resources

Resource units are a collection of messaging resources, such as queues, connections, and so on, required for a message client. You can specify this value in the service descriptor to allocate messaging resources based on a specific business scenario.

> ### Example:  
> For example, if you create a service instance with 12 resource units, you can have 12 queues, 12 webhooks, 12 connections, 36 consumers, 36 producers, and 180 queue subscriptions. There's no limit on message spooling.

If you don't define resource units, all messaging resources can be used based on the general limits applicable to a message client.


<table>
<tr>
<th valign="top">

**Resource**

</th>
<th valign="top">

**Allocation**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

Connections

</td>
<td valign="top">

1

</td>
<td valign="top">

The number of connections that can be established per service instance; the total number of connections is the sum of connections created using AMQP 1.0, MQTT, and REST APIs for Messaging, respectively.

</td>
</tr>
<tr>
<td valign="top">

Endpoints

</td>
<td valign="top">

3

</td>
<td valign="top">

Total number of queues that can be created; sum of queues and topic endpoints.

</td>
</tr>
<tr>
<td valign="top">

Consumers

</td>
<td valign="top">

3

</td>
<td valign="top">

The maximum number of consumers \(only controlled per connection\).

</td>
</tr>
<tr>
<td valign="top">

Producers

</td>
<td valign="top">

3

</td>
<td valign="top">

The maximum number of producers \(only controlled per connection\).

</td>
</tr>
<tr>
<td valign="top">

Queue Subscriptions

</td>
<td valign="top">

15

</td>
<td valign="top">

The maximum number of producers \(only controlled per connection\).

</td>
</tr>
<tr>
<td valign="top">

Message Spool

</td>
<td valign="top">

10 MB

</td>
<td valign="top">

The maximum size of all messages that can be stored in the queues.

</td>
</tr>
</table>

The syntax for resource units is:

Type: attribute

Default: 10

Allowed values: 10–50

Required: false



### rules

Rules define the publish or consume privileges for a message client.

To allow access to a queue or a topic, the namespace of the corresponding owner message client has to be added. The placeholder `${namespace}` can be used instead of the defined namespace. For example, if the namespace `"namespace": "default/sap.myapp/1"` is defined, the most basic rule is `${namespace}/*`. Ensure you provide the attribute `publishFilter` if you want to send messages and the attribute `subscribeFilter` to consume messages. If you omit these attributes, you can’t access messaging. You can omit these attributes if you want to use only the management scenario. Rules support the following wildcards:

-   \+ \(ASCII 0x2B\) represents a single segment with any content that’s valid, but always the whole segment.

-   \* \(ASCII 0x2A\) represents a subtree of segments \(zero, one or more segments\) and can only appear at the end of the rule.


The syntax for rules is:

-   Type: object
-   Required: false
-   Attribute: queueRules
    -   Type: object
    -   Attribute: publishFilter
        -   Type: array
        -   Default: None
        -   Allowed characters: \[a-zA-Z\*+/\]
        -   Sample values: $\{namespace\}/foo/bar/\*, $\{namespace\}/\*, $\{namespace\}/+
        -   Allows a message client to send messages to a queue that matches with the defined rule.

    -   Attribute: subscribeFilter
        -   Type: array
        -   Default: None
        -   Allowed characters: \[a-zA-Z\*+/\]
        -   Sample values: $\{namespace\}/foo/bar/\*, $\{namespace\}/\*, $\{namespace\}/+
        -   Allows a message client to receive messages from a queue that matches with the defined rule.


-   Attribute: topicRules
    -   Type: object
    -   Attribute: publishFilter
        -   Type: array
        -   Default: None
        -   Allowed characters: \[a-zA-Z\*+/\]
        -   Sample values: $\{namespace\}/foo/bar/\*, $\{namespace\}/\*, $\{namespace\}/?, $\{namespace\}/+
        -   Allows a message client to send messages to a topic that matches with the defined rule.

        -   It's recommended that you publish to your own namespace only, for example, the rule must be $\{namespace\}/\*


    -   Attribute: subscribeFilter
        -   Type: array
        -   Default: None
        -   Allowed characters: \[a-zA-Z\*+/\]
        -   Sample values: $\{namespace\}/foo/bar/\*, $\{namespace\}/\*, $\{namespace\}/+, +/+/+/foo/bar/\*
        -   Allows a message client to subscribe to a topic that matches with the defined rule.



