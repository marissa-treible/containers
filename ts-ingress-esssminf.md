---

copyright:
  years: 2022, 2023
lastupdated: "2023-05-10"

keywords: containers, ingress, troubleshoot ingress, secrets manager missing, esssminf

subcollection: containers
content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}



# Why does the Ingress status show an `ESSSMINF` error?
{: #ts-ingress-esssminf}
{: troubleshoot}
{: support}

[Virtual Private Cloud]{: tag-vpc} [Classic infrastructure]{: tag-classic-inf}

You can use the the `ibmcloud ks ingress status-report ignored-errors add` command to add an error to the ignored-errors list. Ignored errors still appear in the output of the `ibmcloud ks ingress status-report get` command, but are ignored when calculating the overall Ingress Status.
{: tip}

When you check the status of your cluster's Ingress components by running the `ibmcloud ks ingress status-report get` command, you see an error similar to the following example.
{: tsSymptoms}

```sh
The Secrets Manager instance is not found (ESSSMINF).
```
{: screen}

The Kubernetes Service is unable to access the {{site.data.keyword.secrets-manager_short}} instance. The instance might have been deleted from your IBM Cloud account, but still remains registered to your cluster.
{: tsCauses}

Check that the {{site.data.keyword.secrets-manager_short}} instances registered to your cluster still exist in your IBM Cloud account. 
{: tsResolve}

1. List the {{site.data.keyword.secrets-manager_short}} instances that are registered to your cluster.
    ```sh
    ibmcloud ks ingress instance ls --cluster <cluster>
    ```
    {: pre}

2. List the resources in your account and check that the {{site.data.keyword.secrets-manager_short}} instances registered to your cluster also exist in your account. 
    ```sh
    ibmcloud resource service-instances
    ```
    {: pre}

3. If the {{site.data.keyword.secrets-manager_short}} instance no longer exists in your account, remove it from the cluster.
    ```sh
    ibmcloud ks ingress instance unregister
    ```
    {: pre}

4. If the problem persists, [open a support ticket](/docs/containers?topic=containers-get-help#help-support).



