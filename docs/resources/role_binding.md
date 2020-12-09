---
page_title: "kubernetes_role_binding Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_role_binding`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard roleBinding's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))
- **role_ref** (Block List, Min: 1, Max: 1) RoleRef references the Role for this binding (see [below for nested schema](#nestedblock--role_ref))
- **subject** (Block List, Min: 1) Subjects defines the entities to bind a Role to. (see [below for nested schema](#nestedblock--subject))

### Optional

- **id** (String, Optional) The ID of this resource.

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the roleBinding that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the roleBinding. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the roleBinding, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the roleBinding must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this roleBinding that can be used by clients to determine when roleBinding has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this roleBinding.
- **uid** (String, Read-only) The unique in time and space value for this roleBinding. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--role_ref"></a>
### Nested Schema for `role_ref`

Required:

- **api_group** (String, Required) The API group of the user. The only value possible at the moment is `rbac.authorization.k8s.io`.
- **kind** (String, Required) The kind of resource.
- **name** (String, Required) The name of the User to bind to.


<a id="nestedblock--subject"></a>
### Nested Schema for `subject`

Required:

- **kind** (String, Required) The kind of resource.
- **name** (String, Required) The name of the resource to bind to.

Optional:

- **api_group** (String, Optional) The API group of the subject resource.
- **namespace** (String, Optional) The Namespace of the subject resource.


