---
page_title: "kubernetes_secret Data Source - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Data Source `kubernetes_secret`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard secret's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **id** (String, Optional) The ID of this resource.

### Read-only

- **data** (Map of String, Read-only) A map of the secret data.
- **type** (String, Read-only) Type of secret

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the secret that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the secret. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the secret, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the secret must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this secret that can be used by clients to determine when secret has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this secret.
- **uid** (String, Read-only) The unique in time and space value for this secret. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


