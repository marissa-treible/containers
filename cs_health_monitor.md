---

copyright:
  years: 2014, 2023
lastupdated: "2023-08-14"

keywords: kubernetes, logmet, logs, metrics, recovery, auto-recovery

subcollection: containers

---

{{site.data.keyword.attribute-definition-list}}





# Monitoring cluster health
{: #health-monitor}

Set up monitoring in {{site.data.keyword.containerlong}} to help you troubleshoot issues and improve the health and performance of your Kubernetes clusters and apps.
{: shortdesc}

Continuous monitoring and logging is the key to detecting attacks on your cluster and troubleshooting issues as they arise. By continuously monitoring your cluster, you're able to better understand your cluster capacity and the availability of resources that are available to your app. With this insight, you can prepare to protect your apps against downtime.

## Choosing a monitoring solution
{: #view_metrics}

Metrics help you monitor the health and performance of your clusters. You can use the standard Kubernetes and container runtime features to monitor the health of your clusters and apps.
{: shortdesc}

Every Kubernetes master is continuously monitored by IBM. {{site.data.keyword.containerlong_notm}} automatically scans every node where the Kubernetes master is deployed for vulnerabilities that are found in Kubernetes and OS-specific security fixes. If vulnerabilities are found, {{site.data.keyword.containerlong_notm}} automatically applies fixes and resolves vulnerabilities on behalf of the user to ensure master node protection. You are responsible for monitoring and analyzing the logs for the rest of your cluster components.

To avoid conflicts when using metrics services, be sure that clusters across resource groups and regions have unique names.
{: tip}

{{site.data.keyword.mon_full}}
:   Gain operational visibility into the performance and health of your apps and your cluster by deploying a {{site.data.keyword.mon_short}} agent to your worker nodes. The agent collects pod and cluster metrics, and sends these metrics to {{site.data.keyword.mon_full_notm}}. For more information about {{site.data.keyword.mon_full_notm}}, see the [service documentation](/docs/monitoring?topic=monitoring-getting-started). To set up the {{site.data.keyword.mon_short}} agent in your cluster, see [Viewing cluster and app metrics with {{site.data.keyword.mon_full_notm}}](#monitoring).

Kubernetes dashboard
:   The Kubernetes dashboard is an administrative web interface where you can review the health of your worker nodes, find Kubernetes resources, deploy containerized apps, and troubleshoot apps with logging and monitoring information. For more information about how to access your Kubernetes dashboard, see [Launching the Kubernetes dashboard for {{site.data.keyword.containerlong_notm}}](/docs/containers?topic=containers-deploy_app#cli_dashboard).


## Forwarding cluster and app metrics to {{site.data.keyword.mon_full_notm}}
{: #monitoring}

Use the {{site.data.keyword.containerlong_notm}} observability plug-in to create a monitoring configuration for {{site.data.keyword.mon_full_notm}} in your cluster, and use this monitoring configuration to automatically collect and forward metrics to {{site.data.keyword.mon_full_notm}}.
{: shortdesc}

With {{site.data.keyword.mon_full_notm}}, you can collect cluster and pod metrics, such as the CPU and memory usage of your worker nodes, incoming and outgoing HTTP traffic for your pods, and data about several infrastructure components. In addition, the agent can collect custom application metrics by using either a Prometheus-compatible scraper or a statsd facade.

Considerations for using the {{site.data.keyword.containerlong_notm}} observability plug-in:
- You can have only one monitoring configuration for {{site.data.keyword.mon_full_notm}} in your cluster at a time. If you want to use a different {{site.data.keyword.mon_full_notm}} service instance to send metrics to, use the [`ibmcloud ob monitoring config replace`](/docs/containers?topic=containers-observability_cli#monitoring_config_replace) command.
- If you created a {{site.data.keyword.mon_short}} configuration in your cluster without using the {{site.data.keyword.containerlong_notm}} observability plug-in, you can use the [`ibmcloud ob monitoring agent discover`](/docs/containers?topic=containers-observability_cli#monitoring_agent_discover) command to make the configuration visible to the plug-in. Then, you can use the observability plug-in commands and functionality in the {{site.data.keyword.cloud_notm}} console to manage the configuration.

Before you begin:
- Verify that you are assigned the **Editor** platform access role and **Manager** server access role for {{site.data.keyword.mon_full_notm}}.
- Verify that you are assigned the **Administrator** platform access role and the **Manager** service access role for all Kubernetes namespaces in {{site.data.keyword.containerlong_notm}} to create the monitoring configuration. To view a monitoring configuration or launch the {{site.data.keyword.mon_short}} dashboard after the monitoring configuration is created, users must be assigned the **Viewer** platform access role and **Reader** service access role for the `ibm-observe` Kubernetes namespace in {{site.data.keyword.containerlong_notm}}.
- If you want to use the CLI to set up the monitoring configuration:
    - [Install the {{site.data.keyword.containerlong_notm}} observability CLI plug-in (`ibmcloud ob`)](/docs/containers?topic=containers-cli-install).
    - [Log in to your account. If applicable, target the appropriate resource group. Set the context for your cluster.](/docs/containers?topic=containers-access_cluster)

To set up a monitoring configuration for your cluster:

1. Create an [{{site.data.keyword.mon_full_notm}} service instance](/docs/monitoring?topic=monitoring-provision) and note the name of the instance. The service instance must belong to the same {{site.data.keyword.cloud_notm}} account where you created your cluster, but can be in a different resource group and {{site.data.keyword.cloud_notm}} region than your cluster.
2. Set up a monitoring configuration for your cluster. When you create the monitoring configuration, a Kubernetes namespace `ibm-observe` is created and a {{site.data.keyword.mon_short}} agent is deployed as a Kubernetes daemon set to all worker nodes in your cluster. This agent collects cluster and pod metrics, such as the worker node CPU and memory usage, or the amount incoming and outgoing network traffic to your pods.

    In the console.
    
    1. From the [Kubernetes clusters console](https://cloud.ibm.com/kubernetes/clusters){: external}, select the cluster for which you want to create a {{site.data.keyword.mon_short}} configuration.
    2. On the cluster **Overview** page, click **Connect**.
    3. Select the region and the {{site.data.keyword.mon_full_notm}} service instance that you created earlier, and click **Connect**.

    In the CLI.
    
    1. Create the {{site.data.keyword.mon_short}} configuration. When you create the {{site.data.keyword.mon_short}} configuration, the access key that was last added is retrieved automatically. If you want to use a different access key, add the `--sysdig-access-key <access_key>` option to the command.

        To use a different service access key after you created the monitoring configuration, use the [`ibmcloud ob monitoring config replace`](/docs/containers?topic=containers-observability_cli#monitoring_config_replace) command.
        {: tip}

        ```sh
        ibmcloud ob monitoring config create --cluster <cluster_name_or_ID> --instance <Monitoring_instance_name_or_ID>
        ```
        {: pre}

        Example output
        ```sh
        Creating configuration...
        OK
        ```
        {: screen}

    2. Verify that the monitoring configuration was added to your cluster.
        ```sh
        ibmcloud ob monitoring config list --cluster <cluster_name_or_ID>
        ```
        {: pre}

        Example output
        ```sh
        Listing configurations...

        OK
        Instance Name                Instance ID                            CRN   
        IBM Cloud Monitoring-aaa     1a111a1a-1111-11a1-a1aa-aaa11111a11a   crn:v1:prod:public:sysdig:us-south:a/a11111a1aaaaa11a111aa11a1aa1111a:1a111a1a-1111-11a1-a1aa-aaa11111a11a::  
        ```
        {: screen}

3. Optional: Verify that the {{site.data.keyword.mon_short}} agent was set up successfully.
    1. If you used the console to create the {{site.data.keyword.mon_short}} configuration, log in to your cluster. For more information, see [Log in to your account. If applicable, target the appropriate resource group. Set the context for your cluster.](/docs/containers?topic=containers-access_cluster)
    2. Verify that the daemon set for the {{site.data.keyword.mon_short}} agent was created and all instances are listed as `AVAILABLE`.
        ```sh
        kubectl get daemonsets -n ibm-observe
        ```
        {: pre}

        Example output
        ```sh
        NAME           DESIRED   CURRENT   READY   UP-TO-DATE   AVAILABLE   NODE SELECTOR   AGE
        sysdig-agent   9         9         9       9            9           <none>          14m
        ```
        {: screen}

        The number of daemon set instances that are deployed equals the number of worker nodes in your cluster.

    3. Review the ConfigMap that was created for your {{site.data.keyword.mon_short}} agent.
        ```sh
        kubectl describe configmap -n ibm-observe
        ```
        {: pre}

4. Access the metrics for your pods and cluster from the {{site.data.keyword.mon_short}} dashboard.
    1. From the [Kubernetes clusters console](https://cloud.ibm.com/kubernetes/clusters){: external}, select the cluster that you configured.
    2. On the cluster **Overview** page, click **Launch**. The {{site.data.keyword.mon_short}} dashboard opens.
    3. Review the pod and cluster metrics that the {{site.data.keyword.mon_short}} agent collected from your cluster. It might take a few minutes for your first metrics to show.

5. Review how you can work with the [{{site.data.keyword.mon_short}} dashboard](/docs/monitoring?topic=monitoring-panels) to further analyze your metrics.

## Viewing cluster states
{: #states}

Review the state of a Kubernetes cluster to get information about the availability and capacity of the cluster, and potential problems that might occur.
{: shortdesc}

To view information about a specific cluster, such as its zones, service endpoint URLs, Ingress subdomain, version, and owner, use the `ibmcloud ks cluster get --cluster <cluster_name_or_ID>` [command](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_get). Include the `--show-resources` option to view more cluster resources such as add-ons for storage pods or subnet VLANs for public and private IPs.

You can review information about the overall cluster, the IBM-managed master, and your worker nodes. To troubleshoot your cluster and worker nodes, see [Troubleshooting clusters](/docs/containers?topic=containers-debug_clusters).

- [Cluster states](/docs/openshift?topic=openshift-health-monitor#states).
- [Worker node states](/docs/openshift?topic=openshift-worker-node-state-reference).

### Master states
{: #states_master}

Your {{site.data.keyword.containerlong_notm}} cluster includes an IBM-managed master with highly available replicas, automatic security patch updates applied for you, and automation in place to recover in case of an incident. You can check the health, status, and state of the cluster master by running `ibmcloud ks cluster get --cluster <cluster_name_or_ID>`.
{: shortdesc}

The **Master Health** reflects the state of master components and notifies you if something needs your attention. The health might be one of the following states.
- `error`: The master is not operational. IBM is automatically notified and takes action to resolve this issue. You can continue monitoring the health until the master is `normal`. You can also [open an {{site.data.keyword.cloud_notm}} support case](/docs/containers?topic=containers-get-help).
- `normal`: The master is operational and healthy. No action is required.
- `unavailable`: The master might not be accessible, which means some actions such as resizing a worker pool are temporarily unavailable. IBM is automatically notified and takes action to resolve this issue. You can continue monitoring the health until the master is `normal`.
- `unsupported`: The master runs an unsupported version of Kubernetes. You must [update your cluster](/docs/containers?topic=containers-update) to return the master to `normal` health.

The **Master Status** provides details of what operation from the master state is in progress. The status includes a timestamp of how long the master has been in the same state, such as `Ready (1 month ago)`. The **Master State** reflects the lifecycle of possible operations that can be performed on the master, such as deploying, updating, and deleting. Each state is described in the following table.

|Master state|Description|
|--- |--- |
|`deployed`|The master is successfully deployed. Check the status to verify that the master is `Ready` or to see if an update is available.|
|`deploying`|The master is currently deploying. Wait for the state to become `deployed` before working with your cluster, such as adding worker nodes.|
|`deploy_failed`|The master failed to deploy. IBM Support is notified and works to resolve the issue. Check the **Master Status** field for more information, or wait for the state to become `deployed`.|
|`deleting`|The master is currently deleting because you deleted the cluster. You can't undo a deletion. After the cluster is deleted, you can no longer check the master state because the cluster is completely removed.|
|`delete_failed`|The master failed to delete. IBM Support is notified and works to resolve the issue. You can't resolve the issue by trying to delete the cluster again. Instead, check the **Master Status** field for more information, or wait for the cluster to delete. You can also [open an {{site.data.keyword.cloud_notm}} support case](/docs/containers?topic=containers-get-help).|
|`scaled_down`| The master resources have been scaled down to zero replicas. This is a temporary state that occurs while etcd is being restored after a backup. You cannot interact with your cluster while it is in this state. Wait for the etcd restoration to complete and the master state to return to `deployed`.|
|`updating`|The master is updating its Kubernetes version. The update might be a patch update that is automatically applied, or a minor or major version that you applied by updating the cluster. During the update, your highly available master can continue processing requests, and your app workloads and worker nodes continue to run. After the master update is complete, you can [update your worker nodes](/docs/containers?topic=containers-update#worker_node). If the update is unsuccessful, the master returns to a `deployed` state and continues running the previous version. IBM Support is notified and works to resolve the issue. You can check if the update failed in the **Master Status** field.|
|`update_cancelled`|The master update is canceled because the cluster was not in a healthy state at the time of the update. Your master remains in this state until your cluster is healthy and you manually update the master. To update the master, use the `ibmcloud ks cluster master update` [command](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update). If you don't want to update the master to the default `major.minor` version during the update, include the `--version` option and specify the latest patch version that is available for the `major.minor` version that you want, such as `1.26`. To list available versions, run `ibmcloud ks versions`.|
|`update_failed`|The master update failed. IBM Support is notified and works to resolve the issue. You can continue to monitor the health of the master until the master reaches a normal state. If the master remains in this state for more than 1 day, [open an {{site.data.keyword.cloud_notm}} support case](/docs/containers?topic=containers-get-help). IBM Support might identify other issues in your cluster that you must fix before the master can be updated.|
{: caption="Master states"}



## Setting up {{site.data.keyword.mon_full}} alerts
{: #monitoring-alerts}

When you set up alerts, make sure to allow your cluster enough time to self-heal. Because Kubernetes has self healing capabilities, configure your alerts only for the issues that arise over time. By observing your cluster over time, you can learn which issues Kubernetes can resolve itself and which issues require alerts to avoid downtime.
{: shortdesc}

On 15 June 2022, the naming convention for {{site.data.keyword.mon_full}} alerts is change to a Prometheus compatible format. For more information, see the [Sysdig release notes](https://docs.sysdig.com/en/docs/release-notes/enhanced-metric-store/#new-features-and-enhancements){: external}, [Mapping Legacy Sysdig Kubernetes Metrics with Prometheus Metrics](https://docs.sysdig.com/en/docs/sysdig-monitor/using-monitor/metrics/metrics-library/metrics-and-labels-mapping/mapping-legacy-sysdig-kubernetes-metrics-with-prometheus-metrics/){: external}, and [Mapping Classic Metrics with PromQL](https://docs.sysdig.com/en/docs/sysdig-monitor/using-monitor/metrics/metrics-library/metrics-and-labels-mapping/mapping-classic-metrics-with-promql-metrics/){: external}.
{: important}

Depending on the size of your cluster, consider setting up alerts on the following levels:

- [Apps](#app-level-alerts)
- [Worker nodes](#worker-node-level-alerts)
- [Cluster](#cluster-level-alerts)
- [Zone](#zone-level-alerts)
- [Account](#account-level-alerts)
- [{{site.data.keyword.block_storage_is_short}}](#vpc-block-storage-alerts)



Set up [autorecovery](#autorecovery) on your worker nodes to enable your cluster to automatically resolve issues.
{: tip}



### App alerts
{: #app-level-alerts}

Review the following app level metrics and alert thresholds for help setting up app monitoring in your cluster.
{: shortdesc}

Common app level conditions to monitor include things such as,
- Multiple app pods or containers are restarted within 10 minutes.
- More than one replica of an app is not running.
- More than ten 5XX `HTTP` response codes received within 10 minutes.
- More than one pod in a namespace is in an unknown state.
- More than five pods can't be scheduled on a worker node (pending state).

The underlying issues for these symptoms include things such as,
- One or more worker node is in an unhealthy state.
- Worker nodes ran out of CPU, memory, or disk space.
- Maximum pod limit per cluster reached.
- App itself has an issue.

To set up monitoring for these conditions, configure alerts based on the following {{site.data.keyword.mon_full_notm}} metrics. Note that your alert thresholds might change depending on your cluster configuration.

| Metric | {{site.data.keyword.mon_full_notm}} metric | Alert threshold |
| --- | --- | --- |
| Multiple restarts of a pod in a short amount of time. | `kubernetes_pod_restart_count` | Greater than 4 for the last 10 minutes |
| No running replicas in a ReplicaSet. | `kube_replicaset_status_replicas` in `kubernetes_deployment_name` | Less than one. |
| More than 5 pods pending in cluster. | `kube_pod_container_status_waiting` | Status equals `pending` greater than five.|
| No replicas in a deployment available. | `kubernetes_deployment_replicas_available` | Less than one. |
| Number of pods per node reaching threshold of 110. | Count by `(kube_cluster_name,kube_node_name)(kube_pod_container_info)` | Greater than or equal to 100. Note that this query is a `promQL` query. |
| Workloads that are in an unknown state. | `(kube_workload_status_unavailable)` | Greater than or equal to one. Note that this query is a `promQL` query. |
{: caption="App level metrics"}


### Worker node alerts
{: #worker-node-level-alerts}

Review the following thresholds and alerts for worker nodes.
{: shortdesc}

|Metric| {{site.data.keyword.mon_full_notm}} metric | Alert threshold |
| --- | --- | --- |
| CPU utilization of the worker node over threshold. | `cpu_used_percent` | Greater than 80% for 1 hour. |
| CPU utilization of the worker node over threshold. | `cpu_used_percent` | Greater than 65% for 24 hours. |
| Memory utilization of the worker node over threshold. | `memory_used_percent` | Greater than 80 % for 1 hour. |
| Memory utilization of the worker node over threshold. | `memory_used_percent` | Greater than 65% for 24 hours. |
| Amount of memory used over threshold. | `memory_bytes_used` | Greater than `NUMBER_OF_BYBTES`. |
| Nodes with disk pressure exist. | `kube_node_status_condition` | Greater than or equal to 1 for 10 minutes. |
| Kubernetes nodes not ready exist. | `kube_node_status_ready >= 1` |
{: caption="Worker node metrics"}

#### Resolving worker node alerts
{: #worker-node-resolve}

Reloading or rebooting the worker can resolve the issue. However, you might need add more workers to increase capacity.
{: shortdesc}

1. Get your worker nodes and review the [state](/docs/containers?topic=containers-worker-node-state-reference). 
    ```sh
    kubectl get nodes
    ```
    {: pre}

2. If all the worker nodes are **not** in the `Ready` state, add worker nodes to your cluster.
    - [Adding worker nodes to Classic clusters](/docs/containers?topic=containers-add-workers-classic).
    - [Adding worker nodes to VPC clusters](/docs/containers?topic=containers-add-workers-vpc).

3. If all the worker nodes are in the `Ready` state, [reload](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reload) or [reboot](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reboot) your worker nodes.
    1. Describe your worker node and review the **Events** section for common error messages.
        ```sh
        kubectl describe node <node>
        ```
        {: pre}
      
    1. Cordon the node that isn't `Ready` so that you can start investigating.

    1. Drain the worker node. Review the [Kubernetes documentation to safely drain pods from your worker node](https://kubernetes.io/docs/tasks/administer-cluster/safely-drain-node/){: external}.
        ```sh
        kubectl drain <node>
        ```
        {: pre}

    1. [Reload](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reload) or [reboot](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reboot) your worker node.


### Zone alerts
{: #zone-level-alerts}

To set up zone level alerts, edit the `sysdig-agent` ConfigMap to include the required label filters.
{: shortdesc}

1. Edit the ConfigMap by running the following command.
    ```sh
    kubectl edit configmap sysdig-agent -n ibm-observe
    ```
    {: pre}
    
1. Add the following YAML block after `k8s_cluster_name: <cluster_name>`. Replace `<cluster_name>` with the name of the cluster that you want to you want to monitor.
    ```yaml
    k8s_labels_filter:
      - include: "kubernetes.node.label.kubernetes.io/hostname"
      - include: "kubernetes.node.label.kubernetes.io/role"
      - include: "kubernetes.node.label.ibm-cloud.kubernetes.io/zone"
      - exclude: "*.kubernetes.io/*"
      - exclude: "*.pod-template-hash"
      - exclude: "*.pod-template-generation"
      - exclude: "*.controller-revision-hash"
      - include: "*"
     ```
     {: codeblock}

1. Restart the {{site.data.keyword.mon_full_notm}} pods. Delete all the pods and wait for them to restart. Get the list of pods.
    ```sh
    kubectl get pods -n ibm-observe
    ```
    {: pre}
    
1. Delete the pods to restart them.
    ```sh
    kubectl delete pods sysdig-agent-1111 sysdig-agent-2222 sysdig-agent-3333 -n ibm-observe
    ```
    {: pre}
    
1. Wait 5 minutes for the pods restart. After the pods have restarted, the label that you added earlier is available in {{site.data.keyword.mon_full_notm}}  
1. Verify that the labels now show by opening the **{{site.data.keyword.mon_full_notm}} dashboard** > **Explore** > **PromQL query**.
1. Enter `kube_node_labels` in the query field and click `Run Query`. 
    
    
| Metric | PromQL query |
| --- | --- |
| CPU usage per zone over threshold | `sum(sysdig_container_cpu_used_percent{agent_tag_cluster="<cluster_name>"}) by (kube_node_label_ibm_cloud_kubernetes_io_zone) / sum (kube_node_info) by (kube_node_label_ibm_cloud_kubernetes_io_zone) > 80` |
| Memory usage per zone over threshold |`sum(sysdig_container_cpu_used_percent{agent_tag_cluster="<cluster_name>"}) by (kube_node_label_ibm_cloud_kubernetes_io_zone)/ sum (kube_node_info) by (kube_node_label_ibm_cloud_kubernetes_io_zone) > 80` |
{: caption="Zone level alerts"}


### Cluster alerts
{: #cluster-level-alerts}

Review the following example thresholds for creating alerts at the cluster level.
{: shortdesc}

- All worker nodes in a region are reaching capacity threshold of 80%.
- More than 50% of all worker nodes are in an unhealthy state.
- Reaching maximum number of file and block storage volumes per account (250).
- Reaching maximum number of worker nodes per cluster (500).

### Account alerts
{: #account-level-alerts}

You might set up an alert for when the maximum number of clusters per account is reaching the limit. For example, 100 per region/infrastructure provider.
{: shortdesc}

    
### {{site.data.keyword.block_storage_is_short}} alerts
{: #vpc-block-storage-alerts}

The following metrics are available for {{site.data.keyword.block_storage_is_short}} alerts:
- `kubelet_volume_stats_available_bytes`
- `kubelet_volume_stats_capacity_bytes`
- `kubelet_volume_stats_inodes`
- `kubelet_volume_stats_inodes_free`
- `kubelet_volume_stats_inodes_used`

1. Create a monitoring instance for {{site.data.keyword.block_storage_is_short}} alerts. See instructions in [Forwarding cluster and app metrics to IBM Cloud Monitoring](/docs/containers?topic=containers-health-monitor#monitoring).

2. Install the `syslog` agent.
    1. [In the {{site.data.keyword.cloud_notm}} console](https://cloud.ibm.com){: external}, select **Observability** from the menu.
    2. Select **Monitoring**.
    3. In the row of the instance for {{site.data.keyword.block_storage_is_short}} alerts, select **Open dashboard**.
    4. From the menu, select **Get started**.
    5. Under the **Install the Agent** section, select **Add Sources**.
    6. Follow the instructions to install the agent.
    7. Make sure the agent is running by using the `kubectl get pods -n CLUSTER_NAME | grep syslog` command.

3. Configure the notification channels.
    1. In the {{site.data.keyword.cloud_notm}} Monitoring dashboard, select **Monitoring Operations > Settings**.
    2. Select **Notification Channels** > **Add Notification Channel** and pick one of the available notification methods.
    3. Complete the settings for the new channel and click **Save**.
    4. Optional: Repeat the previous steps to add more channels.

4. Create an alert.
    1. In the {{site.data.keyword.cloud_notm}} Monitoring dashboard, select **Alerts** > **Library**.
    2. Choose one of the templates and select **Enable Alert**. For example, you can search for `PVC storage` and enable the `PVC Storage Usage Is Reaching The Limit` alert.
    3. Customize the alert settings on the template and select **Enable Alert** to apply your settings.

If your {{site.data.keyword.block_storage_is_short}} volumes are reaching capacity, you can [set up volume expansion](/docs/containers?topic=containers-vpc-block#vpc-block-volume-expand).
{: tip}




## Monitoring worker node health in with Autorecovery
{: #autorecovery}

The Autorecovery system uses various checks to query worker node health status. If Autorecovery detects an unhealthy worker node based on the configured checks, Autorecovery triggers a corrective action like rebooting a VPC worker node or reloading the operating system in a classic worker node. Only one worker node undergoes a corrective action at a time. The worker node must complete the corrective action before any other worker node undergoes a corrective action. For more information, see this [Autorecovery blog post](https://www.ibm.com/cloud/blog/autorecovery-utilizes-consistent-hashing-high-availability){: external}.
{: shortdesc}

Autorecovery requires at least one healthy worker node to function properly. Configure Autorecovery with active checks only in clusters with two or more worker nodes.
{: note}

Before you begin:
- Ensure that you have the following [{{site.data.keyword.cloud_notm}} IAM roles](/docs/containers?topic=containers-users#checking-perms):
    - **Administrator** platform access role for the cluster
    - **Writer** or **Manager** service access role for the `kube-system` namespace
- [Log in to your account. If applicable, target the appropriate resource group. Set the context for your cluster.](/docs/containers?topic=containers-access_cluster)

To configure Autorecovery:

1. [Follow the instructions](/docs/containers?topic=containers-helm#install_v3) to install the Helm version 3 client on your local machine.

2. Create a configuration map file that defines your checks in JSON format. For example, the following YAML file defines three checks: an HTTP check and two Kubernetes API server checks. Refer to the [component descriptions](#configmap-components) and the [health check component table](#health-check-components) for information about the three kinds of checks and information about the individual components of the checks.

    Define each check as a unique key in the `data` section of the configuration map.
    {: tip}

    ```yaml
    kind: ConfigMap
    apiVersion: v1
    metadata:
      name: ibm-worker-recovery-checks
      namespace: kube-system # The `kube-system` namespace is a constant and can't be changed.
    data:
      checknode.json: |
        {
          "Check":"KUBEAPI",
          "Resource":"NODE",
          "FailureThreshold":3,
          "CorrectiveAction":"RELOAD",
          "CooloffSeconds":1800,
          "IntervalSeconds":180,
          "TimeoutSeconds":10,
          "Enabled":true
        }
      checkpod.json: |
        {
          "Check":"KUBEAPI",
          "Resource":"POD",
          "PodFailureThresholdPercent":50,
          "FailureThreshold":3,
          "CorrectiveAction":"RELOAD",
          "CooloffSeconds":1800,
          "IntervalSeconds":180,
          "TimeoutSeconds":10,
          "Enabled":true
        }
      checkhttp.json: |
        {
          "Check":"HTTP",
          "FailureThreshold":3,
          "CorrectiveAction":"REBOOT",
          "CooloffSeconds":1800,
          "IntervalSeconds":180,
          "TimeoutSeconds":10,
          "Port":80,
          "ExpectedStatus":200,
          "Route":"/myhealth",
          "Enabled":false
        }
    ```
    {: codeblock}

3. Create the configuration map in your cluster.
    ```sh
    kubectl apply -f ibm-worker-recovery-checks.yaml
    ```
    {: pre}

4. Verify that you created the configuration map with the name `ibm-worker-recovery-checks` in the `kube-system` namespace with the proper checks.
    ```sh
    kubectl -n kube-system get cm ibm-worker-recovery-checks -o yaml
    ```
    {: pre}

5. Deploy Autorecovery into your cluster by installing the `ibm-worker-recovery` Helm chart.
    ```sh
    helm install ibm-worker-recovery iks-charts/ibm-worker-recovery --namespace kube-system
    ```
    {: pre}

6. After a few minutes, you can check the `Events` section in the output of the following command to see activity on the Autorecovery deployment.
    ```sh
    kubectl -n kube-system describe deployment ibm-worker-recovery
    ```
    {: pre}

7. If you don't see activity on the Autorecovery deployment, you can check the Helm deployment by running the tests that are in the Autorecovery chart definition.
    ```sh
    helm test ibm-worker-recovery -n kube-system
    ```
    {: pre}


### Understanding the configmap components
{: #configmap-components}

Review the following information on the individual components of health checks.
{: shortdesc}

- `name`: The configuration name `ibm-worker-recovery-checks` is a constant and can't be changed.
- `namespace`: The `kube-system` namespace is a constant and can't be changed.
- `checknode.json`: Defines a Kubernetes API node check that checks whether each worker node is in the `Ready` state. The check for a specific worker node counts as a failure if the worker node is not in the `Ready` state. The check in the example YAML runs every 3 minutes. If it fails three consecutive times, the worker node is reloaded. This action is equivalent to running `ibmcloud ks worker reload`. The node check is enabled until you set the **Enabled** field to `false` or remove the check. Note that reloading is supported only for worker nodes on classic infrastructure.
- `checkpod.json`: Defines a Kubernetes API pod check that checks the total percentage of `NotReady` pods on a worker node based on the total pods that are assigned to that worker node. The check for a specific worker node counts as a failure if the total percentage of `NotReady` pods is greater than the defined `PodFailureThresholdPercent`. The check in the example YAML runs every 3 minutes. If it fails three consecutive times, the worker node is reloaded. This action is equivalent to running `ibmcloud ks worker reload`. For example, the default `PodFailureThresholdPercent` is 50%. If the percentage of `NotReady` pods is greater than 50% three consecutive times, the worker node is reloaded. The check runs on all namespaces by default. To restrict the check to only pods in a specified namespace, add the `Namespace` field to the check. The pod check is enabled until you set the **Enabled** field to `false` or remove the check. Note that reloading is supported only for worker nodes on classic infrastructure.
- `checkhttp.json`: Defines an HTTP check that checks if an HTTP server that runs on your worker node is healthy. To use this check, you must deploy an HTTP server on every worker node in your cluster by using a [daemon set](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/){: external}. You must implement a health check that is available at the `/myhealth` path and that can verify whether your HTTP server is healthy. You can define other paths by changing the `Route` parameter. If the HTTP server is healthy, you must return the HTTP response code that is defined in `ExpectedStatus`. The HTTP server must be configured to listen on the private IP address of the worker node. You can find the private IP address by running `kubectl get nodes`. For example, consider two nodes in a cluster that have the private IP addresses 10.10.10.1 and 10.10.10.2. In this example, two routes are checked for a 200 HTTP response: `http://10.10.10.1:80/myhealth` and `http://10.10.10.2:80/myhealth`. The check in the example YAML runs every 3 minutes. If it fails three consecutive times, the worker node is rebooted. This action is equivalent to running `ibmcloud ks worker reboot`. The HTTP check is disabled until you set the **Enabled** field to `true`.


### Understanding the individual components of health checks
{: #health-check-components}

Review the following table for information on the individual components of health checks.
{: shortdesc}


| Component | Description |
| --- | --- |
| `Check` | Enter the type of check that you want Autorecovery to use.  \n `HTTP`: Autorecovery calls HTTP servers that run on each node to determine whether the nodes are running properly.  \n `KUBEAPI`: Autorecovery calls the Kubernetes API server and reads the health status data reported by the worker nodes. |
| `Resource` | When the check type is `KUBEAPI`, enter the type of resource that you want Autorecovery to check. Accepted values are `NODE` or `POD`. |
| `FailureThreshold` | Enter the threshold for the number of consecutive failed checks. When this threshold is met, Autorecovery triggers the specified corrective action. For example, if the value is 3 and Autorecovery fails a configured check three consecutive times, Autorecovery triggers the corrective action that is associated with the check. |
|`PodFailureThresholdPercent`| When the resource type is `POD`, enter the threshold for the percentage of pods on a worker node that can be in a [NotReady](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-readiness-probes){: external} state. This percentage is based on the total number of pods that are scheduled to a worker node. When a check determines that the percentage of unhealthy pods is greater than the threshold, the check counts as one failure.|
|`CorrectiveAction`| Enter the action to run when the failure threshold is met. A corrective action runs only while no other workers are being repaired and when this worker node is not in a cool-off period from a previous action.  \n `REBOOT`: Reboots the worker node.  \n `RELOAD`: Reloads all the necessary configurations for the worker node from a clean OS.|
|`CooloffSeconds`| Enter the number of seconds Autorecovery must wait to issue another corrective action for a node that was already issued a corrective action. The cool off period starts at the time a corrective action is issued.|
|`IntervalSeconds`| Enter the number of seconds between consecutive checks. For example, if the value is 180, Autorecovery runs the check on each node every 3 minutes.|
|`TimeoutSeconds`| Enter the maximum number of seconds that a check call to the database takes before Autorecovery terminates the call operation. The value for `TimeoutSeconds` must be less than the value for `IntervalSeconds`.|
|`Port`| When the check type is `HTTP`, enter the port that the HTTP server must bind to on the worker nodes. This port must be exposed on the IP of every worker node in the cluster. Autorecovery requires a constant port number across all nodes for checking servers. Use [daemon sets](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/){: external} when you deploy a custom server into a cluster.|
|`ExpectedStatus`| When the check type is `HTTP`, enter the HTTP server status that you expect to be returned from the check. For example, a value of 200 indicates that you expect an `OK` response from the server.|
| `Route`| When the check type is `HTTP`, enter the path that is requested from the HTTP server. This value is typically the metrics path for the server that runs on all the worker nodes.|
| `Enabled`| Enter `true` to enable the check or `false` to disable the check.|
|`Namespace`| Optional: To restrict `checkpod.json` to checking only pods in one namespace, add the `Namespace` field and enter the namespace.|
{: caption="Health check components"}



