---
page_title: "kubernetes_ingress Data Source - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Data Source `kubernetes_ingress`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard ingress's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **id** (String, Optional) The ID of this resource.

### Read-only

- **spec** (List of Object, Read-only) Spec is the desired state of the Ingress. More info: https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#spec-and-status (see [below for nested schema](#nestedatt--spec))
- **status** (List of Object, Read-only) (see [below for nested schema](#nestedatt--status))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the ingress that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the ingress. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the ingress, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the ingress must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this ingress that can be used by clients to determine when ingress has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this ingress.
- **uid** (String, Read-only) The unique in time and space value for this ingress. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedatt--spec"></a>
### Nested Schema for `spec`

- **backend** (List of Object) (see [below for nested schema](#nestedobjatt--spec--backend))
- **rule** (List of Object) (see [below for nested schema](#nestedobjatt--spec--rule))
- **tls** (List of Object) (see [below for nested schema](#nestedobjatt--spec--tls))

<a id="nestedobjatt--spec--backend"></a>
### Nested Schema for `spec.backend`

- **service_name** (String)
- **service_port** (String)


<a id="nestedobjatt--spec--rule"></a>
### Nested Schema for `spec.rule`

- **host** (String)
- **http** (List of Object) (see [below for nested schema](#nestedobjatt--spec--rule--http))

<a id="nestedobjatt--spec--rule--http"></a>
### Nested Schema for `spec.rule.http`

- **path** (List of Object) (see [below for nested schema](#nestedobjatt--spec--rule--http--path))

<a id="nestedobjatt--spec--rule--http--path"></a>
### Nested Schema for `spec.rule.http.path`

- **backend** (List of Object) (see [below for nested schema](#nestedobjatt--spec--rule--http--path--backend))
- **path** (String)

<a id="nestedobjatt--spec--rule--http--path--backend"></a>
### Nested Schema for `spec.rule.http.path.backend`

- **service_name** (String)
- **service_port** (String)





<a id="nestedobjatt--spec--tls"></a>
### Nested Schema for `spec.tls`

- **hosts** (List of String)
- **secret_name** (String)



<a id="nestedatt--status"></a>
### Nested Schema for `status`

- **load_balancer** (List of Object) (see [below for nested schema](#nestedobjatt--status--load_balancer))

<a id="nestedobjatt--status--load_balancer"></a>
### Nested Schema for `status.load_balancer`

- **ingress** (List of Object) (see [below for nested schema](#nestedobjatt--status--load_balancer--ingress))

<a id="nestedobjatt--status--load_balancer--ingress"></a>
### Nested Schema for `status.load_balancer.ingress`

- **hostname** (String)
- **ip** (String)


