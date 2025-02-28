---

copyright: 
  years: 2014, 2023
lastupdated: "2023-07-24"

keywords: kubernetes, static route, add-on

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}





# Static route add-on change log
{: #versions-static-route}

For deployment steps, see the [managed static route add-on](/docs/containers?topic=containers-static-routes) docs.
{: shortdesc}

For steps on updating the static route add-on, see [Updating managed add-ons](/docs/containers?topic=containers-managed-addons#updating-managed-add-ons).

To view a list of add-ons and the supported cluster versions, run the following command or see the [Supported cluster add-ons table](/docs/containers?topic=containers-supported-cluster-addon-versions).

```sh
ibmcloud ks cluster addon versions
```
{: pre}


## Version 1.0.0
{: #v100}



### Change log for 1.0.0_1122, released 17 July 2023
{: #100_1122}

Adds support for multiple worker node architectures.



### Change log for 1.0.0_649, released 8 September 2021
{: #100_649}

- Uses `apiextensions.k8s.io/v1` instead of `apiextensions.k8s.io/v1beta1`.




