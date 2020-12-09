---
page_title: "kubernetes_network_policy Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_network_policy`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard network policy's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))
- **spec** (Block List, Min: 1, Max: 1) Specification of the desired behavior for this NetworkPolicy. (see [below for nested schema](#nestedblock--spec))

### Optional

- **id** (String, Optional) The ID of this resource.

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the network policy that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **generate_name** (String, Optional) Prefix, used by the server, to generate a unique name ONLY IF the `name` field has not been provided. This value will also be combined with a unique suffix. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#idempotency
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the network policy. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the network policy, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Namespace defines the space within which name of the network policy must be unique.

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this network policy that can be used by clients to determine when network policy has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this network policy.
- **uid** (String, Read-only) The unique in time and space value for this network policy. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--spec"></a>
### Nested Schema for `spec`

Required:

- **pod_selector** (Block List, Min: 1, Max: 1) Selects the pods to which this NetworkPolicy object applies. The array of ingress rules is applied to any pods selected by this field. Multiple network policies can select the same set of pods. In this case, the ingress rules for each are combined additively. This field is NOT optional and follows standard label selector semantics. An empty podSelector matches all pods in this namespace. (see [below for nested schema](#nestedblock--spec--pod_selector))
- **policy_types** (List of String, Required) List of rule types that the NetworkPolicy relates to. Valid options are "Ingress", "Egress", or "Ingress,Egress". If this field is not specified, it will default based on the existence of Ingress or Egress rules; policies that contain an Egress section are assumed to affect Egress, and all policies (whether or not they contain an Ingress section) are assumed to affect Ingress. If you want to write an egress-only policy, you must explicitly specify policyTypes [ "Egress" ]. Likewise, if you want to write a policy that specifies that no egress is allowed, you must specify a policyTypes value that include "Egress" (since such a policy would not include an Egress section and would otherwise default to just [ "Ingress" ]). This field is beta-level in 1.8

Optional:

- **egress** (Block List) List of egress rules to be applied to the selected pods. Outgoing traffic is allowed if there are no NetworkPolicies selecting the pod (and cluster policy otherwise allows the traffic), OR if the traffic matches at least one egress rule across all of the NetworkPolicy objects whose podSelector matches the pod. If this field is empty then this NetworkPolicy limits all outgoing traffic (and serves solely to ensure that the pods it selects are isolated by default). This field is beta-level in 1.8 (see [below for nested schema](#nestedblock--spec--egress))
- **ingress** (Block List) List of ingress rules to be applied to the selected pods. Traffic is allowed to a pod if there are no NetworkPolicies selecting the pod (and cluster policy otherwise allows the traffic), OR if the traffic source is the pod's local node, OR if the traffic matches at least one ingress rule across all of the NetworkPolicy objects whose podSelector matches the pod. If this field is empty then this NetworkPolicy does not allow any traffic (and serves solely to ensure that the pods it selects are isolated by default) (see [below for nested schema](#nestedblock--spec--ingress))

<a id="nestedblock--spec--pod_selector"></a>
### Nested Schema for `spec.pod_selector`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--pod_selector--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--spec--pod_selector--match_expressions"></a>
### Nested Schema for `spec.pod_selector.match_expressions`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.



<a id="nestedblock--spec--egress"></a>
### Nested Schema for `spec.egress`

Optional:

- **ports** (Block List) List of destination ports for outgoing traffic. Each item in this list is combined using a logical OR. If this field is empty or missing, this rule matches all ports (traffic not restricted by port). If this field is present and contains at least one item, then this rule allows traffic only if the traffic matches at least one port in the list. (see [below for nested schema](#nestedblock--spec--egress--ports))
- **to** (Block List) List of destinations for outgoing traffic of pods selected for this rule. Items in this list are combined using a logical OR operation. If this field is empty or missing, this rule matches all destinations (traffic not restricted by destination). If this field is present and contains at least one item, this rule allows traffic only if the traffic matches at least one item in the to list. (see [below for nested schema](#nestedblock--spec--egress--to))

<a id="nestedblock--spec--egress--ports"></a>
### Nested Schema for `spec.egress.ports`

Optional:

- **port** (String, Optional) The port on the given protocol. This can either be a numerical or named port on a pod. If this field is not provided, this matches all port names and numbers.
- **protocol** (String, Optional) The protocol (TCP, UDP, or SCTP) which traffic must match. If not specified, this field defaults to TCP.


<a id="nestedblock--spec--egress--to"></a>
### Nested Schema for `spec.egress.to`

Optional:

- **ip_block** (Block List, Max: 1) IPBlock defines policy on a particular IPBlock. If this field is set then neither of the other fields can be. (see [below for nested schema](#nestedblock--spec--egress--to--ip_block))
- **namespace_selector** (Block List, Max: 1) Selects Namespaces using cluster-scoped labels. This field follows standard label selector semantics; if present but empty, it selects all namespaces.

If PodSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects all Pods in the Namespaces selected by NamespaceSelector. (see [below for nested schema](#nestedblock--spec--egress--to--namespace_selector))
- **pod_selector** (Block List, Max: 1) This is a label selector which selects Pods. This field follows standard label selector semantics; if present but empty, it selects all pods.

If NamespaceSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects the Pods matching PodSelector in the policy's own Namespace. (see [below for nested schema](#nestedblock--spec--egress--to--pod_selector))

<a id="nestedblock--spec--egress--to--ip_block"></a>
### Nested Schema for `spec.egress.to.pod_selector`

Optional:

- **cidr** (String, Optional) CIDR is a string representing the IP Block Valid examples are "192.168.1.1/24" or "2001:db9::/64"
- **except** (List of String, Optional) Except is a slice of CIDRs that should not be included within an IP Block Valid examples are "192.168.1.1/24" or "2001:db9::/64" Except values will be rejected if they are outside the CIDR range


<a id="nestedblock--spec--egress--to--namespace_selector"></a>
### Nested Schema for `spec.egress.to.pod_selector`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--egress--to--pod_selector--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--spec--egress--to--pod_selector--match_expressions"></a>
### Nested Schema for `spec.egress.to.pod_selector.match_expressions`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.



<a id="nestedblock--spec--egress--to--pod_selector"></a>
### Nested Schema for `spec.egress.to.pod_selector`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--egress--to--pod_selector--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--spec--egress--to--pod_selector--match_expressions"></a>
### Nested Schema for `spec.egress.to.pod_selector.match_expressions`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.





<a id="nestedblock--spec--ingress"></a>
### Nested Schema for `spec.ingress`

Optional:

- **from** (Block List) List of sources which should be able to access the pods selected for this rule. Items in this list are combined using a logical OR operation. If this field is empty or missing, this rule matches all sources (traffic not restricted by source). If this field is present and contains at least one item, this rule allows traffic only if the traffic matches at least one item in the from list. (see [below for nested schema](#nestedblock--spec--ingress--from))
- **ports** (Block List) List of ports which should be made accessible on the pods selected for this rule. Each item in this list is combined using a logical OR. If this field is empty or missing, this rule matches all ports (traffic not restricted by port). If this field is present and contains at least one item, then this rule allows traffic only if the traffic matches at least one port in the list. (see [below for nested schema](#nestedblock--spec--ingress--ports))

<a id="nestedblock--spec--ingress--from"></a>
### Nested Schema for `spec.ingress.from`

Optional:

- **ip_block** (Block List, Max: 1) IPBlock defines policy on a particular IPBlock. If this field is set then neither of the other fields can be. (see [below for nested schema](#nestedblock--spec--ingress--from--ip_block))
- **namespace_selector** (Block List, Max: 1) Selects Namespaces using cluster-scoped labels. This field follows standard label selector semantics; if present but empty, it selects all namespaces.

If PodSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects all Pods in the Namespaces selected by NamespaceSelector. (see [below for nested schema](#nestedblock--spec--ingress--from--namespace_selector))
- **pod_selector** (Block List, Max: 1) This is a label selector which selects Pods. This field follows standard label selector semantics; if present but empty, it selects all pods.

If NamespaceSelector is also set, then the NetworkPolicyPeer as a whole selects the Pods matching PodSelector in the Namespaces selected by NamespaceSelector. Otherwise it selects the Pods matching PodSelector in the policy's own Namespace. (see [below for nested schema](#nestedblock--spec--ingress--from--pod_selector))

<a id="nestedblock--spec--ingress--from--ip_block"></a>
### Nested Schema for `spec.ingress.from.pod_selector`

Optional:

- **cidr** (String, Optional) CIDR is a string representing the IP Block Valid examples are "192.168.1.1/24" or "2001:db9::/64"
- **except** (List of String, Optional) Except is a slice of CIDRs that should not be included within an IP Block Valid examples are "192.168.1.1/24" or "2001:db9::/64" Except values will be rejected if they are outside the CIDR range


<a id="nestedblock--spec--ingress--from--namespace_selector"></a>
### Nested Schema for `spec.ingress.from.pod_selector`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--ingress--from--pod_selector--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--spec--ingress--from--pod_selector--match_expressions"></a>
### Nested Schema for `spec.ingress.from.pod_selector.match_expressions`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.



<a id="nestedblock--spec--ingress--from--pod_selector"></a>
### Nested Schema for `spec.ingress.from.pod_selector`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--ingress--from--pod_selector--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--spec--ingress--from--pod_selector--match_expressions"></a>
### Nested Schema for `spec.ingress.from.pod_selector.match_expressions`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.




<a id="nestedblock--spec--ingress--ports"></a>
### Nested Schema for `spec.ingress.ports`

Optional:

- **port** (String, Optional) The port on the given protocol. This can either be a numerical or named port on a pod. If this field is not provided, this matches all port names and numbers.
- **protocol** (String, Optional) The protocol (TCP, UDP, or SCTP) which traffic must match. If not specified, this field defaults to TCP.


