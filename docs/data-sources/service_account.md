---
page_title: "kubernetes_service_account Data Source - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Data Source `kubernetes_service_account`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard service account's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **id** (String, Optional) The ID of this resource.

### Read-only

- **automount_service_account_token** (Boolean, Read-only) True to enable automatic mounting of the service account token
- **default_secret_name** (String, Read-only)
- **image_pull_secret** (List of Object, Read-only) A list of references to secrets in the same namespace to use for pulling any images in pods that reference this Service Account. More info: http://kubernetes.io/docs/user-guide/secrets#manually-specifying-an-imagepullsecret (see [below for nested schema](#nestedatt--image_pull_secret))
- **secret** (List of Object, Read-only) A list of secrets allowed to be used by pods running using this Service Account. More info: http://kubernetes.io/docs/user-guide/secrets (see [below for nested schema](#nestedatt--secret))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the service account that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the service account. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the service account, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the service account must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this service account that can be used by clients to determine when service account has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this service account.
- **uid** (String, Read-only) The unique in time and space value for this service account. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedatt--image_pull_secret"></a>
### Nested Schema for `image_pull_secret`

- **name** (String)


<a id="nestedatt--secret"></a>
### Nested Schema for `secret`

- **name** (String)


