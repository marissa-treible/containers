---

copyright: 
  years: 2014, 2023
lastupdated: "2023-03-22"

keywords: kubernetes, infrastructure, rbac, policy

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}





# Understanding user access permissions
{: #access_reference}

When you [assign cluster permissions](/docs/containers?topic=containers-users#checking-perms), it can be hard to judge which role you need to assign to a user. Use the tables in the following sections to determine the minimum level of permissions that are required to perform common tasks in {{site.data.keyword.containerlong}}.
{: shortdesc}

## Permissions to create a cluster
{: #cluster_create_permissions}

Review the minimum permissions in {{site.data.keyword.cloud_notm}} IAM that the account owner must set up so that users can create clusters in {{site.data.keyword.containerlong_notm}}.
{: shortdesc}

IAM Services
:    - **Administrator platform** access role for the **Kubernetes Service** in the console (`containers-kubernetes` in the API or CLI) in **All resource groups**.   
     - **Writer** or **Manager** service access role for **Kubernetes Service** in the console (**containers-kubernetes** in the API or CLI) in **All resource groups**.   
     - Administrator platform access role for **Container Registry** in the console (**container-registry** in the API or CLI) at the **Account** level. Do not limit policies for {{site.data.keyword.registrylong_notm}} to the resource group level.
     - If you plan to [expose apps with Ingress](/docs/containers?topic=containers-managed-ingress-about), assign the user **Administrator** or **Editor** platform access role and the **Manager** service access role for **{{site.data.keyword.secrets-manager_short}}** in **All resource groups**.
     - **Viewer** platform access role for the resource group access.
     - If your account [restricts service ID creation](/docs/account?topic=account-restrict-service-id-create), the **Service ID creator** role to **IAM Identity Service** in the console (`iam-identity` in the API or CLI).
     - If your account [restricts API key creation](/docs/account?topic=account-allow-api-create), the **User API key creator** role to **IAM Identity Service** in the console (`iam-identity` in the API or CLI).
     - If you plan to [encrypt your cluster](/docs/containers?topic=containers-encryption#keyprotect):
         - Assign the user the appropriate permission to the key management service (KMS) provider, such as the **Administrator** platform access role.  
         - For clusters that run Kubernetes `1.18.8_1525` or later: When you enable KMS encryption, an additional **Reader** [service-to-service authorization policy](/docs/account?topic=account-serviceauth) between {{site.data.keyword.containerlong_notm}} and your KMS provider, such as {{site.data.keyword.keymanagementserviceshort}}, is automatically created for your cluster, if the policy doesn't already exist. Without this policy, your cluster can't use all the [{{site.data.keyword.keymanagementserviceshort}} features](/docs/containers?topic=containers-encryption#kms-keyprotect-features).
     - **Viewer** platform access role for the resource group access.  

Infrastructure
:    - Classic clusters only: **Super User** role or the [minimum required permissions](/docs/containers?topic=containers-classic-roles) for classic infrastructure.
     - VPC clusters only: **Administrator** platform access role for [VPC Infrastructure](/docs/vpc?topic=vpc-iam-getting-started).

User that creates the cluster
:    In addition to the API key, each individual user must have the following permissions to create a cluster.

:    - **Administrator** platform access role for **Kubernetes Service** in the console (**containers-kubernetes** in the API or CLI). If your access is scoped to a resource group or region, you must also have the **Viewer** platform access role at the **Account** level to view the account's VLANs.
     - **Administrator** platform access role for **Container Registry** in the console (**container-registry** in the API or CLI) at the **Account** level.
     - **Viewer** platform access role to **IAM Identity Service** for account management access.
     - **Viewer** platform access role for the resource group access.


More information about assigning permissions
:    - To understand how access works and how to assign users roles in {{site.data.keyword.cloud_notm}} IAM, see [Setting up access to your cluster](/docs/containers?topic=containers-access-overview#access-checklist).  
     - To create clusters, see [Preparing to create clusters at the account level](/docs/containers?topic=containers-clusters&interface=ui).  
     - For permissions that you might set up for different types of users such as auditors, see [Example use cases and roles](/docs/containers?topic=containers-users#example-iam).  








