---
page_title: "kubernetes_pod Data Source - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Data Source `kubernetes_pod`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard pod's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **id** (String, Optional) The ID of this resource.

### Read-only

- **spec** (List of Object, Read-only) Specification of the desired behavior of the pod. (see [below for nested schema](#nestedatt--spec))
- **status** (String, Read-only)

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the pod that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the pod. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the pod, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the pod must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this pod that can be used by clients to determine when pod has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this pod.
- **uid** (String, Read-only) The unique in time and space value for this pod. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedatt--spec"></a>
### Nested Schema for `spec`

- **active_deadline_seconds** (Number)
- **affinity** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity))
- **automount_service_account_token** (Boolean)
- **container** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container))
- **dns_config** (List of Object) (see [below for nested schema](#nestedobjatt--spec--dns_config))
- **dns_policy** (String)
- **enable_service_links** (Boolean)
- **host_aliases** (List of Object) (see [below for nested schema](#nestedobjatt--spec--host_aliases))
- **host_ipc** (Boolean)
- **host_network** (Boolean)
- **host_pid** (Boolean)
- **hostname** (String)
- **image_pull_secrets** (List of Object) (see [below for nested schema](#nestedobjatt--spec--image_pull_secrets))
- **init_container** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container))
- **node_name** (String)
- **node_selector** (Map of String)
- **priority_class_name** (String)
- **readiness_gate** (List of Object) (see [below for nested schema](#nestedobjatt--spec--readiness_gate))
- **restart_policy** (String)
- **security_context** (List of Object) (see [below for nested schema](#nestedobjatt--spec--security_context))
- **service_account_name** (String)
- **share_process_namespace** (Boolean)
- **subdomain** (String)
- **termination_grace_period_seconds** (Number)
- **toleration** (List of Object) (see [below for nested schema](#nestedobjatt--spec--toleration))
- **volume** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume))

<a id="nestedobjatt--spec--affinity"></a>
### Nested Schema for `spec.affinity`

- **node_affinity** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--node_affinity))
- **pod_affinity** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_affinity))
- **pod_anti_affinity** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_anti_affinity))

<a id="nestedobjatt--spec--affinity--node_affinity"></a>
### Nested Schema for `spec.affinity.node_affinity`

- **preferred_during_scheduling_ignored_during_execution** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--node_affinity--preferred_during_scheduling_ignored_during_execution))
- **required_during_scheduling_ignored_during_execution** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution))

<a id="nestedobjatt--spec--affinity--node_affinity--preferred_during_scheduling_ignored_during_execution"></a>
### Nested Schema for `spec.affinity.node_affinity.required_during_scheduling_ignored_during_execution`

- **preference** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution--preference))
- **weight** (Number)

<a id="nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution--preference"></a>
### Nested Schema for `spec.affinity.node_affinity.required_during_scheduling_ignored_during_execution.preference`

- **match_expressions** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution--preference--match_expressions))

<a id="nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution--preference--match_expressions"></a>
### Nested Schema for `spec.affinity.node_affinity.required_during_scheduling_ignored_during_execution.preference.match_expressions`

- **key** (String)
- **operator** (String)
- **values** (Set of String)




<a id="nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution"></a>
### Nested Schema for `spec.affinity.node_affinity.required_during_scheduling_ignored_during_execution`

- **node_selector_term** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution--node_selector_term))

<a id="nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution--node_selector_term"></a>
### Nested Schema for `spec.affinity.node_affinity.required_during_scheduling_ignored_during_execution.node_selector_term`

- **match_expressions** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution--node_selector_term--match_expressions))

<a id="nestedobjatt--spec--affinity--node_affinity--required_during_scheduling_ignored_during_execution--node_selector_term--match_expressions"></a>
### Nested Schema for `spec.affinity.node_affinity.required_during_scheduling_ignored_during_execution.node_selector_term.match_expressions`

- **key** (String)
- **operator** (String)
- **values** (Set of String)





<a id="nestedobjatt--spec--affinity--pod_affinity"></a>
### Nested Schema for `spec.affinity.pod_affinity`

- **preferred_during_scheduling_ignored_during_execution** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_affinity--preferred_during_scheduling_ignored_during_execution))
- **required_during_scheduling_ignored_during_execution** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution))

<a id="nestedobjatt--spec--affinity--pod_affinity--preferred_during_scheduling_ignored_during_execution"></a>
### Nested Schema for `spec.affinity.pod_affinity.required_during_scheduling_ignored_during_execution`

- **pod_affinity_term** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term))
- **weight** (Number)

<a id="nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term"></a>
### Nested Schema for `spec.affinity.pod_affinity.required_during_scheduling_ignored_during_execution.pod_affinity_term`

- **label_selector** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term--label_selector))
- **namespaces** (Set of String)
- **topology_key** (String)

<a id="nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term--label_selector"></a>
### Nested Schema for `spec.affinity.pod_affinity.required_during_scheduling_ignored_during_execution.pod_affinity_term.topology_key`

- **match_expressions** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term--topology_key--match_expressions))
- **match_labels** (Map of String)

<a id="nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term--topology_key--match_expressions"></a>
### Nested Schema for `spec.affinity.pod_affinity.required_during_scheduling_ignored_during_execution.pod_affinity_term.topology_key.match_labels`

