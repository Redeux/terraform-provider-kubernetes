---
page_title: "kubernetes_persistent_volume Resource - terraform-provider-kubernetes"
subcategory: ""
description: |-
  
---

# Resource `kubernetes_persistent_volume`





## Schema

### Required

- **metadata** (Block List, Min: 1, Max: 1) Standard persistent volume's metadata. More info: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#metadata (see [below for nested schema](#nestedblock--metadata))
- **spec** (Block List, Min: 1) Spec of the persistent volume owned by the cluster (see [below for nested schema](#nestedblock--spec))

### Optional

- **id** (String, Optional) The ID of this resource.
- **timeouts** (Block, Optional) (see [below for nested schema](#nestedblock--timeouts))

<a id="nestedblock--metadata"></a>
### Nested Schema for `metadata`

Optional:

- **annotations** (Map of String, Optional) An unstructured key value map stored with the persistent volume that may be used to store arbitrary metadata. More info: http://kubernetes.io/docs/user-guide/annotations
- **labels** (Map of String, Optional) Map of string keys and values that can be used to organize and categorize (scope and select) the persistent volume. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels
- **name** (String, Optional) Name of the persistent volume, must be unique. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names

Read-only:

- **generation** (Number, Read-only) A sequence number representing a specific generation of the desired state.
- **resource_version** (String, Read-only) An opaque value that represents the internal version of this persistent volume that can be used by clients to determine when persistent volume has changed. Read more: https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api-conventions.md#concurrency-control-and-consistency
- **self_link** (String, Read-only) A URL representing this persistent volume.
- **uid** (String, Read-only) The unique in time and space value for this persistent volume. More info: http://kubernetes.io/docs/user-guide/identifiers#uids


<a id="nestedblock--spec"></a>
### Nested Schema for `spec`

Required:

- **access_modes** (Set of String, Required) Contains all ways the volume can be mounted. More info: http://kubernetes.io/docs/user-guide/persistent-volumes#access-modes
- **capacity** (Map of String, Required) A description of the persistent volume's resources and capacity. More info: http://kubernetes.io/docs/user-guide/persistent-volumes#capacity
- **persistent_volume_source** (Block List, Min: 1, Max: 1) The specification of a persistent volume. (see [below for nested schema](#nestedblock--spec--persistent_volume_source))

Optional:

- **mount_options** (Set of String, Optional) A list of mount options, e.g. ["ro", "soft"]. Not validated - mount will simply fail if one is invalid.
- **node_affinity** (Block List, Max: 1) A description of the persistent volume's node affinity. More info: https://kubernetes.io/docs/concepts/storage/volumes/#local (see [below for nested schema](#nestedblock--spec--node_affinity))
- **persistent_volume_reclaim_policy** (String, Optional) What happens to a persistent volume when released from its claim. Valid options are Retain (default) and Recycle. Recycling must be supported by the volume plugin underlying this persistent volume. More info: http://kubernetes.io/docs/user-guide/persistent-volumes#recycling-policy
- **storage_class_name** (String, Optional) A description of the persistent volume's class. More info: https://kubernetes.io/docs/concepts/storage/persistent-volumes/#class
- **volume_mode** (String, Optional) Defines if a volume is intended to be used with a formatted filesystem. or to remain in raw block state.

<a id="nestedblock--spec--persistent_volume_source"></a>
### Nested Schema for `spec.persistent_volume_source`

Optional:

- **aws_elastic_block_store** (Block List, Max: 1) Represents an AWS Disk resource that is attached to a kubelet's host machine and then exposed to the pod. More info: http://kubernetes.io/docs/user-guide/volumes#awselasticblockstore (see [below for nested schema](#nestedblock--spec--persistent_volume_source--aws_elastic_block_store))
- **azure_disk** (Block List, Max: 1) Represents an Azure Data Disk mount on the host and bind mount to the pod. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--azure_disk))
- **azure_file** (Block List, Max: 1) Represents an Azure File Service mount on the host and bind mount to the pod. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--azure_file))
- **ceph_fs** (Block List, Max: 1) Represents a Ceph FS mount on the host that shares a pod's lifetime (see [below for nested schema](#nestedblock--spec--persistent_volume_source--ceph_fs))
- **cinder** (Block List, Max: 1) Represents a cinder volume attached and mounted on kubelets host machine. More info: http://releases.k8s.io/HEAD/examples/mysql-cinder-pd/README.md (see [below for nested schema](#nestedblock--spec--persistent_volume_source--cinder))
- **csi** (Block List, Max: 1) Represents a CSI Volume. More info: http://kubernetes.io/docs/user-guide/volumes#csi (see [below for nested schema](#nestedblock--spec--persistent_volume_source--csi))
- **fc** (Block List, Max: 1) Represents a Fibre Channel resource that is attached to a kubelet's host machine and then exposed to the pod. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--fc))
- **flex_volume** (Block List, Max: 1) Represents a generic volume resource that is provisioned/attached using an exec based plugin. This is an alpha feature and may change in future. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--flex_volume))
- **flocker** (Block List, Max: 1) Represents a Flocker volume attached to a kubelet's host machine and exposed to the pod for its usage. This depends on the Flocker control service being running (see [below for nested schema](#nestedblock--spec--persistent_volume_source--flocker))
- **gce_persistent_disk** (Block List, Max: 1) Represents a GCE Disk resource that is attached to a kubelet's host machine and then exposed to the pod. Provisioned by an admin. More info: http://kubernetes.io/docs/user-guide/volumes#gcepersistentdisk (see [below for nested schema](#nestedblock--spec--persistent_volume_source--gce_persistent_disk))
- **glusterfs** (Block List, Max: 1) Represents a Glusterfs volume that is attached to a host and exposed to the pod. Provisioned by an admin. More info: http://releases.k8s.io/HEAD/examples/volumes/glusterfs/README.md (see [below for nested schema](#nestedblock--spec--persistent_volume_source--glusterfs))
- **host_path** (Block List, Max: 1) Represents a directory on the host. Provisioned by a developer or tester. This is useful for single-node development and testing only! On-host storage is not supported in any way and WILL NOT WORK in a multi-node cluster. More info: http://kubernetes.io/docs/user-guide/volumes#hostpath (see [below for nested schema](#nestedblock--spec--persistent_volume_source--host_path))
- **iscsi** (Block List, Max: 1) Represents an ISCSI Disk resource that is attached to a kubelet's host machine and then exposed to the pod. Provisioned by an admin. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--iscsi))
- **local** (Block List, Max: 1) Represents a mounted local storage device such as a disk, partition or directory. Local volumes can only be used as a statically created PersistentVolume. Dynamic provisioning is not supported yet. More info: http://kubernetes.io/docs/user-guide/volumes#local (see [below for nested schema](#nestedblock--spec--persistent_volume_source--local))
- **nfs** (Block List, Max: 1) Represents an NFS mount on the host. Provisioned by an admin. More info: http://kubernetes.io/docs/user-guide/volumes#nfs (see [below for nested schema](#nestedblock--spec--persistent_volume_source--nfs))
- **photon_persistent_disk** (Block List, Max: 1) Represents a PhotonController persistent disk attached and mounted on kubelets host machine (see [below for nested schema](#nestedblock--spec--persistent_volume_source--photon_persistent_disk))
- **quobyte** (Block List, Max: 1) Quobyte represents a Quobyte mount on the host that shares a pod's lifetime (see [below for nested schema](#nestedblock--spec--persistent_volume_source--quobyte))
- **rbd** (Block List, Max: 1) Represents a Rados Block Device mount on the host that shares a pod's lifetime. More info: http://releases.k8s.io/HEAD/examples/volumes/rbd/README.md (see [below for nested schema](#nestedblock--spec--persistent_volume_source--rbd))
- **vsphere_volume** (Block List, Max: 1) Represents a vSphere volume attached and mounted on kubelets host machine (see [below for nested schema](#nestedblock--spec--persistent_volume_source--vsphere_volume))

<a id="nestedblock--spec--persistent_volume_source--aws_elastic_block_store"></a>
### Nested Schema for `spec.persistent_volume_source.aws_elastic_block_store`

Required:

- **volume_id** (String, Required) Unique ID of the persistent disk resource in AWS (Amazon EBS volume). More info: http://kubernetes.io/docs/user-guide/volumes#awselasticblockstore

Optional:

- **fs_type** (String, Optional) Filesystem type of the volume that you want to mount. Tip: Ensure that the filesystem type is supported by the host operating system. Examples: "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified. More info: http://kubernetes.io/docs/user-guide/volumes#awselasticblockstore
- **partition** (Number, Optional) The partition in the volume that you want to mount. If omitted, the default is to mount by volume name. Examples: For volume /dev/sda1, you specify the partition as "1". Similarly, the volume partition for /dev/sda is "0" (or you can leave the property empty).
- **read_only** (Boolean, Optional) Whether to set the read-only property in VolumeMounts to "true". If omitted, the default is "false". More info: http://kubernetes.io/docs/user-guide/volumes#awselasticblockstore


<a id="nestedblock--spec--persistent_volume_source--azure_disk"></a>
### Nested Schema for `spec.persistent_volume_source.azure_disk`

Required:

- **caching_mode** (String, Required) Host Caching mode: None, Read Only, Read Write.
- **data_disk_uri** (String, Required) The URI the data disk in the blob storage
- **disk_name** (String, Required) The Name of the data disk in the blob storage

Optional:

- **fs_type** (String, Optional) Filesystem type to mount. Must be a filesystem type supported by the host operating system. Ex. "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified.
- **kind** (String, Optional) The type for the data disk. Expected values: Shared, Dedicated, Managed. Defaults to Shared
- **read_only** (Boolean, Optional) Whether to force the read-only setting in VolumeMounts. Defaults to false (read/write).


<a id="nestedblock--spec--persistent_volume_source--azure_file"></a>
### Nested Schema for `spec.persistent_volume_source.azure_file`

Required:

- **secret_name** (String, Required) The name of secret that contains Azure Storage Account Name and Key
- **share_name** (String, Required) Share Name

Optional:

- **read_only** (Boolean, Optional) Whether to force the read-only setting in VolumeMounts. Defaults to false (read/write).


<a id="nestedblock--spec--persistent_volume_source--ceph_fs"></a>
### Nested Schema for `spec.persistent_volume_source.ceph_fs`

Required:

- **monitors** (Set of String, Required) Monitors is a collection of Ceph monitors More info: http://releases.k8s.io/HEAD/examples/volumes/cephfs/README.md#how-to-use-it

Optional:

- **path** (String, Optional) Used as the mounted root, rather than the full Ceph tree, default is /
- **read_only** (Boolean, Optional) Whether to force the read-only setting in VolumeMounts. Defaults to `false` (read/write). More info: http://releases.k8s.io/HEAD/examples/volumes/cephfs/README.md#how-to-use-it
- **secret_file** (String, Optional) The path to key ring for User, default is /etc/ceph/user.secret More info: http://releases.k8s.io/HEAD/examples/volumes/cephfs/README.md#how-to-use-it
- **secret_ref** (Block List, Max: 1) Reference to the authentication secret for User, default is empty. More info: http://releases.k8s.io/HEAD/examples/volumes/cephfs/README.md#how-to-use-it (see [below for nested schema](#nestedblock--spec--persistent_volume_source--ceph_fs--secret_ref))
- **user** (String, Optional) User is the rados user name, default is admin. More info: http://releases.k8s.io/HEAD/examples/volumes/cephfs/README.md#how-to-use-it

<a id="nestedblock--spec--persistent_volume_source--ceph_fs--secret_ref"></a>
### Nested Schema for `spec.persistent_volume_source.ceph_fs.user`

Optional:

- **name** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names



<a id="nestedblock--spec--persistent_volume_source--cinder"></a>
### Nested Schema for `spec.persistent_volume_source.cinder`

Required:

- **volume_id** (String, Required) Volume ID used to identify the volume in Cinder. More info: http://releases.k8s.io/HEAD/examples/mysql-cinder-pd/README.md

Optional:

- **fs_type** (String, Optional) Filesystem type to mount. Must be a filesystem type supported by the host operating system. Examples: "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified. More info: http://releases.k8s.io/HEAD/examples/mysql-cinder-pd/README.md
- **read_only** (Boolean, Optional) Whether to force the read-only setting in VolumeMounts. Defaults to false (read/write). More info: http://releases.k8s.io/HEAD/examples/mysql-cinder-pd/README.md


<a id="nestedblock--spec--persistent_volume_source--csi"></a>
### Nested Schema for `spec.persistent_volume_source.csi`

Required:

- **driver** (String, Required) the name of the volume driver to use. More info: https://kubernetes.io/docs/concepts/storage/volumes/#csi
- **volume_handle** (String, Required) A string value that uniquely identifies the volume. More info: https://kubernetes.io/docs/concepts/storage/volumes/#csi

Optional:

- **controller_expand_secret_ref** (Block List, Max: 1) A reference to the secret object containing sensitive information to pass to the CSI driver to complete the CSI ControllerExpandVolume call. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--csi--controller_expand_secret_ref))
- **controller_publish_secret_ref** (Block List, Max: 1) A reference to the secret object containing sensitive information to pass to the CSI driver to complete the CSI ControllerPublishVolume and ControllerUnpublishVolume calls. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--csi--controller_publish_secret_ref))
- **fs_type** (String, Optional) Filesystem type to mount. Must be a filesystem type supported by the host operating system. Ex. "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified.
- **node_publish_secret_ref** (Block List, Max: 1) A reference to the secret object containing sensitive information to pass to the CSI driver to complete the CSI NodePublishVolume and NodeUnpublishVolume calls. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--csi--node_publish_secret_ref))
- **node_stage_secret_ref** (Block List, Max: 1) A reference to the secret object containing sensitive information to pass to the CSI driver to complete the CSI NodeStageVolume and NodeStageVolume and NodeUnstageVolume calls. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--csi--node_stage_secret_ref))
- **read_only** (Boolean, Optional) Whether to set the read-only property in VolumeMounts to "true". If omitted, the default is "false". More info: http://kubernetes.io/docs/user-guide/volumes#csi
- **volume_attributes** (Map of String, Optional) Attributes of the volume to publish.

