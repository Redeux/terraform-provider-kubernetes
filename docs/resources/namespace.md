---
page_title: "kubernetes_namespace Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_namespace`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard namespace's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **id** (String, Optional) The ID of this resource.
- **timeouts** (Block, Optional) (see [below for nested schema](#nestedblock--timeouts))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the namespace that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the namespace. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the namespace, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this namespace that can be used by clients to determine when namespace has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this namespace.
- **uid** (String, Read-only) The unique in time and space value for this namespace. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--timeouts"></a>
### Nested Schema for `timeouts`

Optional:

- **delete** (String, Optional)