- **key** (String)
- **operator** (String)
- **values** (Set of String)





<a id="nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution"></a>
### Nested Schema for `spec.affinity.pod_affinity.required_during_scheduling_ignored_during_execution`

- **label_selector** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--label_selector))
- **namespaces** (Set of String)
- **topology_key** (String)

<a id="nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--label_selector"></a>
### Nested Schema for `spec.affinity.pod_affinity.required_during_scheduling_ignored_during_execution.label_selector`

- **match_expressions** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--label_selector--match_expressions))
- **match_labels** (Map of String)

<a id="nestedobjatt--spec--affinity--pod_affinity--required_during_scheduling_ignored_during_execution--label_selector--match_expressions"></a>
### Nested Schema for `spec.affinity.pod_affinity.required_during_scheduling_ignored_during_execution.label_selector.match_labels`

- **key** (String)
- **operator** (String)
- **values** (Set of String)





<a id="nestedobjatt--spec--affinity--pod_anti_affinity"></a>
### Nested Schema for `spec.affinity.pod_anti_affinity`

- **preferred_during_scheduling_ignored_during_execution** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_anti_affinity--preferred_during_scheduling_ignored_during_execution))
- **required_during_scheduling_ignored_during_execution** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution))

<a id="nestedobjatt--spec--affinity--pod_anti_affinity--preferred_during_scheduling_ignored_during_execution"></a>
### Nested Schema for `spec.affinity.pod_anti_affinity.required_during_scheduling_ignored_during_execution`

- **pod_affinity_term** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term))
- **weight** (Number)

<a id="nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term"></a>
### Nested Schema for `spec.affinity.pod_anti_affinity.required_during_scheduling_ignored_during_execution.pod_affinity_term`

- **label_selector** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term--label_selector))
- **namespaces** (Set of String)
- **topology_key** (String)

<a id="nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term--label_selector"></a>
### Nested Schema for `spec.affinity.pod_anti_affinity.required_during_scheduling_ignored_during_execution.pod_affinity_term.topology_key`

- **match_expressions** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term--topology_key--match_expressions))
- **match_labels** (Map of String)

<a id="nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--pod_affinity_term--topology_key--match_expressions"></a>
### Nested Schema for `spec.affinity.pod_anti_affinity.required_during_scheduling_ignored_during_execution.pod_affinity_term.topology_key.match_labels`

- **key** (String)
- **operator** (String)
- **values** (Set of String)





<a id="nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution"></a>
### Nested Schema for `spec.affinity.pod_anti_affinity.required_during_scheduling_ignored_during_execution`

- **label_selector** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--label_selector))
- **namespaces** (Set of String)
- **topology_key** (String)

<a id="nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--label_selector"></a>
### Nested Schema for `spec.affinity.pod_anti_affinity.required_during_scheduling_ignored_during_execution.label_selector`

- **match_expressions** (List of Object) (see [below for nested schema](#nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--label_selector--match_expressions))
- **match_labels** (Map of String)

<a id="nestedobjatt--spec--affinity--pod_anti_affinity--required_during_scheduling_ignored_during_execution--label_selector--match_expressions"></a>
### Nested Schema for `spec.affinity.pod_anti_affinity.required_during_scheduling_ignored_during_execution.label_selector.match_labels`

- **key** (String)
- **operator** (String)
- **values** (Set of String)






<a id="nestedobjatt--spec--container"></a>
### Nested Schema for `spec.container`

- **args** (List of String)
- **command** (List of String)
- **env** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--env))
- **env_from** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--env_from))
- **image** (String)
- **image_pull_policy** (String)
- **lifecycle** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle))
- **liveness_probe** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--liveness_probe))
- **name** (String)
- **port** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--port))
- **readiness_probe** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--readiness_probe))
- **resources** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--resources))
- **security_context** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--security_context))
- **startup_probe** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--startup_probe))
- **stdin** (Boolean)
- **stdin_once** (Boolean)
- **termination_message_path** (String)
- **termination_message_policy** (String)
- **tty** (Boolean)
- **volume_mount** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--volume_mount))
- **working_dir** (String)

<a id="nestedobjatt--spec--container--env"></a>
### Nested Schema for `spec.container.env`

- **name** (String)
- **value** (String)
- **value_from** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--env--value_from))

<a id="nestedobjatt--spec--container--env--value_from"></a>
### Nested Schema for `spec.container.env.value_from`

- **config_map_key_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--env--value_from--config_map_key_ref))
- **field_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--env--value_from--field_ref))
- **resource_field_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--env--value_from--resource_field_ref))
- **secret_key_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--env--value_from--secret_key_ref))

<a id="nestedobjatt--spec--container--env--value_from--config_map_key_ref"></a>
### Nested Schema for `spec.container.env.value_from.config_map_key_ref`

- **key** (String)
- **name** (String)
- **optional** (Boolean)


<a id="nestedobjatt--spec--container--env--value_from--field_ref"></a>
### Nested Schema for `spec.container.env.value_from.field_ref`

- **api_version** (String)
- **field_path** (String)


