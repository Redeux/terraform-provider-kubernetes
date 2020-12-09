---
page_title: "kubernetes_endpoints Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_endpoints`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard endpoints's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **id** (String, Optional) The ID of this resource.
- **subset** (Block Set) Set of addresses and ports that comprise a service. More info: https://kubernetes.io/docs/concepts/services-networking/service/#services-without-selectors (see [below for nested schema](#nestedblock--subset))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the endpoints that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the endpoints. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the endpoints, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the endpoints must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this endpoints that can be used by clients to determine when endpoints has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this endpoints.
- **uid** (String, Read-only) The unique in time and space value for this endpoints. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--subset"></a>
### Nested Schema for `subset`

Optional:

- **address** (Block Set) IP address which offers the related ports that are marked as ready. These endpoints should be considered safe for load balancers and clients to utilize. (see [below for nested schema](#nestedblock--subset--address))
- **not_ready_address** (Block Set) IP address which offers the related ports but is not currently marked as ready because it have not yet finished starting, have recently failed a readiness check, or have recently failed a liveness check. (see [below for nested schema](#nestedblock--subset--not_ready_address))
- **port** (Block Set) Port number available on the related IP addresses. (see [below for nested schema](#nestedblock--subset--port))

<a id="nestedblock--subset--address"></a>
### Nested Schema for `subset.address`

Required:

- **ip** (String, Required) The IP of this endpoint. May not be loopback (127.0.0.0/8), link-local (169.254.0.0/16), or link-local multicast ((224.0.0.0/24).

Optional:

- **hostname** (String, Optional) The Hostname of this endpoint.
- **node_name** (String, Optional) Node hosting this endpoint. This can be used to determine endpoints local to a node.


<a id="nestedblock--subset--not_ready_address"></a>
### Nested Schema for `subset.not_ready_address`

Required:

- **ip** (String, Required) The IP of this endpoint. May not be loopback (127.0.0.0/8), link-local (169.254.0.0/16), or link-local multicast ((224.0.0.0/24).

Optional:

- **hostname** (String, Optional) The Hostname of this endpoint.
- **node_name** (String, Optional) Node hosting this endpoint. This can be used to determine endpoints local to a node.


<a id="nestedblock--subset--port"></a>
### Nested Schema for `subset.port`

Required:

- **port** (Number, Required) The port that will be exposed by this endpoint.

Optional:

- **name** (String, Optional) The name of this port within the endpoint. Must be a DNS_LABEL. Optional if only one Port is defined on this endpoint.
- **protocol** (String, Optional) The IP protocol for this port. Supports `TCP` and `UDP`. Default is `TCP`.


