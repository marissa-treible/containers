---

copyright: 
  years: 2014, 2023
lastupdated: "2023-03-22"

keywords: kubernetes, worker nodes, state

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}





# Worker node states
{: #worker-node-state-reference}


You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

## `Critical` state
{: #worker-node-critical}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A worker node can go into a `Critical` state for many reasons. See [Troubleshooting worker nodes in `Critical` or `NotReady` state](/docs/containers?topic=containers-ts-critical-notready) for more information and troubleshooting steps. 

## `Deleting` state
{: #worker-node-deleting}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Deleting` state means that you requested to delete the worker node, possibly as part of resizing a worker pool or autoscaling the cluster. Other operations can't be issued against the worker node while the worker node deletes. You can't reverse the deletion process. When the deletion process completes, you are no longer billed for the worker nodes.

## `Deleted` state
{: #worker-node-deleted}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Deleted` state means that your worker node is deleted, and no longer is listed in the cluster or billed. This state can't be undone. Any data that was stored only on the worker node, such as container images, are also deleted.



## `Deployed` state
{: #worker-node-deployed}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

Updates are successfully deployed to your worker node. After updates are deployed, {{site.data.keyword.containerlong_notm}} starts a health check on the worker node. After the health check is successful, the worker node goes into a `Normal` state. Worker nodes in a `Deployed` state usually are ready to receive workloads, which you can check by running `kubectl get nodes` and confirming that the state shows `Normal`. 



## `Deploying` state
{: #worker-node-deploying}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Deploying` state means that when you update the Kubernetes version of your worker node, your worker node is redeployed to install the updates. If you reload or reboot your worker node, the worker node is redeployed to automatically install the latest patch version. If your worker node is stuck in this state for a long time, check whether a problem occurred during the deployment. 



## `Deploy_failed` state
{: #worker-node-deploy-failed}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Deploy_failed` state means that your worker node could not be deployed. List the details for the worker node to find the details for the failure by running `ibmcloud ks worker get --cluster <cluster_name_or_id> --worker <worker_node_id>`.


## `Normal` state
{: #worker-node-normal}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Normal` state means that your worker node is fully provisioned and ready to be used in the cluster. This state is considered healthy and does not require an action from the user. 

Although the worker nodes might be normal, other infrastructure resources, such as [networking](/docs/containers?topic=containers-coredns_lameduck) and [storage](/docs/containers?topic=containers-debug_storage_file), might still need attention.
{: note}

## `Provisioned` state
{: #worker-node-provisioned}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Provisioned` state means that your worker node completed provisioning and is part of the cluster. Billing for the worker node begins. The worker node state soon reports a regular health state and status, such as `normal` and `ready`.


## `Provisioning` state
{: #worker-node-provisioning}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Provisioning` state means that your worker node is being provisioned and is not available in the cluster yet. You can monitor the provisioning process in the **Status** column of your CLI output. If your worker node is stuck in this state for a long time, check whether a problem occurred during the provisioning.



## `Provision pending` state
{: #worker-node-provision-pending}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Provision pending` state means that another process is completing before the worker node provisioning process starts. You can monitor the other process that must complete first in the **Status** column of your CLI output. For example, in VPC clusters, the `Pending security group creation` indicates that the security group for your worker nodes is creating first before the worker nodes can be provisioned. If your worker node is stuck in this state for a long time, check whether a problem occurred during the other process.




## `Provision_failed` state
{: #worker-node-provision-failed}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

Your worker node could not be provisioned. List the details for the worker node to find the details for the failure by running `ibmcloud ks worker get --cluster <cluster_name_or_id> --worker <worker_node_id>`.



## `Reloading` state
{: #worker-node-reloading}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Reloading` state means that your worker node is being reloaded and is not available in the cluster. You can monitor the reloading process in the **Status** column of your CLI output. If your worker node is stuck in this state for a long time, check whether a problem occurred during the reloading.


## `Reloading_failed` state
{: #worker-node-reloading-failed}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Reloading_failed` state means that your worker node could not be reloaded. List the details for the worker node to find the details for the failure by running `ibmcloud ks worker get --cluster <cluster_name_or_id> --worker <worker_node_id>`.

## `Reload_pending` state
{: #worker-node-reload-pending}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

You requested to reload or to update the Kubernetes version of your worker node. When reloading begins, the state changes to `Reloading`.

## `Unknown` state
{: #worker-node-unknown}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

An `Unknown` state means that the Kubernetes master is not reachable for one of the following reasons:
- You requested an update of your Kubernetes master. The state of the worker node can't be retrieved during the update. If the worker node remains in this state for an extended period of time even after the Kubernetes master is successfully updated, try to [reload the worker node](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reload).
- You might have another firewall that is protecting your worker nodes, or changed firewall settings recently. {{site.data.keyword.containerlong_notm}} requires certain IP addresses and ports to be opened to allow communication from the worker node to the Kubernetes master and vice versa. For more information, see [Firewall prevents worker nodes from connecting](/docs/containers?topic=containers-firewall#vyatta_firewall).
- The Kubernetes master is down. Contact {{site.data.keyword.cloud_notm}} support by opening an [{{site.data.keyword.cloud_notm}} support case](/docs/containers?topic=containers-get-help).

## `Warning` state
{: #worker-node-warning}

You can view the current worker node state by running the `ibmcloud ks worker ls --cluster <cluster_name_or_ID>` command and locating the **State** and **Status** fields.
{: shortdesc}

A `Warning` state means that your worker node is reaching the limit for memory or disk space. You can either reduce workload on your worker node or add a worker node to your cluster to help load balance the workload.






