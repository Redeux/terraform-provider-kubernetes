---
page_title: "kubernetes_storage_class Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_storage_class`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard storage class's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))
- **storage_provisioner** (String, Required) Indicates the type of the provisioner

### Optional

- **allow_volume_expansion** (Boolean, Optional) Indicates whether the storage class allow volume expand
- **allowed_topologies** (Block List, Max: 1) Restrict the node topologies where volumes can be dynamically provisioned. (see [below for nested schema](#nestedblock--allowed_topologies))
- **id** (String, Optional) The ID of this resource.
- **mount_options** (Set of String, Optional) Persistent Volumes that are dynamically created by a storage class will have the mount options specified
- **parameters** (Map of String, Optional) The parameters for the provisioner that should create volumes of this storage class
- **reclaim_policy** (String, Optional) Indicates the type of the reclaim policy
- **volume_binding_mode** (String, Optional) Indicates when volume binding and dynamic provisioning should occur

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the storage class that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the storage class. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the storage class, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this storage class that can be used by clients to determine when storage class has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this storage class.
- **uid** (String, Read-only) The unique in time and space value for this storage class. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--allowed_topologies"></a>
### Nested Schema for `allowed_topologies`

Optional:

- **match_label_expressions** (Block List) A list of topology selector requirements by labels. (see [below for nested schema](#nestedblock--allowed_topologies--match_label_expressions))

<a id="nestedblock--allowed_topologies--match_label_expressions"></a>
### Nested Schema for `allowed_topologies.match_label_expressions`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **values** (Set of String, Optional) An array of string values. One value must match the label to be selected.


