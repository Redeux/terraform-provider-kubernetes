---
page_title: "kubernetes Provider"
subcategory: ""
description: |-
  
---

# kubernetes Provider





## Schema

### Optional

- **client_certificate** (String, Optional) PEM-encoded client certificate for TLS authentication.
- **client_key** (String, Optional) PEM-encoded client certificate key for TLS authentication.
- **cluster_ca_certificate** (String, Optional) PEM-encoded root certificates bundle for TLS authentication.
- **config_context** (String, Optional)
- **config_context_auth_info** (String, Optional)
- **config_context_cluster** (String, Optional)
- **config_path** (String, Optional) Path to the kube config file, defaults to ~/.kube/config
- **exec** (Block List, Max: 1) (see [below for nested schema](#nestedblock--exec))
- **host** (String, Optional) The hostname (in form of URI) of Kubernetes master.
- **insecure** (Boolean, Optional) Whether server should be accessed without verifying the TLS certificate.
- **load_config_file** (Boolean, Optional) Load local kubeconfig.
- **password** (String, Optional) The password to use for HTTP basic authentication when accessing the Kubernetes master endpoint.
- **token** (String, Optional) Token to authenticate an service account
- **username** (String, Optional) The username to use for HTTP basic authentication when accessing the Kubernetes master endpoint.

<a id="nestedblock--exec"></a>
### Nested Schema for `exec`

Required:

- **api_version** (String, Required)
- **command** (String, Required)

Optional:

- **args** (List of String, Optional)
- **env** (Map of String, Optional)
