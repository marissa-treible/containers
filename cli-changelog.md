---

copyright: 
  years: 2014, 2023
lastupdated: "2023-07-19"

keywords: kubernetes

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}





# CLI change log
{: #cs_cli_changelog}


In the command line, you are notified when updates to the `ibmcloud` CLI and plug-ins are available. Be sure to keep your CLI up-to-date so that you can use all available commands and options.
{: shortdesc}


Refer to the following change logs for a summary of changes for each version of the [{{site.data.keyword.containerlong_notm}} plug-in](/docs/containers?topic=containers-cli-install), which uses the `ibmcloud ks` alias.
  
## Version 1.0
{: #10}

Review the following changes for 1.0 versions of the CLI plug-in.
{: shortdesc}

## Version v1.0.540
{: #cli-10549}

Version 1.0.528 of the CLI was released on 19 July 2023.
:  Adds new [`ibmcloud ks ingress alb autoscale`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoscale_get) commands.
:  Replaces the deprecated `ibmcloud ks alb ls` command in certain command help texts.
:  Updates the help text in various languages. 

## Version v1.0.528
{: #cli-10528}

Version 1.0.528 of the CLI was released on 26 June 2023.
:   Removes unnecessary translations.
:   Adds support for multiple default cluster add-on versions depending on cluster version. Updates `cluster addon versions` output.
:   Updates to `ibmcloud sat cluster register` command better recognize response headers.
:   Updates for pod security admission.



## Version v1.0.523
{: #cli-10523}

Version 1.0.523 of the CLI was released on 25 May 2023.
:   Adds doc links to command help. 
:   Updates description for the Satellite service endpoint allowlist command.
:   Updates CLI to handle the new multiple default add-on versions schema.

## Version v1.0.516
{: #cli-10516}

Version 1.0.516 of the CLI was released on 16 May 2023.
:   Updates the help text in various languages. 


## Version v1.0.510 
{: #cli-10510}

Version 1.0.510 of the CLI was released on 11 April 2023.
:   Adds support for Pod Security admission.
:   Resolved an issue about config file race conditions.
:   Updates the `ibmcloud ks ingress domain create` command output to return the full qualified domain.

## Version v1.0.498
{: #cli-10498}

Version 1.0.498 of the CLI was released on 1 March 2023.
:   Adds the `ibmcloud ks cluster master pod-security get` command.
:   Updates the `golang` version to resolve [CVE-2022-41723](https://cve.mitre.org/cgi-bin/cvename.cgi?name=2022-41723){: external}.
:   Adds an `Architecture` field to the `ibmcloud ks flavor get` command output.
:   Improves formatting of the `ibmcloud ks ingress secret ls` command output.
:   When the `ibmcloud ks cluster config` command returns, you can run `kubectl` or `oc` commands immediately without a waiting period.

## Version 1.0.489
{: #cli-10489}

Version 1.0.489 of the CLI was released on 30 January 2023.
:   Adds a fix where table headings are no longer printed if the output of a command contains no results.
:   Adds the `--secondary-storage` option to the `cluster create vpc-gen2`, `worker-pool create vpc-gen2`, and `flavor get` commands.

## Version 1.0.487
{: #cli-10487}

Version 1.0.487 of the CLI was released on 24 January 2023.
:   Adds the `satellite-service-endpoint allowlist` commands
:   Updates the help text in various languages.



## Version 1.0.480
{: #cli-10480}

Version 1.0.480 of the CLI was released on 14 December 2022.
:   Adjusted `ibmcloud ks flavor get` and `ibmcloud ks flavor ls` commands to show secondary storage details.
:   Introduced Secondary Storage Configuration for `worker-pool get`.
:   Added Ignored Errors to `ingress status-report`.

## Version 1.0.471
{: #cli-10471}

Version 1.0.471 of the CLI was released on 1 December 2022.
:   Adds new endpoint type `vpe`(Virtual Private Endpoint) for cluster config command. 
:   Updates the cluster get command to show VPE url.
:   Adds `infrastructureTopology` field to cluster response.
:   Adds JSON output to Satellite get host command.

## Version 1.0.459
{: #cli-10459}

Version 1.0.459 of the CLI was released on 21 October 2022.
:   Adds the `--infrastructure-topology` option for the `ibmcloud ks cluster create satellite` command. 
:   Adds new `ibmcloud ks flavor get` and `ibmcloud ks flavor ls` commands.

## Version 1.0.454
{: #cli-10454}

Version 1.0.454 of the CLI was released on 3 October 2022.
:   Adds new [Ingress status](/docs/containers?topic=containers-kubernetes-service-cli#alb-commands) commands.
:   Adds the `--operating-system` option for the cluster create commands. 

## Version 1.0.452
{: #cli-10452}

Version 1.0.452 of the CLI was released on 21 September 2022.
:   Updates the help text in various languages.

## Version 1.0.446
{: #cli-10446}

Version 1.0.446 of the CLI was released on 12 September 2022.
:   Adds `--pod-network-interface-selection` option to location create flow.

## Version 1.0.444
{: #cli-10444}

Version 1.0.444 of the CLI was released on 8 September 2022.
:   Adds {{site.data.keyword.secrets-manager_short}} registration to cluster create flow. 
:   Adds worker-pool OS support.
:   Removes Ingress migration command support.

## Version 1.0.439
{: #cli-10439}

Version 1.0.439 of the CLI was released on 26 Aug 2022.
:   Adds new commands to enable, disable, and get status of ALB health checker.  

## Version 1.0.433
{: #cli-10433}

Version 1.0.433 of the CLI was released on 5 Aug 2022.
:   Updates the help text in various languages. 

## Version 1.0.431
{: #cli-10431}

Version 1.0.431 of the CLI was released on 15 Jul 2022.
:   The `KMS Account ID` string is now translatable.

## Version 1.0.430
{: #cli-10430}

Version 1.0.430 of the CLI was released on 13 Jul 2022.
:   Adds the `--kms-account-id ID` option to various commands to support cross-account encryption for KMS enablement, VPC cluster, and worker pool creation.

## Version 1.0.426
{: #cli-10426}

Version 1.0.426 of the CLI was released on 6 Jul 2022.
:   Adds the `--secret-group` option to various {{site.data.keyword.secrets-manager_short}} commands. With this option, you can create secret groups to organize your secrets and control who on your team has access to them.

## Version 1.0.419
{: #cli-10419}

Version 1.0.419 of the CLI was released on 7 June 2022.
:   Implements various backend updates. 

## Version 1.0.415
{: #cli-10415}

Version 1.0.415 of the CLI was released on 26 May 2022.
:   Updates the help text in various languages.

## Version 1.0.408
{: #cli-10408}

Version 1.0.408 of the CLI was released on 6 May 2022.
:   Fixes Ingress secret type backward compatibility. 
:   Deprecates the Ingress migration tool.

## Version 1.0.404
{: #cli-10404}

Version 1.0.404 of the CLI was released on 28 April 2022.
:   Adds features visible to select users only. 

## Version 1.0.403
{: #cli-10403}

Version 1.0.403 of the CLI was released on 26 April 2022.
:   Adds support for M1 processor on Linux and macOS.
:   Updates the help text in various languages. 

## Version 1.0.394
{: #cli-10394}

Version 1.0.394 of the CLI was released on 7 April 2022.
:   Adds the `--operating-system` label to `ibmcloud ks worker-pool create satellite` and `ibmcloud ks cluster create satellite`.

## Version 1.0.384
{: #cli-10384}

Version 1.0.384 of the CLI was released on 21 March 2022.
:   Adds the `--output` option to the `ibmcloud ks storage assignment ls` and `ibmcloud ks storage config ls` commands.

## Version 1.0.374
{: #cli-10374}

Version 1.0.374 of the CLI was released on 24 February 2022.
:   Removes the default zone in the `ibmcloud ks cluster create satellite` command.

## Version 1.0.372
{: #cli-10372}

Version 1.0.372 of the CLI was released on 18 February 2022.
:   Modifies relevant commands to accept either the `--worker-pool` or `-p` options for worker pool options.
:   Updates JSON outputs to include additional resources, such as add-ons, VLANs, and subnets. 
:   Makes `ibmcloud ks ingress` commands generally available.
:   Updates the `ibmcloud ks ingress alb get` command output to include ALB status. 
:   Adds the new `ibmcloud ks nlb-dns get` command.
:   Adds the new `ibmcloud ks ca get` command. 
:   Updates the help text in various languages. 

## Version 1.0.353
{: #cli-10353}

Version 1.0.353 of the CLI was released on 3 December 2021.
:   Updates the help text in various languages.

## Version 1.0.347
{: #cli-10347}

Version 1.0.347 of the CLI was released on 15 November 2021.
:   Updates various output messages.

## Version 1.0.344
{: #cli-10344}

Version 1.0.344 of the CLI was released on 15 November 2021.
:   Includes a Go version update from `1.16.7` to `1.16.10` and other fixes.

## Version 1.0.334
{: #cli-10334}

Version 1.0.334 of the CLI was released on 26 October 2021.
{: shortdesc}

- Adds the `ibmcloud ks cluster master private-service-endpoint disable` command. You can now disable private service endpoints to remove private accessibility to your cluster master. 
- Updates the help text in various languages. 

## Version 1.0.331
{: #cli-10331}

Version 1.0.331 of the CLI was released on 12 October 2021.
{: shortdesc}

- Adds the `--policy` option to the `ibmcloud ks master audit-webhook set` command. You can now configure the amount of information included in your cluster audits by specifying the `default` or `verbose` audit policy type.

## Version 1.0.312
{: #cli-10312}

Version 1.0.312 of the CLI was released on 9 August 2021.

- Removes the `ibmcloud ks nlb-dns monitor status` command. Checking the health of individual IP addresses, which was previously supported by the Cloudflare DNS provider, is not supported by the Akamai DNS provider. Instead, you can check the overall health of a subdomain by using the `ibmcloud ks nlb-dns monitor ls` command. For more information on the migration to Akamai for all `containers.appdomain.cloud`, `containers.mybluemix.net`, and `containers.cloud.ibm.com` domains, see the [migration announcement](https://cloud.ibm.com/notifications?selected=1621697674798){: external}.
- Removes the `ibmcloud ks cluster addon enable kube-terminal` command. The Kubernetes web terminal add-on became unsupported on 1 July 2021. Instead, use the [IBM Cloud Shell](/docs/cloud-shell?topic=cloud-shell-shell-ui).

- Makes the `ibmcloud ks cluster addon update` feature available to all users.
- Updates the help text in various languages.

## Version 1.0.300
{: #cli-10300}

Version 1.0.300 of the CLI was released on 12 July 2021.

- Updates the help text in various languages.

## Version 1.0.295
{: #cli-10295}

Version 1.0.295 of the CLI was released on 24 June 2021.

- Removes the unsupported {{site.data.keyword.containerlong_notm}} Ingress image version from the output of `ibmcloud ks alb version ls`.
- Adds the following updates for add-on commands: - Adds the `ibmcloud ks cluster addon get` command to view the details of an installed add-on. 
- Adds the `ibmcloud ks cluster addon options` command to view optional installation settings for an add-on. 
- Adds the `--param` option to specify an optional installation setting for the `ibmcloud ks cluster addon enable openshift-container-storage` command. 
- Updates the help text in various languages.

## Version 1.0.275
{: #cli-10275}

Version 1.0.275 of the CLI was released on 26 May 2021.
  
- The `--region` option is now required for the `ibmcloud ks api-key reset`, `ibmcloud ks credential get`, and `ibmcloud ks credential set` commands. 
- Adds the `ibmcloud ks cluster addon versions` command to list the Kubernetes versions that are supported for each add-on version, and deprecates the `ibmcloud ks addon-versions` command.
- The `ibmcloud ks image-security disable` and `ibmcloud ks image-security enable` commands are now generally available. 
- The IAM token that is used for your CLI session is now refreshed 5 minutes before expiration to keep the session active. 
- Updates the help text in various languages.

## Version 1.0.258
{: #cli-10258}

Version 1.0.258 of the CLI was released on 26 April 2021.
  
- Adds the `--ip` option to the `ibmcloud ks nlb-dns create vpc-gen2` and `ibmcloud ks nlb-dns rm vpc-gen2` commands to support DNS records for Network Load Balancers for VPC. 
- Adds the `--dns-type` option to `ibmcloud ks nlb-dns create` commands to specify the DNS provider type for the subdomain registration. Currently, only `public` DNS is supported. 
- Adds a warning that the `--region` option is planned to be required for the `ibmcloud ks api-key reset`, `ibmcloud ks credential get`, and `ibmcloud ks credential set` commands as of 10 May 2021. The region is already required by the API. Currently in the CLI, the region defaults to the targeted region if the `--region` option is not used. 
- In the output of the `ibmcloud ks addon-versions` command, changes the `Min. OpenShift version` column to `Supported Openshift Range`. 
- When `--output json` is specified for the `ibmcloud ks storage attachment get` or `ibmcloud ks storage attachment ls` commands, fixes the output so that a volume table is not printed after the JSON output. 
- Fixes a `golang` vulnerability for [CVE-2020-28852](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-28852){: external}. 
- Updates the help text in various languages.

## Version 1.0.233
{: #cli-10233}

Version 1.0.233 of the CLI was released on 1 March 2021.

- Adds `satellite` as a supported provider to the output of the `ibmcloud ks cluster ls` command. 
- General refactoring and improvements.

## Version 1.0.231
{: #cli-10231}

Version 1.0.231 of the CLI was released on 25 February 2021.

- Updates the Go version to 1.15.8. 
- Updates the help text in various languages.

## Version 1.0.223
{: #cli-102238}

Version 1.0.223 of the CLI was released on 8 February 2021.

- Adds the [`ibmcloud ks worker-pool label set`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pool_label_set) and [`ibmcloud ks worker-pool label rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pool_label_rm) commands to set and remove custom Kubernetes labels for all worker nodes in a worker pool.

## Version 1.0.208
{: #cli-10208}

Version 1.0.208 of the CLI was released on 18 December 2020.

- Updates the help text in various languages.

## Version 1.0.206
{: #cli-10206}

Version 1.0.206 of the CLI was released on 10 December 2020.

- Adds the `ibmcloud ks ingress lb get`, `ibmcloud ks ingress lb proxy-protocol disable`, and `ibmcloud ks ingress lb proxy-protocol disable` [beta commands](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_lb_proxy-protocol_enable) to manage the configuration of load balancers that expose Ingress ALBs in your cluster. For example, you can enable the NGINX PROXY protocol so that client connection information is passed in request headers to ALBs. 
- Adds the optional `--endpoint` option to the `ibmcloud ks cluster config` command to specify a type of endpoint for the cluster context, such as the cluster's private cloud service endpoint. 
- Updates the help text in various languages. 
- Updates the Go version to 1.15.6.

## Version 1.0.197
{: #cli-10197}

Version 1.0.197 of the CLI was released on 18 November 2020.

- Adds a warning message to the `ibmcloud ks cluster config` command about temporary `kubectl` command failures due to RBAC synchronization. 
- Ensures that incident IDs are returned with 500-level messages. 
- In `ibmcloud ks cluster storage` commands, the cluster name is now accepted in the `--cluster` option in addition to the cluster ID. 
- Updates the output of the `ibmcloud ks ingress alb migrate` command to be more readable. 
- Updates the help text in various languages.

## Version 1.0.178
{: #cli-10178}

Version 1.0.178 of the CLI was released on 6 October 2020.

- Updates the Go version to 1.15.2.
- Updates the help text in various languages.

## Version 1.0.171
{: #cli-10171}

Version 1.0.171 of the CLI was released on 24 September 2020.

- Shifts all existing `ibmcloud ks cluster feature` commands into the [`ibmcloud ks cluster master`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_master_pse_enable) subcategory. 
- Adds the cluster `Status`, the `Pod Subnet`, and the `Service Subnet` fields to the output of the `ibmcloud ks cluster get` command. 
- Updates the help text in various languages.

## Version 1.0.157
{: #cli-10157}

Version 1.0.157 of the CLI was released on 24 August 2020.

**Added commands**: The following commands are added. 
- Adds the [`ibmcloud ks cluster ca create`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_ca_create), [`ibmcloud ks cluster ca rotate`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_ca_rotate), and [`ibmcloud ks cluster ca status`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_ca_status) commands to manage the rotation of certificate authority (CA) certificates for your cluster components. 
- Adds the [`ibmcloud ks ingress secret`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_secret_create) set of beta commands to manage Ingress secrets in your cluster, such as creating secrets for TLS certificates that are stored in {{site.data.keyword.cloudcerts_long_notm}}. 
- Adds the `ibmcloud ks ingress alb migrate` set of beta commands to migrate resources that are formatted for ALBs that run the {{site.data.keyword.containerlong_notm}} Ingress image to resources that are formatted for ALBs that run the Kubernetes Ingress image. 
- Adds the [`ibmcloud ks ingress alb enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_configure) and [`ibmcloud ks ingress alb disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_disable) commands. 
- Adds the optional `--version` option to the `ibmcloud ks ingress alb create` command to specify the {{site.data.keyword.containerlong_notm}} Ingress image version or Kubernetes Ingress image version for the ALB.

**Renamed commands**: The following commands are shifted to new naming categories. 
- Shifts all existing `ibmcloud ks alb` commands into the [`ibmcloud ks ingress alb`](/docs/containers?topic=containers-kubernetes-service-cli#alb-commands) subcategory. 
- Changes the names of the following options in the relevant `ibmcloud ks ingress alb` commands: `--alb-id` to `--alb`, `--secret-name` to `--name`, and `--user-ip` to `--ip`.

**Deprecated commands**: The following commands are deprecated in favor of the new commands. 
- Deprecates the `ibmcloud ks alb cert` set of commands. 
- Deprecates the `ibmcloud ks alb configure` command. 
- Removes the deprecated `ibmcloud ks alb rollback` command,

## Version 1.0.143
{: #cli-10143}

Version 1.0.143 of the CLI was released on 6 August 2020.

- Adds the [`ibmcloud ks quota ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_quota_ls) command to list all quota and limits for cluster-related resources in your {{site.data.keyword.cloud_notm}} account. 
- Deprecates the `--json` option. To print a command output in JSON format, use the `--output json` option instead. 
- Deprecates the `-s` option. To not show the message of the day or update reminders in command output, use the `-q` option instead. 
- Updates `ibmcloud ks cluster ls` command so that if you include the `--ouput json` option but don't include the `--provider` option, only classic clusters are returned. 
- Corrects the example master update command that is displayed in the output of the `ibmcloud ks cluster get` command when a master update is available. 
- Adds information about the effects of worker node replacement in the warning message for the `ibmcloud ks worker replace` command. 
- Standardizes the help text for options that have a list of supported values. 
- Updates the help text in various languages.

## Version 1.0.118
{: #cli-10118}

Version 1.0.118 of the CLI was released on 7 July 2020.

- Deprecates the `ibmcloud ks cluster user-subnet add`, `ibmcloud ks cluster user-subnet rm`, and `ibmcloud ks va` commands.
- Updates the Go version to 1.13.12 for [CVE-2020-7919](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-7919){: external}. 
- Fixes a bug for downloading the Calico configuration by using the `--network` option in the `ibmcloud ks cluster config` command. 
- Updates the help text for the `--endpoint` option of the `ibmcloud ks kms enable` command. 
- Updates the help text in various languages.

## Version 1.0.99
{: #cli-1099}

Version 1.0.99 of the CLI was released on 15 June 2020.


- Updates the help text in various places.

## Version 1.0.94
{: #cli-1094}

Version 1.0.94 of the CLI was released on 9 June 2020.

- Adds the [`ibmcloud ks cluster addon enable static-route`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_enable_static-route) and [`ibmcloud ks cluster addon disable static-route`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_disable_static-route) commands to manage the Static Route add-on for your cluster. 
- Adds the [`ibmcloud ks worker-pool taint set`](/docs/containers?topic=containers-kubernetes-service-cli#worker_pool_taint_set) and [`ibmcloud ks worker-pool taint rm`](/docs/containers?topic=containers-kubernetes-service-cli#worker_pool_taint_rm) commands to set and remove Kubernetes taints on worker nodes in a worker pool. 
- Beta: Adds the [`ibmcloud ks storage`](/docs/containers?topic=containers-kubernetes-service-cli#cs_storage) set of commands to view and modify storage resources in your cluster. 
- Moves the `ibmcloud ks locations` command to the `Informational Commands` group in the help output of `ibmcloud ks`. 
- Updates the help text for options in the `ibmcloud ks nlb-dns monitor configure` command. 
- Updates the help text in various languages.

## Version 1.0.84
{: #cli-1084}

Version 1.0.84 of the CLI was released on 26 May 2020.

- Fixes bugs for credentials in Kubernetes configuration contexts: 
    - When you download the contexts for clusters that run Kubernetes version 1.17 or later, those contexts are merged into your `kubeconfig` file. The tokens from the version 1.17 or later contexts now don't overwrite tokens for any version 1.16 or later contexts. 
    - Credentials are now correctly added to your `kubeconfig` file when you download the context for a cluster. 
    - Fixes credential issues for CLI plug-in installations on macOS that don't use `cgo`. 
- Adds commands for creating and managing VPC clusters.
    - [`alb configure vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_alb_configure_vpc_gen2)
    - [`alb create vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_alb-create-vpc-gen2)
    - [`cluster create vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_cluster-create-vpc-gen2)
    - [`nlb-dns create vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-create-vpc-gen2)
    - [`nlb-dns rm vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-rm-vpc-gen2)
    - [`worker-pool create vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_worker_pool_create_vpc_gen2)
    - [`zone add vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_zone-add-vpc-gen2)
- Adds the **Ingress Status** and **Ingress Message** fields to the output of the `ibmcloud ks cluster get` command. For more information about these fields, see [Checking the status of Ingress components](/docs/containers?topic=containers-ingress-status).
- Adds the ALB ID to the output of the `ibmcloud ks alb create` command. 
- Adds the supported `Auth version` to the output of the `ibmcloud ks alb versions` command. 
- Adds the supported range of Kubernetes versions that your cluster must run to the output of the `ibmcloud ks addon versions` command. 
- Updates the help text in various languages.

## Version 1.0.57
{: #cli-1057}

Version 1.0.57 of the CLI was released on 7 May 2020.

- Adds a check for deprecated positional options. 
- Updates the macOS DNS resolver to fix network issues when you use the CLI plug-in with a VPN connection. 
- Help documentation updates: 
    - Adds instructions for enabling or disabling an add-on to the help text for the `ibmcloud ks addon-versions` command. 
    - Clarifies optional and required options in option help text. 
    - Updates the help text in various languages.

## Version 1.0.28
{: #cli-1028}

Version 1.0.28 of the CLI was released on 6 April 2020.

- Adds the optional `--alb-id` option to `ibmcloud ks alb update` so that you can specify IDs of individual ALBs to update. 
- Adds the optional `--show-storage` option to `ibmcloud ks flavors` to show additional raw disks that are available for [SDS worker node flavors](/docs/containers?topic=containers-planning_worker_nodes#sds). 
- Adds a message to the output of `ibmcloud ks pull-secret apply` about the amount of time it takes for the pull secrets to be applied to your cluster.

## Version 1.0.15
{: #cli-1015}

Version 1.0.15 of the CLI was released on 24 March 2020.

- Adds the [`ibmcloud ks nlb-dns secret regenerate`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-secret-regenerate) and [`ibmcloud ks nlb-dns secret rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-secret-rm) commands to help you manage secrets for NLB subdomains. 
- Adds the optional `--worker-pool WORKER_POOL` option to `ibmcloud ks zone rm`. 
- Deprecates the option to specify a YAML file in the `--file` option of the `ibmcloud ks cluster create` and `ibmcloud ks worker add` commands. Instead, specify values for your cluster in the supported options for these commands. 
- Fixes the following bugs: 
    - For `ibmcloud ks cluster rm`, the `--force-delete-storage` option no longer sets the `-f` option.
    - For `ibmcloud ks cluster create`, the `--private-only` option no longer requires the `--private-vlan` option.
- Updates the help text in various languages.

## Version 1.0.0
{: #cli-100}

Version 1.0.0 of the CLI was released on 26 March 2020.

- Introduces permanent behavior and syntax changes that are not compatible with earlier versions. For a summary of the changes in version 1.0, see [Using version 1.0 of the plug-in](#changelog_beta).


## Deprecated versions
{: #deprecated}

All versions of the CLI plug-in that are earlier than version 1.0 are no longer supported. You can review the archive of the change logs. To update to the latest version, see [Updating to version 1.0 of the plug-in](#changelog_beta).
{: shortdesc}

### Updating to version 1.0 of the plug-in
{: #changelog_beta}

Version 1.0 of the CLI plug-in was released on 16 March 2020. This version contains permanent syntax and behavior changes that are not compatible with earlier versions.

To maintain all CLI functionality, update and test any automation before you update to 1.0 by checking out the [`ibmcloud ks script update` command](/docs/containers?topic=containers-kubernetes-service-cli#script_update) and setting your `IKS_BETA_VERSION` environment variable to `1.0`. After you update your scripts, update your CLI to version `1.0` of the plug-in.
{: important}

Check out the following syntax and behavior changes between each version of the CLI plug-in:

|Functionality|`0.2`|`0.3`|`0.4`|`1.0`|
|-------------|-----|-----|-----|-----|
| Supported? | Deprecated | Deprecated | Deprecated | Default |
| `ibmcloud ks help` output structure  \n -  Legacy: Alphabetical list of commands  \n -  Latest: Categories of commands | Legacy | Legacy | Latest | Latest |
| Command structure  \n -  Legacy: Hyphenated structure (`ibmcloud ks cluster-get`)  \n -  Latest: Spaced structure (`ibmcloud ks cluster get`) | Legacy and latest | Legacy and latest | Legacy and latest | Latest |
| Positional options  \n -  Legacy: options specified by position (`cluster-get mycluster`)  \n -  Latest: options specified by options (`cluster get --cluster mycluster`) | Legacy and latest | Legacy and latest | Legacy and latest | Latest |
| Repeated options  \n -  Legacy: Comma-delineated values (`--worker-pools pool1,pool2,pool3 ...`)  \n -  Latest: Repeated options for each value with optional shorthand option aliases (`-p pool1 -p pool2 ...`) | Legacy | Legacy | Legacy and latest | Latest |
| option format  \n -  Legacy: Camel-case (`--showResources`)  \n -  Latest: Dashed (`--show-resources`) | Legacy | Legacy | Legacy and latest | Latest |
| Cluster context provided by `ibmcloud ks cluster-config`  \n -  Legacy: Provides a command that you must copy and paste to set the new `kubeconfig` file as your current `KUBECONFIG` environment variable. You must set your environment variable before you can interact with your cluster.  \n -  Latest: Appends the new `kubeconfig` file to your existing `kubeconfig` file in `~/.kube/config` or the [last file that is set by the `KUBECONFIG` environment variable](/docs/containers?topic=containers-cli-install). After you run `ibmcloud ks cluster config`, you can interact with your cluster immediately, and quickly [change the context to other clusters in the Kubernetes context](/docs/containers?topic=containers-cli-install). | Legacy | Legacy | Legacy | Latest |
| API endpoint  \n -  Legacy: [Target a region and use a regional endpoint to work with resources in that region](/docs/containers?topic=containers-regions-and-zones#bluemix_regions).  \n -  Latest: [Use the global endpoint to work with resources in any location](/docs/containers?topic=containers-regions-and-zones#bluemix_regions). | Legacy | Latest | Latest | Latest |
{: caption="Latest versions of the redesigned {{site.data.keyword.containerlong_notm}} plug-in" caption-side="bottom"}

### Version 0.4
{: #04}

Review the following changes for 0.4 versions of the CLI plug-in.
{: shortdesc}

Version 0.4 of the CLI plug-in is deprecated. To update to the latest version, see [Updating to version 1.0 of the plug-in](#changelog_beta).
{: deprecated}

#### Version 0.4.102
{: #cli-04102}

Version 0.4.102 of the CLI was released on 4 March 2020.

- Adds the [`ibmcloud ks alb create classic`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_create) and `ibmcloud ks alb create vpc-classic` commands so that you can create and enable new public or private ALBs in a zone. 
- Removes the beta tag from `ibmcloud ks kms` commands. 
- Adds `--public-endpoint` as an optional option to the `ibmcloud ks kms enable` command. Include this option only if you want to use the KMS public cloud service endpoint instead of the private cloud service endpoint. 
- Fixes a bug so that the new `--version` option is accepted in `ibmcloud ks cluster create` commands. 
- Help documentation updates: 
    - Fixes incorrect deprecation warnings for commands that are correctly formatted with version 1.0 syntax. 
    - Removes incorrect `ibmcloud ks cs` syntax from command deprecation warnings.
    - Updates the help text in various languages.

#### Version 0.4.90
{: #cli-0490}

Version 0.4.90 of the CLI was released on 19 February 2020.

- Updates the Go version to 1.13.5 and removes `xgo`. 
- **Command updates**: 
    - Adds the `--provider` option to the [`ibmcloud ks flavors`](/docs/containers?topic=containers-kubernetes-service-cli#cs_machine_types) command. 
    - Accepts newer option names like `--flavor` instead of `--machine-type` across various commands.
    - Changes the default value of the `--flavor` option to `free`.
    - Deprecates the `--disable-deployment` option of the `ibmcloud ks alb configure vpc-classic` command. 
- **VPC-specific command updates**: 
    - Fixes the [`ibmcloud ks zone rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_zone_rm) command for VPC multizone clusters. 
    - For the [`ibmcloud ks vpcs`](/docs/containers?topic=containers-kubernetes-service-cli#cs_vpcs) command, defaults to list only generation 1 (`vpc-classic`) VPCs. 
    - Revises the `ibmcloud ks worker-pool create vpc-classic` command to remove the `--disable-disk-encrypt` option and to hide the `--hardware` option because it only accepts one value. 
- **Help documentation updates**: 
    - Add deprecation warnings to encourage you to use the newer `classic` subcommands. For example, use `ibmcloud ks cluster create classic` instead of `ibmcloud ks cluster create`.
    - Standardizes formatting in help text, such as adding single quotes around variable names or styling for URLs. 
    - Updates the help text in various languages.|

#### Version 0.4.66
{: #cli-0466}

Version 0.4.66 of the CLI was released on 19 December 2019.

- Adds a **Status** field to the `ibmcloud ks alb cert get` command. The previous **Status** field is now called **State**. 
- Fixes a bug so that help text is now properly displayed for some commands, such as `ibmcloud ks flavors` and `ibmcloud ks subnets`.

#### Version 0.4.64
{: #cli-0464}

Version 0.4.64 of the CLI was released on 11 December 2019.


- Updates the Go version to 1.12.11. 
- Updates the help text in various languages.
  
#### Version 0.4.61
{: #cli-0461}

Version 0.4.61 of the CLI was released on 26 November 2019.

- Removes the `kube-audit` log source option from `ibmcloud ks logging config` commands.
- Adds a check to verify that you are logged in to the {{site.data.keyword.cloud_notm}} CLI before a command request is issued. 
- Updates the help text in various languages.
  
#### Version 0.4.51
{: #cli-0451}

Version 0.4.51 of the CLI was released on 7 November 2019.

- Adds the [`ibmcloud ks kms crk ls`](/docs/containers?topic=containers-kubernetes-service-cli#ks_kms_crk_ls), [`ibmcloud ks kms enable`](/docs/containers?topic=containers-kubernetes-service-cli#ks_kms_enable), and [`ibmcloud ks kms instance ls`](/docs/containers?topic=containers-kubernetes-service-cli#ks_kms_instance_ls) commands to create and manage key management service (KMS) providers in a cluster. 
- Adds the optional `--skip-advance-permissions-check` option to `ibmcloud ks cluster create` and `ibmcloud ks cluster rm`. 
- Changes the `--vpc-id` option to be optional for `ibmcloud ks worker-pool create vpc-classic`. 
- Fixes the error message for when no cluster name or ID is specified for `ibmcloud ks worker get` or `ibmcloud ks worker-pool get`. 
- Adds `public` and `private` as supported values for the `--hardware` option of `ibmcloud ks worker-pool create classic`. 
- When the `--admin` option is included in `ibmcloud ks cluster config`, removes `-admin` from the cluster name in the `KUBECONFIG` file path. 
- Updates all command help to use the new space-separated syntax.

#### Version 0.4.42
{: #cli-0442}

Version 0.4.42 of the CLI was released on 24 October 2019.

- Adds the cluster ID to the output of `ibmcloud ks cluster create`. 
- Updates the Go version to 1.12.10 to fix `golang` vulnerabilities for [CVE-2019-16276](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-16276){: external}.

#### Version 0.4.38
{: #cli-0438}

Version 0.4.38 of the CLI was released on 14 October 2019.


- Adds the `ibmcloud ks nlb-dns create vpc-classic`, [`ibmcloud ks nlb-dns replace`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-replace), and `ibmcloud ks nlb-dns rm vpc-classic` commands to create and manage DNS subdomains for VPC load balancers in VPC clusters.
- Adds the `--secret-namespace` option to the `ibmcloud ks nlb-dns create classic` and `ibmcloud ks nlb-dns create vpc-classic` commands to specify the Kubernetes namespace that you want the SSL secret for the DNS subdomain to be created in. 
- Updates status information of worker nodes for VPC clusters. 
- Updates the help text in various languages.

#### Version 0.4.31
{: #cli-0431}

Version 0.4.31 of the CLI was released on 24 September 2019.


- Adds the `--gateway-enabled` option to the `ibmcloud ks cluster create classic` command to create a gateway-enabled cluster. You can enable a gateway only on standard, Kubernetes clusters during cluster creation.
- Removes the deprecated `region get`, `region set`, and `region ls` commands from help output. 
- Updates command structure to the new spaced format in help output. 
- Adds a warning to the output of legacy `cluster config` behavior. For more information, see the [version 1.0 plug-in documentation](/docs/containers?topic=containers-cs_cli_changelog#changelog_beta). 
- Fixes a bug so that `worker reload` and `messages` commands now fail if the command errors. 
- Updates the help text in various languages.

#### Version 0.4.23
{: #cli-0423}

Version 0.4.23 of the CLI was released on 16 September 2019.

- Decreases startup time for the plug-in. 
- Fixes a Go version issue for macOS users. 
- Improves debug tracing. 
- In `ibmcloud ks logging filter` commands, the syntax of the `--logging-config` option changes from accepting multiple values in a comma-separated list to requiring repeated options. 
- Minor bug and security fixes. 
- Updates message, warning, and help text.

#### Version 0.4.3
{: #cli-043}

Version 0.4.3 of the CLI was released on 4 September 2019.

- Adds deprecation warnings for legacy commands to error messages that are sent to `stderr`.

#### Version 0.4.1
{: #cli-041}

Version 0.4.1 of the CLI was released on 3 April 2019.

- Sets the {{site.data.keyword.containerlong_notm}} plug-in to the redesigned format by default. This redesigned version includes changes such as categorical lists instead of an alphabetical list of commands in the output of `ibmcloud ks help`, spaced-structured commands instead of hyphenated-structure commands, repeated options instead of multiple values in comma-separated lists, and more. For a full list of the changes between version `0.3` and `0.4`, see the comparison table in [Using the beta {{site.data.keyword.containerlong_notm}} plug-in](/docs/containers?topic=containers-cs_cli_changelog#changelog_beta). 
- Adds the [`ibmcloud ks script update`](/docs/containers?topic=containers-kubernetes-service-cli#script_update) command to rewrite scripts that call `ibmcloud ks` commands. 
- Improves error handling for `ibmcloud ks cluster ls`. 
- Updates help text.



### Version 0.3
{: #03}

Review the following changes for 0.3 versions of the CLI plug-in.
{: shortdesc}

Version 0.3 of the CLI plug-in is deprecated. To update to the latest version, see [Updating to version 1.0 of the plug-in](#changelog_beta).
{: deprecated}

#### Version 0.3.112
{: #cli-03112}

Version 0.3.112 of the CLI was released on 19 August 2019.

- With the release of the [{{site.data.keyword.containerlong_notm}} version 2 API](/docs/containers?topic=containers-cs_api_install#api_about), the {{site.data.keyword.cloud_notm}} CLI `kubernetes-service` plug-in supports both classic and VPC infrastructure providers. Some `ibmcloud ks` commands support only one type of infrastructure, whereas other commands include additional names or options. 
- Adds the `--pod-subnet` and `--service-subnet` options to the `ibmcloud ks cluster create classic` commands for standard clusters that run Kubernetes 1.15 or later. If you plan to connect your cluster to on-premises networks, you can avoid subnet conflicts by specifying a custom subnet CIDR that provides the private IP addresses for your pods and subnets. 
- Enhances the `ibmcloud ks nlb-dns create` and `ibmcloud ks nlb-dns add` commands so that you can add more than one IP address at a time. For example, to create a DNS entry for multiple network load balancer IP addresses, use multiple options such as `ibmcloud ks nlb-dns create --cluster mycluster --ip IP1 --ip IP2`.

#### Version 0.3.103
{: #cli-03103}

Version 0.3.103 of the CLI was released on 12 August 2019.

- General refactoring and improvements.

#### Version 0.3.99
{: #cli-0399}

Version 0.3.99 of the CLI was released on 5 August 2019.

- Improves error handling for `ibmcloud ks cluster config`. 
- Updates the help text in various languages.

#### Version 0.3.95
{: #cli-0395}

Version 0.3.95 of the CLI was released on 30 July 2019.


- Adds the [`ibmcloud ks cluster subnet detach`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_subnet_detach) command to detach a public or private portable subnet in a classic IBM Cloud infrastructure account from a cluster. 
- Renames the `ibmcloud ks machine-types` command to `ibmcloud ks flavors`. You can still use the `machine-types` alias. 
- In the output of `ibmcloud ks flavors (machine-types)`, indicates flavors that are supported only for {{site.data.keyword.containerlong_notm}} or only for {{site.data.keyword.openshiftlong_notm}}. 
- In the output of `ibmcloud ks cluster get`, changes the term `Owner` to `Creator` to reflect that the field returns information about the user that created the cluster. 
- Improves error handling for `ibmcloud ks zone add`. 
- Updates the help text in various languages.

#### Version 0.3.58
{: #cli-0358}

Version 0.3.58 of the CLI was released on 2 July 2019.

- Fixes a bug so that a worker pool rebalance message is not returned when the cluster autoscaler is enabled.
- Updates help text for the `cluster master private-service-endpoint enable` and `nlb-dns monitor configure` commands. 
- Updates the help text in various languages.
  
#### Version 0.3.49
{: #cli-0349}

Version 0.3.49 of the CLI was released on 18 June 2019.

- Updates the Go version to 1.12.6.

#### Version 0.3.47
{: #cli-0347}

Version 0.3.47 of the CLI was released on 15 June 2019.

- Fixes a bug so that empty tables are not returned in the output of `ibmcloud ks kube-versions`. 
- Updates the NLB DNS model so that an array of NLB IP addresses is returned by `ibmcloud ks nlb-dns ls`. 
- Changes the description text for the {{site.data.keyword.containerlong_notm}} CLI plug-in.

#### Version 0.3.34
{: #cli-0334}

Version 0.3.34 of the CLI was released on 31 May 2019.


- Adds the `versions` command to list all supported Kubernetes and {{site.data.keyword.redhat_openshift_notm}} versions. 
- Deprecates the `kube-versions` command.

#### Version 0.3.33
{: #cli-0333}

Version 0.3.33 of the CLI was released on 30 May 2019.

- Adds the `--powershell` option to the `cluster config` command to retrieve Kubernetes environment variables in Windows PowerShell format. 
- Deprecates the `region get`, `region set`, and `region ls` commands. For more information, see [global endpoint functionality](/docs/containers?topic=containers-regions-and-zones#endpoint).

#### Version 0.3.28
{: #cli-0328}

Version 0.3.28 of the CLI was released on 23 May 2019.

- Adds the [`ibmcloud ks infra-permissions get`](/docs/containers?topic=containers-kubernetes-service-cli#infra_permissions_get) command to check whether the credentials that allow [access to the IBM Cloud infrastructure portfolio](/docs/containers?topic=containers-access-creds) for the targeted resource group and region are missing suggested or required infrastructure permissions.
- Adds the `--private-only` option to the `zone network-set` command to unset the public VLAN for the worker pool metadata. Subsequent worker nodes in that worker pool zone are connected to a private VLAN only.
- Removes the `--force-update` option from the `worker update` command. 
- Adds the **VLAN ID** column to the output of the `alb ls` and `alb get` commands. 
- Adds the **Multizone Metro** column to the output of the `locations` command to designate zones that are multizone-capable. 
- Adds the **Master State** and **Master Health** fields to the output of the `cluster get` command. For more information, see [Master states](/docs/containers?topic=containers-health-monitor#states_master). 
- Updates the help text in various languages.

#### Version 0.3.8
{: #cli-038}

Version 0.3.8 of the CLI was released on 30 April 2019.

- Adds support for [global endpoint functionality](/docs/containers?topic=containers-regions-and-zones#endpoint) in version `0.3`. By default, you can now view and manage all your {{site.data.keyword.containerlong_notm}} resources in all locations. You are not required to target a region to work with resources. 
- Adds the [`ibmcloud ks locations`](/docs/containers?topic=containers-kubernetes-service-cli#cs_supported-locations) command to list all locations that {{site.data.keyword.containerlong_notm}} supports. 
- Adds the `--location` option to the `cluster ls` and `zone ls` commands to filter resources by one or more locations. - Adds the `--region` option to the `credential set/unset/get`, `api-key reset`, and `vlan spanning get` commands. To run these commands, you must specify a region in the `--region` option.


### Version 0.2
{: #02}

Review the following changes for 0.2 versions of the CLI plug-in.
{: shortdesc}

Version 0.2 of the CLI plug-in is deprecated. To update to the latest version, see [Updating to version 1.0 of the plug-in](#changelog_beta).
{: deprecated}

#### Version 0.2.102
{: #cli-02102}

Version 0.2.102 of the CLI was released on 15 April 2019.

- Adds the [`ibmcloud ks nlb-dns` group of commands](/docs/containers?topic=containers-kubernetes-service-cli#nlb-dns) for registering and managing a subdomain for network load balancer (NLB) IP addresses, and the [`ibmcloud ks nlb-dns monitor` group of commands](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-monitor-configure) for creating and modifying health check monitors for NLB subdomains. For more information, see [Registering NLB IPs with a DNS subdomain](/docs/containers?topic=containers-loadbalancer_hostname#loadbalancer_hostname_dns).

#### Version 0.2.99
{: #cli-0299}

Version 0.2.99 of the CLI was released on 9 April 2019.

- Updates help text. 
- Updates the Go version to 1.12.2.

#### Version 0.2.95
{: #cli-02}

Version 0.2.95 of the CLI was released on 3 April 2019.

- Adds versioning support for managed cluster add-ons.
- Adds the [`ibmcloud ks addon-versions`](/docs/containers?topic=containers-kubernetes-service-cli#cs_addon_versions) command. 
- Adds the `--version` option to [`ibmcloud ks cluster addon enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_enable) commands.
- Updates the help text in various languages. 
- Updates short links to documentation in help text. 
- Fixes a bug where JSON error messages printed in an incorrect format. 
- Fixes a bug where using the silent option (`-s`) on some commands prevented errors from printing.
  
#### Version 0.2.80
{: #cli-0280}

Version 0.2.80 of the CLI was released on 19 March 2019.

- Adds support for enabling [master-to-worker communication with service endpoints](/docs/containers?topic=containers-plan_basics#workeruser-master) in standard clusters in [VRF-enabled accounts](/docs/account?topic=account-vrf-service-endpoint#vrf). 
- Adds the `--private-service-endpoint` and `--public-service-endpoint` options to the [`ibmcloud ks cluster-create`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_create) command. 
- Adds the **Public Service Endpoint URL** and **Private Service Endpoint URL** fields to the output of `ibmcloud ks cluster get`. 
- Adds the [`ibmcloud ks cluster master private-service-endpoint enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_master_pse_enable) command. 
- Adds the [`ibmcloud ks cluster master public-service-endpoint enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_master_pub_se_enable) command.
- Adds the [`ibmcloud ks cluster master public-service-endpoint disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_master_pub_se_disable) command.
- Updates the help text in various languages. 
- Updates the Go version to 1.11.6. 
- Resolves intermittent networking issues for macOS users.

#### Version 0.2.75
{: #cli-0275}

Version 0.2.75 of the CLI was released on 14 March 2019.

- Hides raw HTML from error outputs. 
- Fixes typos in help text. 
- Updates the help text in various languages.

#### Version 0.2.61
{: #cli-0261}

Version 0.2.61 of the CLI was released on 26 February 2019.

- Adds the `cluster pull-secret apply` command, which creates an IAM service ID for the cluster, policies, API key, and image pull secrets so that containers that run in the `default` Kubernetes namespace can pull images from IBM Cloud Container Registry. For new clusters, image pull secrets that use IAM credentials are created by default. Use this command to update existing clusters or if your cluster has an image pull secret error during creation. For more information, see [the doc](/docs/containers?topic=containers-registry#cluster_registry_auth). 
- Fixes a bug where `ibmcloud ks init` failures caused help output to be printed.

#### Version 0.2.53
{: #cli-0253}

Version 0.2.53 of the CLI was released on 19 February 2019.

- Fixes a bug where the region was ignored for `ibmcloud ks api-key reset`, `ibmcloud ks credential get/set`, and `ibmcloud ks vlan spanning get`. 
- Improves performance for `ibmcloud ks worker update`. 
- Adds the version of the add-on in `ibmcloud ks cluster addon enable` prompts.

#### Version 0.2.44
{: #cli-0244}

Version 0.2.44 of the CLI was released on 8 February 2019.

- Adds `--skip-rbac` option to the `ibmcloud ks cluster config` command to skip adding user Kubernetes RBAC roles based on the {{site.data.keyword.cloud_notm}} IAM service access roles to the cluster configuration. Include this option only if you [manage your own Kubernetes RBAC roles](/docs/containers?topic=containers-users#rbac). If you use [{{site.data.keyword.cloud_notm}} IAM service access roles](/docs/containers?topic=containers-iam-service-access-roles) to manage all your RBAC users, don't include this option. - Updates the Go version to 1.11.5.

#### Version 0.2.40
{: #cli-0240}

Version 0.2.40 of the CLI was released on 6 February 2019.

- Adds the [`ibmcloud ks cluster addon ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addons), [`ibmcloud ks cluster addon enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_enable), and [`ibmcloud ks cluster addon disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_disable) commands for working with managed cluster add-ons such as the [Istio](/docs/containers?topic=containers-istio) managed add-on for {{site.data.keyword.containerlong_notm}}. 
- Improves help text for {{site.data.keyword.Bluemix_dedicated_notm}} users of the `ibmcloud ks vlan ls` command.

#### Version 0.2.30
{: #cli-0230}

Version 0.2.30 of the CLI was released on 31 January 2019.

- Increases the default timeout value for `ibmcloud ks cluster config` to `500s`.

#### Version 0.2.19
{: #cli-0219}

Version 0.2.19 of the CLI was released on 16 January 2019.

- Adds the `IKS_BETA_VERSION` environment variable to enable the redesigned beta version of the {{site.data.keyword.containerlong_notm}} plug-in CLI. To try out the redesigned version, see [Using the beta command structure](/docs/containers?topic=containers-cs_cli_changelog#changelog_beta). 
- Increases the default timeout value for `ibmcloud ks subnets` to `60s`. 
- Fixes a minor bug and updates the help text in various languages.


### Version 0.1
{: #01}

Review the following changes for 0.1 versions of the CLI plug-in.
{: shortdesc}

Version 0.1 of the CLI plug-in is deprecated. To update to the latest version, see [Updating to version 1.0 of the plug-in](#changelog_beta).
{: deprecated}

#### Version 0.1.668
{: #cli-01668}

Version 0.1.68 of the CLI was released on 18  December 2018.

- Changes the default API endpoint from `containers.bluemix.net` to `containers.cloud.ibm.com`. 
- Fixes bug so that command help text and error messages display properly for various languages. 
- Displays command help faster.

#### Version 0.1.654
{: #cli-01654}

Version 0.1.654 of the CLI was released on 5  December 2018.

- Updates the help text in various languages.

#### Version 0.1.638
{: #cli-01638}

Version 0.1.638 of the CLI was released on 15 November 2018.

- Adds the [`ibmcloud ks cluster-refresh`](/docs/containers?topic=containers-kubernetes-service-cli#cs_apiserver_refresh) alias to the `apiserver-refresh` command. 
- Adds the resource group name to the output of `ibmcloud ks cluster get` and `ibmcloud ks cluster ls`.

#### Version 0.1.635
{: #cli-01635}

Version 0.1.635 of the CLI was released on 6 November 2018.

Adds commands for managing automatic updates of the Ingress ALB cluster add-on: 
- [`ibmcloud ks alb autoupdate disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoupdate_disable)
- [`ibmcloud ks alb autoupdate enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoupdate_enable)
- [`ibmcloud ks alb autoupdate get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoupdate_get)
- `ibmcloud ks alb rollback` 
- [`ibmcloud ks alb-update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_update)

#### Version 0.1.621
{: #cli-01621}

Version 0.1.621 of the CLI was released on 30 October 2018.


- Adds the [`ibmcloud ks credential get` command](/docs/containers?topic=containers-kubernetes-service-cli#cs_credential_get). 
- Adds support for the `storage` log source to all cluster logging commands. For more information, see [Understanding cluster and app log forwarding](/docs/containers?topic=containers-health#logging). 
- Adds the `--network` option to the [`ibmcloud ks cluster config` command](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_config), which downloads the Calico configuration file to run all Calico commands. 
- Minor bug fixes and refactoring.

#### Version 0.1.593
{: #cli-01593}

Version 0.1.593 of the CLI was released on 10 October 2018.

- Adds the resource group ID to the output of `ibmcloud ks cluster get`. 
- When [{{site.data.keyword.keymanagementserviceshort}} is enabled](/docs/containers?topic=containers-encryption#keyprotect) as a key management service (KMS) provider in your cluster, adds the KMS enabled field in the output of `ibmcloud ks cluster get`.

#### Version 0.1.591
{: #cli-01591}

Version 0.1.591 of the CLI was released on 2 October 2018.

- Adds support for [resource groups](/docs/containers?topic=containers-clusters&interface=ui).

#### Version 0.1.590
{: #cli-01590}

Version 0.1.590 of the CLI was released on 1 October 2018.


- Adds the [`ibmcloud ks logging collect`](/docs/containers?topic=containers-kubernetes-service-cli) and [`ibmcloud ks logging collect-status`](/docs/containers?topic=containers-kubernetes-service-cli) commands for collecting API server logs in your cluster.
- Adds the [`ibmcloud ks key-protect-enable` command](/docs/containers?topic=containers-kubernetes-service-cli#ks_kms) to enable {{site.data.keyword.keymanagementserviceshort}} as a key management service (KMS) provider in your cluster. 
- Adds the `--skip-master-health` option to the [ibmcloud ks worker reboot](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reboot) and [ibmcloud ks worker reload](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reboot) commands to skip the master health check before initiating the reboot or reload. 
- Renames `Owner Email` to `Owner` in the output of `ibmcloud ks cluster get`.
  
  
