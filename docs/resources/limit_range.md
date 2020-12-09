---
page_title: "kubernetes_limit_range Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_limit_range`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard limit range's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **id** (String, Optional) The ID of this resource.
- **spec** (Block List, Max: 1) Spec defines the limits enforced. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#spec-and-status (see [below for nested schema](#nestedblock--spec))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the limit range that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the limit range. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the limit range, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the limit range must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this limit range that can be used by clients to determine when limit range has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this limit range.
- **uid** (String, Read-only) The unique in time and space value for this limit range. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--spec"></a>
### Nested Schema for `spec`

Optional:

- **limit** (Block List) Limits is the list of objects that are enforced. (see [below for nested schema](#nestedblock--spec--limit))

<a id="nestedblock--spec--limit"></a>
### Nested Schema for `spec.limit`

Optional:

- **default** (Map of String, Optional) Default resource requirement limit value by resource name if resource limit is omitted.
- **default_request** (Map of String, Optional) The default resource requirement request value by resource name if resource request is omitted.
- **max** (Map of String, Optional) Max usage constraints on this kind by resource name.
- **max_limit_request_ratio** (Map of String, Optional) The named resource must have a request and limit that are both non-zero where limit divided by request is less than or equal to the enumerated value; this represents the max burst for the named resource.
- **min** (Map of String, Optional) Min usage constraints on this kind by resource name.
- **type** (String, Optional) Type of resource that this limit applies to.


