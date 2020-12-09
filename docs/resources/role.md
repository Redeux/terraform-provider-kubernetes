---
page_title: "kubernetes_role Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_role`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard role's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))
- **rule** (Block List, Min: 1) Rule defining a set of permissions for the role (see [below for nested schema](#nestedblock--rule))

### Optional

- **id** (String, Optional) The ID of this resource.

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the role that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the role. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the role, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the role must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this role that can be used by clients to determine when role has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this role.
- **uid** (String, Read-only) The unique in time and space value for this role. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--rule"></a>
### Nested Schema for `rule`

Required:

- **api_groups** (Set of String, Required) Name of the APIGroup that contains the resources
- **resources** (Set of String, Required) List of resources that the rule applies to
- **verbs** (Set of String, Required) List of Verbs that apply to ALL the ResourceKinds and AttributeRestrictions contained in this rule

Optional:

- **resource_names** (Set of String, Optional) White list of names that the rule applies to


