---

copyright: 
  years: 2014, 2023
lastupdated: "2023-03-22"

keywords: kubernetes, help, network, connectivity

subcollection: containers

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}





# Why does the Block storage plug-in Helm chart give CPU throttling warnings?
{: #block_helm_cpu}

[Classic infrastructure]{: tag-classic-inf}



When you install the Block storage Helm chart, the installation gives a warning similar to the following:
{: tsSymptoms}

```sh
Message: 50% throttling of CPU in namespace kube-system for container ibmcloud-block-storage-driver-container in pod ibmcloud-block-storage-driver-1abab.
```
{: screen}


The default Block storage plug-in resource requests are not sufficient. The Block storage plug-in and driver are installed with the following default resource request and limit values.
{: tsCauses}

```yaml
plugin:
  resources:
    requests:
      memory: 100Mi
      cpu: 50m
    limits:
      memory: 300Mi
      cpu: 300m
driver:
  resources:
    requests:
      memory: 50Mi
      cpu: 25m
    limits:
      memory: 200Mi
      cpu: 100m
```
{: codeblock}


Remove and reinstall the Helm chart with increased resource requests and limits.
{: tsResolve}

1. Remove the Helm chart.
    ```sh
    helm uninstall <release_name> iks-charts/ibmcloud-block-storage-plugin -n <namespace>
    ```
    {: pre}

2. Reinstall the Helm chart and increase the resource requests and limits by using the `--set` option when running `helm install`. The following example command sets the `plugin.resources.requests.memory` value to `200Mi` and the `plugin.resources.requests.cpu` value to `100m`. You can pass multiple values by using the `--set` option for each value that you want to pass.

    ```sh
    helm install <release_name> iks-charts/ibmcloud-block-storage-plugin -n <namespace> --set plugin.resources.requests.memory=200Mi --set plugin.resources.requests.cpu=100m
    ```
    {: pre}