<a id="nestedobjatt--spec--container--env--value_from--resource_field_ref"></a>
### Nested Schema for `spec.container.env.value_from.resource_field_ref`

- **container_name** (String)
- **divisor** (String)
- **resource** (String)


<a id="nestedobjatt--spec--container--env--value_from--secret_key_ref"></a>
### Nested Schema for `spec.container.env.value_from.secret_key_ref`

- **key** (String)
- **name** (String)
- **optional** (Boolean)




<a id="nestedobjatt--spec--container--env_from"></a>
### Nested Schema for `spec.container.env_from`

- **config_map_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--env_from--config_map_ref))
- **prefix** (String)
- **secret_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--env_from--secret_ref))

<a id="nestedobjatt--spec--container--env_from--config_map_ref"></a>
### Nested Schema for `spec.container.env_from.secret_ref`

- **name** (String)
- **optional** (Boolean)


<a id="nestedobjatt--spec--container--env_from--secret_ref"></a>
### Nested Schema for `spec.container.env_from.secret_ref`

- **name** (String)
- **optional** (Boolean)



<a id="nestedobjatt--spec--container--lifecycle"></a>
### Nested Schema for `spec.container.lifecycle`

- **post_start** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--post_start))
- **pre_stop** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--pre_stop))

<a id="nestedobjatt--spec--container--lifecycle--post_start"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--pre_stop--exec))
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--pre_stop--http_get))
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--pre_stop--tcp_socket))

<a id="nestedobjatt--spec--container--lifecycle--pre_stop--exec"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop.exec`

- **command** (List of String)


<a id="nestedobjatt--spec--container--lifecycle--pre_stop--http_get"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop.http_get`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--pre_stop--http_get--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--container--lifecycle--pre_stop--http_get--http_header"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop.http_get.scheme`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--container--lifecycle--pre_stop--tcp_socket"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop.tcp_socket`

- **port** (String)



<a id="nestedobjatt--spec--container--lifecycle--pre_stop"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--pre_stop--exec))
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--pre_stop--http_get))
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--pre_stop--tcp_socket))

<a id="nestedobjatt--spec--container--lifecycle--pre_stop--exec"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop.exec`

- **command** (List of String)


<a id="nestedobjatt--spec--container--lifecycle--pre_stop--http_get"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop.http_get`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--lifecycle--pre_stop--http_get--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--container--lifecycle--pre_stop--http_get--http_header"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop.http_get.scheme`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--container--lifecycle--pre_stop--tcp_socket"></a>
### Nested Schema for `spec.container.lifecycle.pre_stop.tcp_socket`

- **port** (String)




<a id="nestedobjatt--spec--container--liveness_probe"></a>
### Nested Schema for `spec.container.liveness_probe`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--liveness_probe--exec))
- **failure_threshold** (Number)
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--liveness_probe--http_get))
- **initial_delay_seconds** (Number)
- **period_seconds** (Number)
- **success_threshold** (Number)
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--liveness_probe--tcp_socket))
- **timeout_seconds** (Number)

<a id="nestedobjatt--spec--container--liveness_probe--exec"></a>
### Nested Schema for `spec.container.liveness_probe.timeout_seconds`

- **command** (List of String)


<a id="nestedobjatt--spec--container--liveness_probe--http_get"></a>
### Nested Schema for `spec.container.liveness_probe.timeout_seconds`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--liveness_probe--timeout_seconds--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--container--liveness_probe--timeout_seconds--http_header"></a>
### Nested Schema for `spec.container.liveness_probe.timeout_seconds.http_header`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--container--liveness_probe--tcp_socket"></a>
### Nested Schema for `spec.container.liveness_probe.timeout_seconds`

- **port** (String)



<a id="nestedobjatt--spec--container--port"></a>
### Nested Schema for `spec.container.port`

- **container_port** (Number)
- **host_ip** (String)
- **host_port** (Number)
- **name** (String)
- **protocol** (String)


<a id="nestedobjatt--spec--container--readiness_probe"></a>
### Nested Schema for `spec.container.readiness_probe`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--readiness_probe--exec))
- **failure_threshold** (Number)
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--readiness_probe--http_get))
- **initial_delay_seconds** (Number)
- **period_seconds** (Number)
- **success_threshold** (Number)
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--readiness_probe--tcp_socket))
- **timeout_seconds** (Number)

<a id="nestedobjatt--spec--container--readiness_probe--exec"></a>
### Nested Schema for `spec.container.readiness_probe.timeout_seconds`

- **command** (List of String)


<a id="nestedobjatt--spec--container--readiness_probe--http_get"></a>
### Nested Schema for `spec.container.readiness_probe.timeout_seconds`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--readiness_probe--timeout_seconds--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--container--readiness_probe--timeout_seconds--http_header"></a>
### Nested Schema for `spec.container.readiness_probe.timeout_seconds.http_header`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--container--readiness_probe--tcp_socket"></a>
### Nested Schema for `spec.container.readiness_probe.timeout_seconds`

- **port** (String)



<a id="nestedobjatt--spec--container--resources"></a>
### Nested Schema for `spec.container.resources`

- **limits** (Map of String)
- **requests** (Map of String)


<a id="nestedobjatt--spec--container--security_context"></a>
### Nested Schema for `spec.container.security_context`

