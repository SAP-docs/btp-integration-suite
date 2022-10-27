<!-- loio09be9835e1184603ad796071e0a86b98 -->

# Qualifying Nodes

You can qualify nodes to provide context to the semantically generic elements of your Message Implementation Guideline \(MIG\).

The message structure is composed of logically related pieces of information grouped into generic data segments. You can customize and precisely specify the context of generic elements in your MIG message structure to provide business meaning to the rest of the data in a segment. For example, a generic element like Date/Time reference or Address is unclear at the semantic level as to which date or address the message interface refers to. As a result, additional information is required to remove any ambiguity related to the semantic purpose of a segment. Qualifiers can be used to specify which type of address is stored within a particular instance of a data segment.

An address segment generally consists of a similar set of fields such as - street, city, state, postal code, and country. However, there may be more than one set of addresses such as a delivery address, a contact address, or a billing address. In these situations, you could use a common address segment structure and then use a qualifier to specify which type of address is stored within a particular instance of a data segment.

Qualifiers are provided by a leaf node \(qualifying node\) in the form of codelists and related code values. A leaf node can qualify a group node or another leaf node \(peer node\) only if it has a codelist assigned to it. See [Assigning Codelists to Leaf Nodes](assigning-codelists-to-leaf-nodes-770f7be.md). The link between the qualifying node \(leaf node\) and the node you want to qualify \(qualifiable node\) is expressed by a qualifier marker arrow in gray. A qualifier marker can go from a qualifying element to a parent group element or a peer element at the same level. It helps identify the elements that can be qualified. Qualifier markers are either automatically provided by message templates from type systems, or you can create your own qualifier markers to suit your business context. See [Creating a Qualifier Marker](creating-a-qualifier-marker-0101869.md).

A qualified group or peer leaf node is indicated by a blue arrow marker from the qualifying leaf node to the qualified node along with the qualifier value provided by the selected code values. The name of the qualifier value is appended to the qualified instance. See [Creating a Qualified Instance](creating-a-qualified-instance-efcf25e.md). You can create multiple instances of a qualified element by repeating it with different qualifier values. Each qualified instance can have its own customization.

