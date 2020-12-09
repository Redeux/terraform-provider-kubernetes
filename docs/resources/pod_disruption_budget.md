---
page_title: "kubernetes_pod_disruption_budget Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_pod_disruption_budget`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard pod disruption budget's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))
- **spec** (Block List, Min: 1, Max: 1) Specification of the desired behavior of the PodDisruptionBudget. (see [below for nested schema](#nestedblock--spec))

### Optional

- **id** (String, Optional) The ID of this resource.

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the pod disruption budget that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the pod disruption budget. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the pod disruption budget, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the pod disruption budget must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this pod disruption budget that can be used by clients to determine when pod disruption budget has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this pod disruption budget.
- **uid** (String, Read-only) The unique in time and space value for this pod disruption budget. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--spec"></a>
### Nested Schema for `spec`

Required:

- **selector** (Block List, Min: 1, Max: 1) (see [below for nested schema](#nestedblock--spec--selector))

Optional:

- **max_unavailable** (String, Optional)
- **min_available** (String, Optional)

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


