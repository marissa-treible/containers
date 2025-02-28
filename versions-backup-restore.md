---

copyright: 
  years: 2014, 2023
lastupdated: "2023-03-22"

keywords: back up, restore, changelog, kubernetes

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}





# Back up and restore Helm chart 
{: #backup_restore_changelog}


View information for updates to the back up and restore Helm chart in your {{site.data.keyword.containerlong}} clusters.
{: shortdesc}

Refer to the following tables for a summary of changes for each version of the [back up and restore Helm chart](/docs/containers?topic=containers-utilities#ibmcloud-backup-restore).

| `ibmcloud-backup-restore` Helm chart version | Supported? | Cluster version support |
| -------------------- | -----------|--------------------------- |
| 2.0.5 | Yes | 1.15 - 1.20 |
{: caption="Back up and restore Helm chart versions" caption-side="bottom"}


## Change log for 1.0.5, released 17 December 2020
{: #0105_br_chart}

The following table shows the changes that are in version `1.0.5` of the `ibmcloud-backup-restore` Helm chart.
{: shortdesc}


- Image tags: `v100`  
- Supported cluster versions: 1.10 - 1.20  
- Images are now signed.  
- The `ibmcloud-backup-restore` Helm chart now pulls the universal base image (UBI) from the proxy image registry.  
- Resources that are deployed by the `ibmcloud-backup-restore` Helm chart are now linked with the corresponding source code and build URLs.  







