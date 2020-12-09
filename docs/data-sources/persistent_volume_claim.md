---
page_title: "kubernetes_persistent_volume_claim Data Source - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Data Source `kubernetes_persistent_volume_claim`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard persistent volume claim's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **id** (String, Optional) The ID of this resource.
- **spec** (Block List) Spec defines the desired characteristics of a volume requested by a pod author. More info: http://kubernetes.io/docs/user-guide/persistent-volumes#persistentvolumeclaims (see [below for nested schema](#nestedblock--spec))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the persistent volume claim that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the persistent volume claim. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the persistent volume claim, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the persistent volume claim must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this persistent volume claim that can be used by clients to determine when persistent volume claim has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this persistent volume claim.
- **uid** (String, Read-only) The unique in time and space value for this persistent volume claim. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--spec"></a>
### Nested Schema for `spec`

Optional:

- **selector** (Block List) A label query over volumes to consider for binding. (see [below for nested schema](#nestedblock--spec--selector))
- **storage_class_name** (String, Optional) Name of the storage class requested by the claim
- **volume_name** (String, Optional) The binding reference to the PersistentVolume backing this claim.

Read-only:

- **access_modes** (Set of String, Read-only) A set of the desired access modes the volume should have. More info: http://kubernetes.io/docs/user-guide/persistent-volumes#access-modes-1
- **resources** (List of Object, Read-only) A list of the minimum resources the volume should have. More info: http://kubernetes.io/docs/user-guide/persistent-volumes#resources (see [below for nested schema](#nestedatt--spec--resources))

<a id="nestedblock--spec--selector"></a>
### Nested Schema for `spec.selector`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--selector--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--spec--selector--match_expressions"></a>
### Nested Schema for `spec.selector.match_expressions`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.



<a id="nestedatt--spec--resources"></a>
### Nested Schema for `spec.resources`

- **limits** (Map of String)
- **requests** (Map of String)


