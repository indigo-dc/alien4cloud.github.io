---
layout: post
title:  Relationship type
root: ../../../
categories: DOCUMENTATION
parent: [tosca_ref_root, tosca_ref, tosca_ref_definitions]
node_name: tosca_ref_types_relationship_type
weight: 400
---

A Relationship Type is a reusable entity that defines the type of one or more relationships between Node Types or Node Templates.

## Keynames

{: .table .table-bordered}
| Keyname         | Type                | Required | Description |
|:----------------|:--------------------|:---------|:------------|
| abstract*     | boolean | no | Optional flag to specify if a component is abstract and has no valid implementation. Defaults to false. |
| derived_from | string | no* | An optional parent Relationship Type name the Relationship Type derives from. |
| description | string | no | An optional description for the Relationship Type. |
| properties | [property definitions](#/documentation/tosca_ref/tosca_grammar/property_definition.html) | no | An optional list of property definitions for the Relationship Type.|
| attributes | [attribute definitions](#/documentation/tosca_ref/tosca_grammar/attribute_definition.html) | no | An optional list of attribute definitions for the Relationship Type. |
| interfaces | [interface definitions](#/documentation/tosca_ref/tosca_grammar/interface_definition.html) | no | An optional list of named interfaces for the Relationship Type. |
| valid_sources | string[] | no | An optional list of one or more valid target entities or entity types (i.e., a Node Types or Capability Types). |
| valid_targets | string[] | yes | A required list of one or more valid target entities or entity types (i.e., a Node Types or Capability Types). |

{% info %}
 - Abstract flag is specific to Alien 4 Cloud and is not part of TOSCA Simple Profile in YAML.
 - derived_from is not required however relationship types SHOULD all extends from a normative type (ConnectsTo or HostedOn for example).
{% endinfo %}

## Grammar

{% highlight yaml %}
<relationship_type_name>:
  derived_from: <parent_relationship_type_name>
  description: <relationship_description>
  properties:
    <property_definitions>
  attributes:
    <attribute_definitions>
  interfaces:
    <interface_definitions>
  valid_targets: [ <entity_name_or_type_1>, ..., <entity_name_or_type_n> ]
{% endhighlight %}

See:

- [property_definitions](#/documentation/tosca_ref/tosca_grammar/property_definition.html)
- [attribute definitions](#/documentation/tosca_ref/tosca_grammar/attribute_definition.html)
- [interface definitions](#/documentation/tosca_ref/tosca_grammar/interface_definition.html)

## Example

{% highlight yaml %}
mycompanytypes.myrelationships.AppDependency:
  derived_from: tosca.relationships.DependsOn
  valid_targets: [ mycompanytypes.mycapabilities.SomeAppCapability ]
{% endhighlight %}