- **allow_privilege_escalation** (Boolean)
- **capabilities** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--security_context--capabilities))
- **privileged** (Boolean)
- **read_only_root_filesystem** (Boolean)
- **run_as_group** (Number)
- **run_as_non_root** (Boolean)
- **run_as_user** (Number)
- **se_linux_options** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--security_context--se_linux_options))

<a id="nestedobjatt--spec--container--security_context--capabilities"></a>
### Nested Schema for `spec.container.security_context.se_linux_options`

- **add** (List of String)
- **drop** (List of String)


<a id="nestedobjatt--spec--container--security_context--se_linux_options"></a>
### Nested Schema for `spec.container.security_context.se_linux_options`

- **level** (String)
- **role** (String)
- **type** (String)
- **user** (String)



<a id="nestedobjatt--spec--container--startup_probe"></a>
### Nested Schema for `spec.container.startup_probe`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--startup_probe--exec))
- **failure_threshold** (Number)
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--startup_probe--http_get))
- **initial_delay_seconds** (Number)
- **period_seconds** (Number)
- **success_threshold** (Number)
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--startup_probe--tcp_socket))
- **timeout_seconds** (Number)

<a id="nestedobjatt--spec--container--startup_probe--exec"></a>
### Nested Schema for `spec.container.startup_probe.timeout_seconds`

- **command** (List of String)


<a id="nestedobjatt--spec--container--startup_probe--http_get"></a>
### Nested Schema for `spec.container.startup_probe.timeout_seconds`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--container--startup_probe--timeout_seconds--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--container--startup_probe--timeout_seconds--http_header"></a>
### Nested Schema for `spec.container.startup_probe.timeout_seconds.http_header`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--container--startup_probe--tcp_socket"></a>
### Nested Schema for `spec.container.startup_probe.timeout_seconds`

- **port** (String)



<a id="nestedobjatt--spec--container--volume_mount"></a>
### Nested Schema for `spec.container.volume_mount`

- **mount_path** (String)
- **mount_propagation** (String)
- **name** (String)
- **read_only** (Boolean)
- **sub_path** (String)



<a id="nestedobjatt--spec--dns_config"></a>
### Nested Schema for `spec.dns_config`

- **nameservers** (List of String)
- **option** (List of Object) (see [below for nested schema](#nestedobjatt--spec--dns_config--option))
- **searches** (List of String)

<a id="nestedobjatt--spec--dns_config--option"></a>
### Nested Schema for `spec.dns_config.option`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--host_aliases"></a>
### Nested Schema for `spec.host_aliases`

- **hostnames** (List of String)
- **ip** (String)


<a id="nestedobjatt--spec--image_pull_secrets"></a>
### Nested Schema for `spec.image_pull_secrets`

- **name** (String)


<a id="nestedobjatt--spec--init_container"></a>
### Nested Schema for `spec.init_container`

- **args** (List of String)
- **command** (List of String)
- **env** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--env))
- **env_from** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--env_from))
- **image** (String)
- **image_pull_policy** (String)
- **lifecycle** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle))
- **liveness_probe** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--liveness_probe))
- **name** (String)
- **port** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--port))
- **readiness_probe** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--readiness_probe))
- **resources** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--resources))
- **security_context** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--security_context))
- **startup_probe** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--startup_probe))
- **stdin** (Boolean)
- **stdin_once** (Boolean)
- **termination_message_path** (String)
- **termination_message_policy** (String)
- **tty** (Boolean)
- **volume_mount** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--volume_mount))
- **working_dir** (String)

<a id="nestedobjatt--spec--init_container--env"></a>
### Nested Schema for `spec.init_container.env`

- **name** (String)
- **value** (String)
- **value_from** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--env--value_from))

<a id="nestedobjatt--spec--init_container--env--value_from"></a>
### Nested Schema for `spec.init_container.env.value_from`

- **config_map_key_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--env--value_from--config_map_key_ref))
- **field_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--env--value_from--field_ref))
- **resource_field_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--env--value_from--resource_field_ref))
- **secret_key_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--env--value_from--secret_key_ref))

<a id="nestedobjatt--spec--init_container--env--value_from--config_map_key_ref"></a>
### Nested Schema for `spec.init_container.env.value_from.config_map_key_ref`

- **key** (String)
- **name** (String)
- **optional** (Boolean)


<a id="nestedobjatt--spec--init_container--env--value_from--field_ref"></a>
### Nested Schema for `spec.init_container.env.value_from.field_ref`

- **api_version** (String)
- **field_path** (String)


<a id="nestedobjatt--spec--init_container--env--value_from--resource_field_ref"></a>
### Nested Schema for `spec.init_container.env.value_from.resource_field_ref`

- **container_name** (String)
- **divisor** (String)
- **resource** (String)


<a id="nestedobjatt--spec--init_container--env--value_from--secret_key_ref"></a>
### Nested Schema for `spec.init_container.env.value_from.secret_key_ref`

- **key** (String)
- **name** (String)
- **optional** (Boolean)




<a id="nestedobjatt--spec--init_container--env_from"></a>
### Nested Schema for `spec.init_container.env_from`

- **config_map_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--env_from--config_map_ref))
- **prefix** (String)
- **secret_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--env_from--secret_ref))

