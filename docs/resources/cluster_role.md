---
page_title: "kubernetes_cluster_role Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_cluster_role`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard clusterRole's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))

### Optional

- **aggregation_rule** (Block List, Max: 1) Describes how to build the Rules for this ClusterRole. (see [below for nested schema](#nestedblock--aggregation_rule))
- **id** (String, Optional) The ID of this resource.
- **rule** (Block List) List of PolicyRules for this ClusterRole (see [below for nested schema](#nestedblock--rule))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the clusterRole that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the clusterRole. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the clusterRole, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this clusterRole that can be used by clients to determine when clusterRole has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this clusterRole.
- **uid** (String, Read-only) The unique in time and space value for this clusterRole. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--aggregation_rule"></a>
### Nested Schema for `aggregation_rule`

Optional:

- **cluster_role_selectors** (Block List) A list of selectors which will be used to find ClusterRoles and create the rules. (see [below for nested schema](#nestedblock--aggregation_rule--cluster_role_selectors))

<a id="nestedblock--aggregation_rule--cluster_role_selectors"></a>
### Nested Schema for `aggregation_rule.cluster_role_selectors`

Optional:

- **match_expressions** (Block List) A list of label selector requirements. The requirements are ANDed. (see [below for nested schema](#nestedblock--aggregation_rule--cluster_role_selectors--match_expressions))
- **match_labels** (Map of String, Optional) A map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of `match_expressions`, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.

<a id="nestedblock--aggregation_rule--cluster_role_selectors--match_expressions"></a>
### Nested Schema for `aggregation_rule.cluster_role_selectors.match_expressions`

Optional:

- **key** (String, Optional) The label key that the selector applies to.
- **operator** (String, Optional) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists` and `DoesNotExist`.
- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.




<a id="nestedblock--rule"></a>
### Nested Schema for `rule`

Required:

- **verbs** (List of String, Required) Verbs is a list of Verbs that apply to ALL the ResourceKinds and AttributeRestrictions contained in this rule. VerbAll represents all kinds.

Optional:

- **api_groups** (List of String, Optional) APIGroups is the name of the APIGroup that contains the resources. If multiple API groups are specified, any action requested against one of the enumerated resources in any API group will be allowed.
- **non_resource_urls** (List of String, Optional) NonResourceURLs is a set of partial urls that a user should have access to. *s are allowed, but only as the full, final step in the path Since non-resource URLs are not namespaced, this field is only applicable for ClusterRoles referenced from a ClusterRoleBinding. Rules can either apply to API resources (such as "pods" or "secrets") or non-resource URL paths (such as "/api"), but not both.
- **resource_names** (List of String, Optional) ResourceNames is an optional white list of names that the rule applies to. An empty set means that everything is allowed.
- **resources** (List of String, Optional) Resources is a list of resources this rule applies to. ResourceAll represents all resources.


