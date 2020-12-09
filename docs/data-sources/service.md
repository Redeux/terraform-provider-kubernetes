---
page_title: "kubernetes_service Data Source - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Data Source `kubernetes_service`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard service's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **id** (String, Optional) The ID of this resource.

### Read-only

- **spec** (List of Object, Read-only) Spec defines the behavior of a service. https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#spec-and-status (see [below for nested schema](#nestedatt--spec))
- **status** (List of Object, Read-only) (see [below for nested schema](#nestedatt--status))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the service that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the service. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the service, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the service must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this service that can be used by clients to determine when service has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this service.
- **uid** (String, Read-only) The unique in time and space value for this service. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedatt--spec"></a>
### Nested Schema for `spec`

- **cluster_ip** (String)
- **external_ips** (Set of String)
- **external_name** (String)
- **external_traffic_policy** (String)
- **health_check_node_port** (Number)
- **load_balancer_ip** (String)
- **load_balancer_source_ranges** (Set of String)
- **port** (List of Object) (see [below for nested schema](#nestedobjatt--spec--port))
- **publish_not_ready_addresses** (Boolean)
- **selector** (Map of String)
- **session_affinity** (String)
- **type** (String)

<a id="nestedobjatt--spec--port"></a>
### Nested Schema for `spec.port`

- **name** (String)
- **node_port** (Number)
- **port** (Number)
- **protocol** (String)
- **target_port** (String)



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


