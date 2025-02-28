---

copyright: 
  years: 2014, 2023
lastupdated: "2023-03-22"

keywords: kubernetes, help, network, connectivity

subcollection: containers

content-type: troubleshoot

---


{{site.data.keyword.attribute-definition-list}}





# Why can't the ownership of the mount path be changed?
{: #cos_mountpath_error}
{: support}

[Virtual Private Cloud]{: tag-vpc} [Classic infrastructure]{: tag-classic-inf}




You created a deployment that mounts an {{site.data.keyword.cos_full_notm}} bucket to your app. During the deployment, you try to change the ownership of the volume mount path, but this action fails. You see error messages similar to the following:
{: tsSymptoms}

```sh
chown: changing ownership of '<volume_mount_path>': Input/output error
chown: changing ownership of '<volume_mount_path>': Operation not permitted
```
{: screen}


When you create a bucket in {{site.data.keyword.cos_full_notm}}, the bucket is managed by `s3fs-fuse`. The UID and GID that own the volume mount path are automatically set by Fuse when you mount the bucket to your app and can't be changed.
{: tsCauses}


You can't change the ownership of the volume mount path. However, you can change the UID and GID for a file or a directory that is stored under your volume mount path. For more information, see [Object storage: Accessing files with a non-root user fails](/docs/containers?topic=containers-cos_nonroot_access).
{: tsResolve}