<a id="nestedobjatt--spec--init_container--env_from--config_map_ref"></a>
### Nested Schema for `spec.init_container.env_from.secret_ref`

- **name** (String)
- **optional** (Boolean)


<a id="nestedobjatt--spec--init_container--env_from--secret_ref"></a>
### Nested Schema for `spec.init_container.env_from.secret_ref`

- **name** (String)
- **optional** (Boolean)



<a id="nestedobjatt--spec--init_container--lifecycle"></a>
### Nested Schema for `spec.init_container.lifecycle`

- **post_start** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--post_start))
- **pre_stop** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--pre_stop))

<a id="nestedobjatt--spec--init_container--lifecycle--post_start"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--pre_stop--exec))
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--pre_stop--http_get))
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--pre_stop--tcp_socket))

<a id="nestedobjatt--spec--init_container--lifecycle--pre_stop--exec"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop.exec`

- **command** (List of String)


<a id="nestedobjatt--spec--init_container--lifecycle--pre_stop--http_get"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop.http_get`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--pre_stop--http_get--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--init_container--lifecycle--pre_stop--http_get--http_header"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop.http_get.scheme`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--init_container--lifecycle--pre_stop--tcp_socket"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop.tcp_socket`

- **port** (String)



<a id="nestedobjatt--spec--init_container--lifecycle--pre_stop"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--pre_stop--exec))
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--pre_stop--http_get))
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--pre_stop--tcp_socket))

<a id="nestedobjatt--spec--init_container--lifecycle--pre_stop--exec"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop.exec`

- **command** (List of String)


<a id="nestedobjatt--spec--init_container--lifecycle--pre_stop--http_get"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop.http_get`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--lifecycle--pre_stop--http_get--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--init_container--lifecycle--pre_stop--http_get--http_header"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop.http_get.scheme`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--init_container--lifecycle--pre_stop--tcp_socket"></a>
### Nested Schema for `spec.init_container.lifecycle.pre_stop.tcp_socket`

- **port** (String)




<a id="nestedobjatt--spec--init_container--liveness_probe"></a>
### Nested Schema for `spec.init_container.liveness_probe`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--liveness_probe--exec))
- **failure_threshold** (Number)
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--liveness_probe--http_get))
- **initial_delay_seconds** (Number)
- **period_seconds** (Number)
- **success_threshold** (Number)
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--liveness_probe--tcp_socket))
- **timeout_seconds** (Number)

<a id="nestedobjatt--spec--init_container--liveness_probe--exec"></a>
### Nested Schema for `spec.init_container.liveness_probe.timeout_seconds`

- **command** (List of String)


<a id="nestedobjatt--spec--init_container--liveness_probe--http_get"></a>
### Nested Schema for `spec.init_container.liveness_probe.timeout_seconds`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--liveness_probe--timeout_seconds--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--init_container--liveness_probe--timeout_seconds--http_header"></a>
### Nested Schema for `spec.init_container.liveness_probe.timeout_seconds.http_header`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--init_container--liveness_probe--tcp_socket"></a>
### Nested Schema for `spec.init_container.liveness_probe.timeout_seconds`

- **port** (String)



<a id="nestedobjatt--spec--init_container--port"></a>
### Nested Schema for `spec.init_container.port`

- **container_port** (Number)
- **host_ip** (String)
- **host_port** (Number)
- **name** (String)
- **protocol** (String)


<a id="nestedobjatt--spec--init_container--readiness_probe"></a>
### Nested Schema for `spec.init_container.readiness_probe`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--readiness_probe--exec))
- **failure_threshold** (Number)
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--readiness_probe--http_get))
- **initial_delay_seconds** (Number)
- **period_seconds** (Number)
- **success_threshold** (Number)
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--readiness_probe--tcp_socket))
- **timeout_seconds** (Number)

<a id="nestedobjatt--spec--init_container--readiness_probe--exec"></a>
### Nested Schema for `spec.init_container.readiness_probe.timeout_seconds`

- **command** (List of String)


<a id="nestedobjatt--spec--init_container--readiness_probe--http_get"></a>
### Nested Schema for `spec.init_container.readiness_probe.timeout_seconds`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--readiness_probe--timeout_seconds--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--init_container--readiness_probe--timeout_seconds--http_header"></a>
### Nested Schema for `spec.init_container.readiness_probe.timeout_seconds.http_header`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--init_container--readiness_probe--tcp_socket"></a>
### Nested Schema for `spec.init_container.readiness_probe.timeout_seconds`

- **port** (String)



<a id="nestedobjatt--spec--init_container--resources"></a>
### Nested Schema for `spec.init_container.resources`

- **limits** (Map of String)
- **requests** (Map of String)


<a id="nestedobjatt--spec--init_container--security_context"></a>
### Nested Schema for `spec.init_container.security_context`

- **allow_privilege_escalation** (Boolean)
- **capabilities** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--security_context--capabilities))
- **privileged** (Boolean)
- **read_only_root_filesystem** (Boolean)
- **run_as_group** (Number)
- **run_as_non_root** (Boolean)
- **run_as_user** (Number)
- **se_linux_options** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--security_context--se_linux_options))