<a id="nestedblock--spec--persistent_volume_source--csi--controller_expand_secret_ref"></a>
### Nested Schema for `spec.persistent_volume_source.csi.volume_attributes`

Optional:

- **name** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names


<a id="nestedblock--spec--persistent_volume_source--csi--controller_publish_secret_ref"></a>
### Nested Schema for `spec.persistent_volume_source.csi.volume_attributes`

Optional:

- **name** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names


<a id="nestedblock--spec--persistent_volume_source--csi--node_publish_secret_ref"></a>
### Nested Schema for `spec.persistent_volume_source.csi.volume_attributes`

Optional:

- **name** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names


<a id="nestedblock--spec--persistent_volume_source--csi--node_stage_secret_ref"></a>
### Nested Schema for `spec.persistent_volume_source.csi.volume_attributes`

Optional:

- **name** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names



<a id="nestedblock--spec--persistent_volume_source--fc"></a>
### Nested Schema for `spec.persistent_volume_source.fc`

Required:

- **lun** (Number, Required) FC target lun number
- **target_ww_ns** (Set of String, Required) FC target worldwide names (WWNs)

Optional:

- **fs_type** (String, Optional) Filesystem type to mount. Must be a filesystem type supported by the host operating system. Ex. "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified.
- **read_only** (Boolean, Optional) Whether to force the read-only setting in VolumeMounts. Defaults to false (read/write).


