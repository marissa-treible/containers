---

copyright: 
  years: 2014, 2023
lastupdated: "2023-03-22"

keywords: block, debug, help

subcollection: containers

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}





# Why do I get a `Volume not attached` error when trying to expand a {{site.data.keyword.block_storage_is_short}} volume?
{: #block_not_attached_vpc}
{: support}

[Virtual Private Cloud]{: tag-vpc} 


When you edit a {{site.data.keyword.block_storage_is_short}} and update the `spec.resources.requests.storage` section to expand your volume, you see the following error:
{: tsSymptoms}

```sh
Volume not attached
```
{: screen}


You tried to expand the volume size of an existing {{site.data.keyword.block_storage_is_short}} PVC that is not mounted by a pod. Only volumes mounted by app pods can be expanded.
{: tsCauses}


Verify that your PVC supports volume expansion, then create an app pod that uses your PVC.
{: tsResolve}

1. Describe your existing PVC. Verify that `allowVolumeExpansion` is set to `true`.
    ```sh
    kubectl describe pvc <pvc-name>
    ```
    {: pre}

1. Create an app pod that uses your PVC and deploy it to your cluster.

1. Edit the PVC and increase the value in the `spec.resources.requests.storage` field.
    ```sh
    kubectl edit pvc <pvc-name>
    ```
    {: pre}

1. Get the details of your PVC and make a note of the PV name.
    ```sh
    kubectl get pvc <pvc-name>
    ```
    {: pre}

1. Describe your PV and make a note of the volume ID
    ```sh
    kubectl describe PV
    ```
    {: pre}

1. Get the details of your {{site.data.keyword.block_storage_is_short}} volume and verify the capacity.
    ```sh
    ibmcloud is vol <volume-ID>
    ```
    {: pre}