<a id="nestedobjatt--spec--init_container--security_context--capabilities"></a>
### Nested Schema for `spec.init_container.security_context.se_linux_options`

- **add** (List of String)
- **drop** (List of String)


<a id="nestedobjatt--spec--init_container--security_context--se_linux_options"></a>
### Nested Schema for `spec.init_container.security_context.se_linux_options`

- **level** (String)
- **role** (String)
- **type** (String)
- **user** (String)



<a id="nestedobjatt--spec--init_container--startup_probe"></a>
### Nested Schema for `spec.init_container.startup_probe`

- **exec** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--startup_probe--exec))
- **failure_threshold** (Number)
- **http_get** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--startup_probe--http_get))
- **initial_delay_seconds** (Number)
- **period_seconds** (Number)
- **success_threshold** (Number)
- **tcp_socket** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--startup_probe--tcp_socket))
- **timeout_seconds** (Number)

<a id="nestedobjatt--spec--init_container--startup_probe--exec"></a>
### Nested Schema for `spec.init_container.startup_probe.timeout_seconds`

- **command** (List of String)


<a id="nestedobjatt--spec--init_container--startup_probe--http_get"></a>
### Nested Schema for `spec.init_container.startup_probe.timeout_seconds`

- **host** (String)
- **http_header** (List of Object) (see [below for nested schema](#nestedobjatt--spec--init_container--startup_probe--timeout_seconds--http_header))
- **path** (String)
- **port** (String)
- **scheme** (String)

<a id="nestedobjatt--spec--init_container--startup_probe--timeout_seconds--http_header"></a>
### Nested Schema for `spec.init_container.startup_probe.timeout_seconds.http_header`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--init_container--startup_probe--tcp_socket"></a>
### Nested Schema for `spec.init_container.startup_probe.timeout_seconds`

- **port** (String)



<a id="nestedobjatt--spec--init_container--volume_mount"></a>
### Nested Schema for `spec.init_container.volume_mount`

- **mount_path** (String)
- **mount_propagation** (String)
- **name** (String)
- **read_only** (Boolean)
- **sub_path** (String)



<a id="nestedobjatt--spec--readiness_gate"></a>
### Nested Schema for `spec.readiness_gate`

- **condition_type** (String)


<a id="nestedobjatt--spec--security_context"></a>
### Nested Schema for `spec.security_context`

- **fs_group** (Number)
- **run_as_group** (Number)
- **run_as_non_root** (Boolean)
- **run_as_user** (Number)
- **se_linux_options** (List of Object) (see [below for nested schema](#nestedobjatt--spec--security_context--se_linux_options))
- **supplemental_groups** (Set of Number)
- **sysctl** (List of Object) (see [below for nested schema](#nestedobjatt--spec--security_context--sysctl))

<a id="nestedobjatt--spec--security_context--se_linux_options"></a>
### Nested Schema for `spec.security_context.se_linux_options`

- **level** (String)
- **role** (String)
- **type** (String)
- **user** (String)


<a id="nestedobjatt--spec--security_context--sysctl"></a>
### Nested Schema for `spec.security_context.sysctl`

- **name** (String)
- **value** (String)



<a id="nestedobjatt--spec--toleration"></a>
### Nested Schema for `spec.toleration`

- **effect** (String)
- **key** (String)
- **operator** (String)
- **toleration_seconds** (String)
- **value** (String)


<a id="nestedobjatt--spec--volume"></a>
### Nested Schema for `spec.volume`

- **aws_elastic_block_store** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--aws_elastic_block_store))
- **azure_disk** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--azure_disk))
- **azure_file** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--azure_file))
- **ceph_fs** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--ceph_fs))
- **cinder** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--cinder))
- **config_map** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--config_map))
- **csi** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--csi))
- **downward_api** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--downward_api))
- **empty_dir** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--empty_dir))
- **fc** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--fc))
- **flex_volume** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--flex_volume))
- **flocker** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--flocker))
- **gce_persistent_disk** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--gce_persistent_disk))
- **git_repo** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--git_repo))
- **glusterfs** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--glusterfs))
- **host_path** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--host_path))
- **iscsi** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--iscsi))
- **local** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--local))
- **name** (String)
- **nfs** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--nfs))
- **persistent_volume_claim** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--persistent_volume_claim))
- **photon_persistent_disk** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--photon_persistent_disk))
- **projected** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected))
- **quobyte** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--quobyte))
- **rbd** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--rbd))
- **secret** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--secret))
- **vsphere_volume** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--vsphere_volume))

<a id="nestedobjatt--spec--volume--aws_elastic_block_store"></a>
### Nested Schema for `spec.volume.aws_elastic_block_store`

- **fs_type** (String)
- **partition** (Number)
- **read_only** (Boolean)
- **volume_id** (String)


<a id="nestedobjatt--spec--volume--azure_disk"></a>
### Nested Schema for `spec.volume.azure_disk`

- **caching_mode** (String)
- **data_disk_uri** (String)
- **disk_name** (String)
- **fs_type** (String)
- **kind** (String)
- **read_only** (Boolean)


<a id="nestedobjatt--spec--volume--azure_file"></a>
### Nested Schema for `spec.volume.azure_file`

- **read_only** (Boolean)
- **secret_name** (String)
- **share_name** (String)