<a id="nestedblock--spec--persistent_volume_source--flex_volume"></a>
### Nested Schema for `spec.persistent_volume_source.flex_volume`

Required:

- **driver** (String, Required) Driver is the name of the driver to use for this volume.

Optional:

- **fs_type** (String, Optional) Filesystem type to mount. Must be a filesystem type supported by the host operating system. Ex. "ext4", "xfs", "ntfs". The default filesystem depends on FlexVolume script.
- **options** (Map of String, Optional) Extra command options if any.
- **read_only** (Boolean, Optional) Whether to force the ReadOnly setting in VolumeMounts. Defaults to false (read/write).
- **secret_ref** (Block List, Max: 1) Reference to the secret object containing sensitive information to pass to the plugin scripts. This may be empty if no secret object is specified. If the secret object contains more than one secret, all secrets are passed to the plugin scripts. (see [below for nested schema](#nestedblock--spec--persistent_volume_source--flex_volume--secret_ref))

<a id="nestedblock--spec--persistent_volume_source--flex_volume--secret_ref"></a>
### Nested Schema for `spec.persistent_volume_source.flex_volume.secret_ref`

Optional:

- **name** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names



<a id="nestedblock--spec--persistent_volume_source--flocker"></a>
### Nested Schema for `spec.persistent_volume_source.flocker`

Optional:

- **dataset_name** (String, Optional) Name of the dataset stored as metadata -> name on the dataset for Flocker should be considered as deprecated
- **dataset_uuid** (String, Optional) UUID of the dataset. This is unique identifier of a Flocker dataset


<a id="nestedblock--spec--persistent_volume_source--gce_persistent_disk"></a>
### Nested Schema for `spec.persistent_volume_source.gce_persistent_disk`

Required:

- **pd_name** (String, Required) Unique name of the PD resource in GCE. Used to identify the disk in GCE. More info: http://kubernetes.io/docs/user-guide/volumes#gcepersistentdisk

Optional:

- **fs_type** (String, Optional) Filesystem type of the volume that you want to mount. Tip: Ensure that the filesystem type is supported by the host operating system. Examples: "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified. More info: http://kubernetes.io/docs/user-guide/volumes#gcepersistentdisk
- **partition** (Number, Optional) The partition in the volume that you want to mount. If omitted, the default is to mount by volume name. Examples: For volume /dev/sda1, you specify the partition as "1". Similarly, the volume partition for /dev/sda is "0" (or you can leave the property empty). More info: http://kubernetes.io/docs/user-guide/volumes#gcepersistentdisk
- **read_only** (Boolean, Optional) Whether to force the ReadOnly setting in VolumeMounts. Defaults to false. More info: http://kubernetes.io/docs/user-guide/volumes#gcepersistentdisk


<a id="nestedblock--spec--persistent_volume_source--glusterfs"></a>
### Nested Schema for `spec.persistent_volume_source.glusterfs`

Required:

- **endpoints_name** (String, Required) The endpoint name that details Glusterfs topology. More info: http://releases.k8s.io/HEAD/examples/volumes/glusterfs/README.md#create-a-pod
- **path** (String, Required) The Glusterfs volume path. More info: http://releases.k8s.io/HEAD/examples/volumes/glusterfs/README.md#create-a-pod

Optional:

- **read_only** (Boolean, Optional) Whether to force the Glusterfs volume to be mounted with read-only permissions. Defaults to false. More info: http://releases.k8s.io/HEAD/examples/volumes/glusterfs/README.md#create-a-pod


<a id="nestedblock--spec--persistent_volume_source--host_path"></a>
### Nested Schema for `spec.persistent_volume_source.host_path`

Optional:

- **path** (String, Optional) Path of the directory on the host. More info: http://kubernetes.io/docs/user-guide/volumes#hostpath
- **type** (String, Optional) Type for HostPath volume. Allowed values are "" (default), DirectoryOrCreate, Directory, FileOrCreate, File, Socket, CharDevice and BlockDevice


<a id="nestedblock--spec--persistent_volume_source--iscsi"></a>
### Nested Schema for `spec.persistent_volume_source.iscsi`

Required:

- **iqn** (String, Required) Target iSCSI Qualified Name.
- **target_portal** (String, Required) iSCSI target portal. The portal is either an IP or ip_addr:port if the port is other than default (typically TCP ports 860 and 3260).

Optional:

- **fs_type** (String, Optional) Filesystem type of the volume that you want to mount. Tip: Ensure that the filesystem type is supported by the host operating system. Examples: "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified. More info: http://kubernetes.io/docs/user-guide/volumes#iscsi
- **iscsi_interface** (String, Optional) iSCSI interface name that uses an iSCSI transport. Defaults to 'default' (tcp).
- **lun** (Number, Optional) iSCSI target lun number.
- **read_only** (Boolean, Optional) Whether to force the read-only setting in VolumeMounts. Defaults to false.


<a id="nestedblock--spec--persistent_volume_source--local"></a>
### Nested Schema for `spec.persistent_volume_source.local`

Optional:

- **path** (String, Optional) Path of the directory on the host. More info: http://kubernetes.io/docs/user-guide/volumes#local


<a id="nestedblock--spec--persistent_volume_source--nfs"></a>
### Nested Schema for `spec.persistent_volume_source.nfs`

Required:

- **path** (String, Required) Path that is exported by the NFS server. More info: http://kubernetes.io/docs/user-guide/volumes#nfs
- **server** (String, Required) Server is the hostname or IP address of the NFS server. More info: http://kubernetes.io/docs/user-guide/volumes#nfs

Optional:

- **read_only** (Boolean, Optional) Whether to force the NFS export to be mounted with read-only permissions. Defaults to false. More info: http://kubernetes.io/docs/user-guide/volumes#nfs


<a id="nestedblock--spec--persistent_volume_source--photon_persistent_disk"></a>
### Nested Schema for `spec.persistent_volume_source.photon_persistent_disk`

Required:

- **pd_id** (String, Required) ID that identifies Photon Controller persistent disk

Optional:

- **fs_type** (String, Optional) Filesystem type to mount. Must be a filesystem type supported by the host operating system. Ex. "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified.


<a id="nestedblock--spec--persistent_volume_source--quobyte"></a>
### Nested Schema for `spec.persistent_volume_source.quobyte`

Required:

- **registry** (String, Required) Registry represents a single or multiple Quobyte Registry services specified as a string as host:port pair (multiple entries are separated with commas) which acts as the central registry for volumes
- **volume** (String, Required) Volume is a string that references an already created Quobyte volume by name.

Optional:

- **group** (String, Optional) Group to map volume access to Default is no group
- **read_only** (Boolean, Optional) Whether to force the Quobyte volume to be mounted with read-only permissions. Defaults to false.
- **user** (String, Optional) User to map volume access to Defaults to serivceaccount user


<a id="nestedblock--spec--persistent_volume_source--rbd"></a>
### Nested Schema for `spec.persistent_volume_source.rbd`

Required:

- **ceph_monitors** (Set of String, Required) A collection of Ceph monitors. More info: http://releases.k8s.io/HEAD/examples/volumes/rbd/README.md#how-to-use-it
- **rbd_image** (String, Required) The rados image name. More info: http://releases.k8s.io/HEAD/examples/volumes/rbd/README.md#how-to-use-it

Optional:

- **fs_type** (String, Optional) Filesystem type of the volume that you want to mount. Tip: Ensure that the filesystem type is supported by the host operating system. Examples: "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified. More info: http://kubernetes.io/docs/user-guide/volumes#rbd
- **keyring** (String, Optional) Keyring is the path to key ring for RBDUser. Default is /etc/ceph/keyring. More info: http://releases.k8s.io/HEAD/examples/volumes/rbd/README.md#how-to-use-it
- **rados_user** (String, Optional) The rados user name. Default is admin. More info: http://releases.k8s.io/HEAD/examples/volumes/rbd/README.md#how-to-use-it
- **rbd_pool** (String, Optional) The rados pool name. Default is rbd. More info: http://releases.k8s.io/HEAD/examples/volumes/rbd/README.md#how-to-use-it.
- **read_only** (Boolean, Optional) Whether to force the read-only setting in VolumeMounts. Defaults to false. More info: http://releases.k8s.io/HEAD/examples/volumes/rbd/README.md#how-to-use-it
- **secret_ref** (Block List, Max: 1) Name of the authentication secret for RBDUser. If provided overrides keyring. Default is nil. More info: http://releases.k8s.io/HEAD/examples/volumes/rbd/README.md#how-to-use-it (see [below for nested schema](#nestedblock--spec--persistent_volume_source--rbd--secret_ref))

<a id="nestedblock--spec--persistent_volume_source--rbd--secret_ref"></a>
### Nested Schema for `spec.persistent_volume_source.rbd.secret_ref`

Optional:

- **name** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names
- **namespace** (String, Optional) Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names



<a id="nestedblock--spec--persistent_volume_source--vsphere_volume"></a>
### Nested Schema for `spec.persistent_volume_source.vsphere_volume`

Required:

- **volume_path** (String, Required) Path that identifies vSphere volume vmdk

Optional:

- **fs_type** (String, Optional) Filesystem type to mount. Must be a filesystem type supported by the host operating system. Ex. "ext4", "xfs", "ntfs". Implicitly inferred to be "ext4" if unspecified.



<a id="nestedblock--spec--node_affinity"></a>
### Nested Schema for `spec.node_affinity`

Optional:

- **required** (Block List, Max: 1) (see [below for nested schema](#nestedblock--spec--node_affinity--required))

<a id="nestedblock--spec--node_affinity--required"></a>
### Nested Schema for `spec.node_affinity.required`

Required:

- **node_selector_term** (Block List, Min: 1) (see [below for nested schema](#nestedblock--spec--node_affinity--required--node_selector_term))

<a id="nestedblock--spec--node_affinity--required--node_selector_term"></a>
### Nested Schema for `spec.node_affinity.required.node_selector_term`

Optional:

- **match_expressions** (Block List) A list of node selector requirements by node's labels. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--node_affinity--required--node_selector_term--match_expressions))
- **match_fields** (Block List) A list of node selector requirements by node's fields. The requirements are ANDed. (see [below for nested schema](#nestedblock--spec--node_affinity--required--node_selector_term--match_fields))

<a id="nestedblock--spec--node_affinity--required--node_selector_term--match_expressions"></a>
### Nested Schema for `spec.node_affinity.required.node_selector_term.match_expressions`

Required:

- **key** (String, Required) The label key that the selector applies to.
- **operator** (String, Required) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists`, `DoesNotExist`, `Gt`, and `Lt`.

Optional:

- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.


<a id="nestedblock--spec--node_affinity--required--node_selector_term--match_fields"></a>
### Nested Schema for `spec.node_affinity.required.node_selector_term.match_fields`

Required:

- **key** (String, Required) The label key that the selector applies to.
- **operator** (String, Required) A key's relationship to a set of values. Valid operators ard `In`, `NotIn`, `Exists`, `DoesNotExist`, `Gt`, and `Lt`.

Optional:

- **values** (Set of String, Optional) An array of string values. If the operator is `In` or `NotIn`, the values array must be non-empty. If the operator is `Exists` or `DoesNotExist`, the values array must be empty. This array is replaced during a strategic merge patch.






<a id="nestedblock--timeouts"></a>
### Nested Schema for `timeouts`

Optional:

- **create** (String, Optional)


