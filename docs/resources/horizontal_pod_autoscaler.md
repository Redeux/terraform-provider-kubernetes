---
page_title: "kubernetes_horizontal_pod_autoscaler Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_horizontal_pod_autoscaler`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard horizontal pod autoscaler's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))
- **spec** (Block List, Min: 1, Max: 1) Behaviour of the autoscaler. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#spec-and-status (see [below for nested schema](#nestedblock--spec))

### Optional

- **id** (String, Optional) The ID of this resource.

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the horizontal pod autoscaler that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the horizontal pod autoscaler. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the horizontal pod autoscaler, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the horizontal pod autoscaler must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this horizontal pod autoscaler that can be used by clients to determine when horizontal pod autoscaler has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this horizontal pod autoscaler.
- **uid** (String, Read-only) The unique in time and space value for this horizontal pod autoscaler. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--spec"></a>
### Nested Schema for `spec`

Required:

- **max_replicas** (Number, Required) Upper limit for the number of pods that can be set by the autoscaler.
- **scale_target_ref** (Block List, Min: 1, Max: 1) Reference to scaled resource. e.g. Replication Controller (see [below for nested schema](#nestedblock--spec--scale_target_ref))

Optional:

- **metric** (Block List) The specifications for which to use to calculate the desired replica count (the maximum replica count across all metrics will be used). The desired replica count is calculated multiplying the ratio between the target value and the current value by the current number of pods. Ergo, metrics used must decrease as the pod count is increased, and vice-versa. See the individual metric source types for more information about how each type of metric must respond. If not set, the default metric will be set to 80% average CPU utilization. (see [below for nested schema](#nestedblock--spec--metric))
- **min_replicas** (Number, Optional) Lower limit for the number of pods that can be set by the autoscaler, defaults to `1`.
- **target_cpu_utilization_percentage** (Number, Optional) Target average CPU utilization (represented as a percentage of requested CPU) over all the pods. If not specified the default autoscaling policy will be used.

<a id="nestedblock--spec--scale_target_ref"></a>
### Nested Schema for `spec.scale_target_ref`

Required:

- **kind** (String, Required) Kind of the referent. e.g. `ReplicationController`. More info: http://releases.k8s.io/HEAD/docs/devel/api-conventions.md#types-kinds
- **name** (String, Required) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names

Optional:

- **api_version** (String, Optional) API version of the referent


<a id="nestedblock--spec--metric"></a>
### Nested Schema for `spec.metric`

Required:

- **type** (String, Required) type is the type of metric source. It should be one of "Object", "Pods", "External" or "Resource", each mapping to a matching field in the object.

Optional:

- **external** (Block List, Max: 1) (see [below for nested schema](#nestedblock--spec--metric--external))
- **object** (Block List, Max: 1) (see [below for nested schema](#nestedblock--spec--metric--object))
- **pods** (Block List, Max: 1) (see [below for nested schema](#nestedblock--spec--metric--pods))
- **resource** (Block List, Max: 1) (see [below for nested schema](#nestedblock--spec--metric--resource))

<a id="nestedblock--spec--metric--external"></a>
### Nested Schema for `spec.metric.external`

Required:

- **metric** (Block List, Min: 1, Max: 1) metric identifies the target metric by name and selector (see [below for nested schema](#nestedblock--spec--metric--external--metric))

Optional:

- **target** (Block List, Max: 1) target specifies the target value for the given metric (see [below for nested schema](#nestedblock--spec--metric--external--target))

<a id="nestedblock--spec--metric--external--metric"></a>
### Nested Schema for `spec.metric.external.target`

Required:

- **name** (String, Required) name is the name of the given metric

Optional:

- **selector** (Block List) selector is the string-encoded form of a standard kubernetes label selector for the given metric When set, it is passed as an additional parameter to the metrics server for more specific metrics scoping. When unset, just the metricName will be used to gather metrics. (see [below for nested schema](#nestedblock--spec--metric--external--target--selector))

<a id="nestedblock--spec--metric--external--target--selector"></a>
### Nested Schema for `spec.metric.external.target.selector`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--metric--external--target--selector--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--spec--metric--external--target--selector--match_expressions"></a>
### Nested Schema for `spec.metric.external.target.selector.match_labels`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.




<a id="nestedblock--spec--metric--external--target"></a>
### Nested Schema for `spec.metric.external.target`

Required:

- **type** (String, Required) type represents whether the metric type is Utilization, Value, or AverageValue

Optional:

- **average_utilization** (Number, Optional) averageUtilization is the target value of the average of the resource metric across all relevant pods, represented as a percentage of the requested value of the resource for the pods. Currently only valid for Resource metric source type
- **average_value** (String, Optional) averageValue is the target value of the average of the metric across all relevant pods (as a quantity)
- **value** (String, Optional) value is the target value of the metric (as a quantity).



<a id="nestedblock--spec--metric--object"></a>
### Nested Schema for `spec.metric.object`

Required:

- **described_object** (Block List, Min: 1, Max: 1) (see [below for nested schema](#nestedblock--spec--metric--object--described_object))
- **metric** (Block List, Min: 1, Max: 1) metric identifies the target metric by name and selector (see [below for nested schema](#nestedblock--spec--metric--object--metric))

Optional:

- **target** (Block List, Max: 1) target specifies the target value for the given metric (see [below for nested schema](#nestedblock--spec--metric--object--target))

<a id="nestedblock--spec--metric--object--described_object"></a>
### Nested Schema for `spec.metric.object.target`

Required:

- **api_version** (String, Required) API version of the referent
- **kind** (String, Required) Kind of the referent; More info: https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#types-kinds
- **name** (String, Required) Name of the referent; More info: http://kubernetes.io/docs/user-guide/identifiers#names


<a id="nestedblock--spec--metric--object--metric"></a>
### Nested Schema for `spec.metric.object.target`

Required:

- **name** (String, Required) name is the name of the given metric

Optional:

- **selector** (Block List) selector is the string-encoded form of a standard kubernetes label selector for the given metric When set, it is passed as an additional parameter to the metrics server for more specific metrics scoping. When unset, just the metricName will be used to gather metrics. (see [below for nested schema](#nestedblock--spec--metric--object--target--selector))

<a id="nestedblock--spec--metric--object--target--selector"></a>
### Nested Schema for `spec.metric.object.target.selector`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--metric--object--target--selector--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--spec--metric--object--target--selector--match_expressions"></a>
### Nested Schema for `spec.metric.object.target.selector.match_labels`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.




<a id="nestedblock--spec--metric--object--target"></a>
### Nested Schema for `spec.metric.object.target`

Required:

- **type** (String, Required) type represents whether the metric type is Utilization, Value, or AverageValue

Optional:

- **average_utilization** (Number, Optional) averageUtilization is the target value of the average of the resource metric across all relevant pods, represented as a percentage of the requested value of the resource for the pods. Currently only valid for Resource metric source type
- **average_value** (String, Optional) averageValue is the target value of the average of the metric across all relevant pods (as a quantity)
- **value** (String, Optional) value is the target value of the metric (as a quantity).



<a id="nestedblock--spec--metric--pods"></a>
### Nested Schema for `spec.metric.pods`

Required:

- **metric** (Block List, Min: 1, Max: 1) metric identifies the target metric by name and selector (see [below for nested schema](#nestedblock--spec--metric--pods--metric))

Optional:

- **target** (Block List, Max: 1) target specifies the target value for the given metric (see [below for nested schema](#nestedblock--spec--metric--pods--target))

<a id="nestedblock--spec--metric--pods--metric"></a>
### Nested Schema for `spec.metric.pods.target`

Required:

- **name** (String, Required) name is the name of the given metric

Optional:

- **selector** (Block List) selector is the string-encoded form of a standard kubernetes label selector for the given metric When set, it is passed as an additional parameter to the metrics server for more specific metrics scoping. When unset, just the metricName will be used to gather metrics. (see [below for nested schema](#nestedblock--spec--metric--pods--target--selector))

<a id="nestedblock--spec--metric--pods--target--selector"></a>
### Nested Schema for `spec.metric.pods.target.selector`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--metric--pods--target--selector--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--spec--metric--pods--target--selector--match_expressions"></a>
### Nested Schema for `spec.metric.pods.target.selector.match_labels`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.




<a id="nestedblock--spec--metric--pods--target"></a>
### Nested Schema for `spec.metric.pods.target`

Required:

- **type** (String, Required) type represents whether the metric type is Utilization, Value, or AverageValue

Optional:

- **average_utilization** (Number, Optional) averageUtilization is the target value of the average of the resource metric across all relevant pods, represented as a percentage of the requested value of the resource for the pods. Currently only valid for Resource metric source type
- **average_value** (String, Optional) averageValue is the target value of the average of the metric across all relevant pods (as a quantity)
- **value** (String, Optional) value is the target value of the metric (as a quantity).



<a id="nestedblock--spec--metric--resource"></a>
### Nested Schema for `spec.metric.resource`

Required:

- **name** (String, Required) name is the name of the resource in question.

Optional:

- **target** (Block List, Max: 1) Target specifies the target value for the given metric (see [below for nested schema](#nestedblock--spec--metric--resource--target))

<a id="nestedblock--spec--metric--resource--target"></a>
### Nested Schema for `spec.metric.resource.target`

Required:

- **type** (String, Required) type represents whether the metric type is Utilization, Value, or AverageValue

Optional:

- **average_utilization** (Number, Optional) averageUtilization is the target value of the average of the resource metric across all relevant pods, represented as a percentage of the requested value of the resource for the pods. Currently only valid for Resource metric source type
- **average_value** (String, Optional) averageValue is the target value of the average of the metric across all relevant pods (as a quantity)
- **value** (String, Optional) value is the target value of the metric (as a quantity).