<a id="nestedobjatt--spec--volume--ceph_fs"></a>
### Nested Schema for `spec.volume.ceph_fs`

- **monitors** (Set of String)
- **path** (String)
- **read_only** (Boolean)
- **secret_file** (String)
- **secret_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--ceph_fs--secret_ref))
- **user** (String)

<a id="nestedobjatt--spec--volume--ceph_fs--secret_ref"></a>
### Nested Schema for `spec.volume.ceph_fs.user`

- **name** (String)
- **namespace** (String)



<a id="nestedobjatt--spec--volume--cinder"></a>
### Nested Schema for `spec.volume.cinder`

- **fs_type** (String)
- **read_only** (Boolean)
- **volume_id** (String)


<a id="nestedobjatt--spec--volume--config_map"></a>
### Nested Schema for `spec.volume.config_map`

- **default_mode** (String)
- **items** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--config_map--items))
- **name** (String)
- **optional** (Boolean)

<a id="nestedobjatt--spec--volume--config_map--items"></a>
### Nested Schema for `spec.volume.config_map.optional`

- **key** (String)
- **mode** (String)
- **path** (String)



<a id="nestedobjatt--spec--volume--csi"></a>
### Nested Schema for `spec.volume.csi`

- **controller_expand_secret_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--csi--controller_expand_secret_ref))
- **controller_publish_secret_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--csi--controller_publish_secret_ref))
- **driver** (String)
- **fs_type** (String)
- **node_publish_secret_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--csi--node_publish_secret_ref))
- **node_stage_secret_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--csi--node_stage_secret_ref))
- **read_only** (Boolean)
- **volume_attributes** (Map of String)
- **volume_handle** (String)

<a id="nestedobjatt--spec--volume--csi--controller_expand_secret_ref"></a>
### Nested Schema for `spec.volume.csi.volume_handle`

- **name** (String)
- **namespace** (String)


<a id="nestedobjatt--spec--volume--csi--controller_publish_secret_ref"></a>
### Nested Schema for `spec.volume.csi.volume_handle`

- **name** (String)
- **namespace** (String)


<a id="nestedobjatt--spec--volume--csi--node_publish_secret_ref"></a>
### Nested Schema for `spec.volume.csi.volume_handle`

- **name** (String)
- **namespace** (String)


<a id="nestedobjatt--spec--volume--csi--node_stage_secret_ref"></a>
### Nested Schema for `spec.volume.csi.volume_handle`

- **name** (String)
- **namespace** (String)



<a id="nestedobjatt--spec--volume--downward_api"></a>
### Nested Schema for `spec.volume.downward_api`

- **default_mode** (String)
- **items** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--downward_api--items))

<a id="nestedobjatt--spec--volume--downward_api--items"></a>
### Nested Schema for `spec.volume.downward_api.items`

- **field_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--downward_api--items--field_ref))
- **mode** (String)
- **path** (String)
- **resource_field_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--downward_api--items--resource_field_ref))

<a id="nestedobjatt--spec--volume--downward_api--items--field_ref"></a>
### Nested Schema for `spec.volume.downward_api.items.field_ref`

- **api_version** (String)
- **field_path** (String)


<a id="nestedobjatt--spec--volume--downward_api--items--resource_field_ref"></a>
### Nested Schema for `spec.volume.downward_api.items.resource_field_ref`

- **container_name** (String)
- **divisor** (String)
- **resource** (String)




<a id="nestedobjatt--spec--volume--empty_dir"></a>
### Nested Schema for `spec.volume.empty_dir`

- **medium** (String)
- **size_limit** (String)


<a id="nestedobjatt--spec--volume--fc"></a>
### Nested Schema for `spec.volume.fc`

- **fs_type** (String)
- **lun** (Number)
- **read_only** (Boolean)
- **target_ww_ns** (Set of String)


<a id="nestedobjatt--spec--volume--flex_volume"></a>
### Nested Schema for `spec.volume.flex_volume`

- **driver** (String)
- **fs_type** (String)
- **options** (Map of String)
- **read_only** (Boolean)
- **secret_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--flex_volume--secret_ref))

<a id="nestedobjatt--spec--volume--flex_volume--secret_ref"></a>
### Nested Schema for `spec.volume.flex_volume.secret_ref`

- **name** (String)
- **namespace** (String)



<a id="nestedobjatt--spec--volume--flocker"></a>
### Nested Schema for `spec.volume.flocker`

- **dataset_name** (String)
- **dataset_uuid** (String)


<a id="nestedobjatt--spec--volume--gce_persistent_disk"></a>
### Nested Schema for `spec.volume.gce_persistent_disk`

- **fs_type** (String)
- **partition** (Number)
- **pd_name** (String)
- **read_only** (Boolean)


<a id="nestedobjatt--spec--volume--git_repo"></a>
### Nested Schema for `spec.volume.git_repo`

- **directory** (String)
- **repository** (String)
- **revision** (String)


<a id="nestedobjatt--spec--volume--glusterfs"></a>
### Nested Schema for `spec.volume.glusterfs`

- **endpoints_name** (String)
- **path** (String)
- **read_only** (Boolean)


<a id="nestedobjatt--spec--volume--host_path"></a>
### Nested Schema for `spec.volume.host_path`

- **path** (String)
- **type** (String)


<a id="nestedobjatt--spec--volume--iscsi"></a>
### Nested Schema for `spec.volume.iscsi`

- **fs_type** (String)
- **iqn** (String)
- **iscsi_interface** (String)
- **lun** (Number)
- **read_only** (Boolean)
- **target_portal** (String)


<a id="nestedobjatt--spec--volume--local"></a>
### Nested Schema for `spec.volume.local`

- **path** (String)


<a id="nestedobjatt--spec--volume--nfs"></a>
### Nested Schema for `spec.volume.nfs`

- **path** (String)
- **read_only** (Boolean)
- **server** (String)


<a id="nestedobjatt--spec--volume--persistent_volume_claim"></a>
### Nested Schema for `spec.volume.persistent_volume_claim`

- **claim_name** (String)
- **read_only** (Boolean)


<a id="nestedobjatt--spec--volume--photon_persistent_disk"></a>
### Nested Schema for `spec.volume.photon_persistent_disk`

- **fs_type** (String)
- **pd_id** (String)


<a id="nestedobjatt--spec--volume--projected"></a>
### Nested Schema for `spec.volume.projected`

- **default_mode** (String)
- **sources** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources))

<a id="nestedobjatt--spec--volume--projected--sources"></a>
### Nested Schema for `spec.volume.projected.sources`

- **config_map** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources--config_map))
- **downward_api** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources--downward_api))
- **secret** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources--secret))
- **service_account_token** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources--service_account_token))

<a id="nestedobjatt--spec--volume--projected--sources--config_map"></a>
### Nested Schema for `spec.volume.projected.sources.config_map`

- **items** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources--config_map--items))
- **name** (String)
- **optional** (Boolean)

<a id="nestedobjatt--spec--volume--projected--sources--config_map--items"></a>
### Nested Schema for `spec.volume.projected.sources.config_map.optional`

- **key** (String)
- **mode** (String)
- **path** (String)



<a id="nestedobjatt--spec--volume--projected--sources--downward_api"></a>
### Nested Schema for `spec.volume.projected.sources.downward_api`

- **items** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources--downward_api--items))

<a id="nestedobjatt--spec--volume--projected--sources--downward_api--items"></a>
### Nested Schema for `spec.volume.projected.sources.downward_api.items`

- **field_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources--downward_api--items--field_ref))
- **mode** (String)
- **path** (String)
- **resource_field_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources--downward_api--items--resource_field_ref))

<a id="nestedobjatt--spec--volume--projected--sources--downward_api--items--field_ref"></a>
### Nested Schema for `spec.volume.projected.sources.downward_api.items.resource_field_ref`

- **api_version** (String)
- **field_path** (String)


<a id="nestedobjatt--spec--volume--projected--sources--downward_api--items--resource_field_ref"></a>
### Nested Schema for `spec.volume.projected.sources.downward_api.items.resource_field_ref`

- **container_name** (String)
- **quantity** (String)
- **resource** (String)




<a id="nestedobjatt--spec--volume--projected--sources--secret"></a>
### Nested Schema for `spec.volume.projected.sources.secret`

- **items** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--projected--sources--secret--items))
- **name** (String)
- **optional** (Boolean)

<a id="nestedobjatt--spec--volume--projected--sources--secret--items"></a>
### Nested Schema for `spec.volume.projected.sources.secret.optional`

- **key** (String)
- **mode** (String)
- **path** (String)



<a id="nestedobjatt--spec--volume--projected--sources--service_account_token"></a>
### Nested Schema for `spec.volume.projected.sources.service_account_token`

- **audience** (String)
- **expiration_seconds** (Number)
- **path** (String)




<a id="nestedobjatt--spec--volume--quobyte"></a>
### Nested Schema for `spec.volume.quobyte`

- **group** (String)
- **read_only** (Boolean)
- **registry** (String)
- **user** (String)
- **volume** (String)


<a id="nestedobjatt--spec--volume--rbd"></a>
### Nested Schema for `spec.volume.rbd`

- **ceph_monitors** (Set of String)
- **fs_type** (String)
- **keyring** (String)
- **rados_user** (String)
- **rbd_image** (String)
- **rbd_pool** (String)
- **read_only** (Boolean)
- **secret_ref** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--rbd--secret_ref))

<a id="nestedobjatt--spec--volume--rbd--secret_ref"></a>
### Nested Schema for `spec.volume.rbd.secret_ref`

- **name** (String)
- **namespace** (String)



<a id="nestedobjatt--spec--volume--secret"></a>
### Nested Schema for `spec.volume.secret`

- **default_mode** (String)
- **items** (List of Object) (see [below for nested schema](#nestedobjatt--spec--volume--secret--items))
- **optional** (Boolean)
- **secret_name** (String)

<a id="nestedobjatt--spec--volume--secret--items"></a>
### Nested Schema for `spec.volume.secret.secret_name`

- **key** (String)
- **mode** (String)
- **path** (String)



<a id="nestedobjatt--spec--volume--vsphere_volume"></a>
### Nested Schema for `spec.volume.vsphere_volume`

- **fs_type** (String)
- **volume_path** (String)


