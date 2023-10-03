---
layout: post
title:  "Introduction to Multi-Tenancy in Kubernetes"
date:   2021-11-15 13:16:52 +0530
categories: Kubernetes, multitenancy
---

## What is multi-tenancy?

The idea of sharing a single instance of an application or of software among various tenants is called multi-tenancy. This approach is quite popular since the rise of cloud environments. Now, with the introduction of Kubernetes, developers and administrators require the same approach to be implemented on Kubernetes clusters. As that would provide better resource utilization, provide better management of underlying compute resources, and reduce cost.

This blog post will discuss various available approaches to introduce multi-tenancy in Kubernetes clusters and will try to draw a comparison between all of them.

## Where multi-tenancy serves better?

Before even discussing multi-tenant architecture, one should know whether it is better to deploy a single [Kubernetes](/kubernetes-consulting-partner/) cluster with multi-tenant support or should deploy multiple clusters, different for each tenant. 

To begin with, there is no specific rule for this and most organizations decide this on the basis of ease of use, management etc. Deploying multiple clusters is simple as you don’t have to worry about following additional best practices such as auditing [RBAC](/blogs/role-based-access-kubernetes/), setting up standard practice for users. Besides this, cost also plays an important role while making this decision. If cost is not an issue and you want simple architecture, deploy multiple clusters. Whereas, if your compute need is far less and you want to save some extra cost, multi-tenancy could be a better option. Some other factors also play a vital role such as the lifecycle of your cluster, if your need is only temporary, multi-cluster could be a viable option, as you don’t have to install anything else on your cluster. 

One major drawback of having multiple clusters is the increased management overhead, specially for the large environments, it requires a lot of effort to keep every cluster updated, more [security audits](/blogs/kubernetes-auditing/) would be required as well. It is worth noting that while you may use a multi-cluster approach, you shouldn’t block future expansion around the multi-tenancy by making some little mistakes like deploying all applications in the same namespace.

## Different approaches of multi-tenant architecture

Multi-tenancy in Kubernetes can be categorized in two broad terms:

1. **Soft Isolation:** In this, we have a single enterprise with different teams accessing the same cluster, this requires less amount of security overhead as users can trust each other.  
2. **Hard isolation:** This is required where the Kubernetes is exposed to multiple enterprises with independent and completely untrusted users.

There are various approaches discussed in [KubeCon Europe 2019](https://static.sched.com/hosted_files/kccnceu19/74/kubecon-eu-multitenancy-wg-deepdive.pdf) wherein every approach can be enlisted in either of the two mentioned above categories.



![Image description](../assets/images/y0vei8bhhfcjhdhetrj9.png)
[Image Credits](https://static.sched.com/hosted_files/kccnceu19/74/kubecon-eu-multitenancy-wg-deepdive.pdf)

The above-shown diagram outlines 4 different approaches to consume Kubernetes clusters in your environment.

1. **Approach A** 
This doesn’t provide an exact multi-tenant solution as it deploys different Kubernetes clusters. However, can be still considered as in this solution each tenant will receive a different Kubernetes cluster, which is completely isolated from any other compute resource. This can be implemented by using segregated VM providers like Amazon EC2, GCP compute instance, and vSphere VM’s. 

2. **Approach B** 
This is one of the popular architecture, wherein segregation is based on namespaces. This provides soft isolation among different tenants. With this, tenants can only see, modify, and create objects within their namespace. Moreover, they can create policies for security and roles within their namespace. There are two major drawbacks in this approach, the principal one is shared master components like API server and the other one is the provisioning of Cluster scoped resources. The main work carried out for the development of this approach is done by Project HNC (hierarchical namespaces).

3. **Approach C** 
This approach provides a way to implement hard isolation among Kubernetes tenants who have no trust between them. This provides segregated master plane components for each tenant by creating a mini virtual cluster on the super Kubernetes cluster. Admins can also create custom resources in those virtual clusters as well. This is provided by projects like [VirtualCluster](https://github.com/kubernetes-sigs/cluster-api-provider-nested/tree/main/virtualcluster) and [vCluster](https://github.com/loft-sh/vcluster). 

4. **Approach D** 
Different from all of the above approaches, this suggests that Kubernetes should provide the support for creating tenants out of the box. It is not yet developed, because of the efforts that it would require to modify the Kubernetes source code. 

## Comparison of various solutions

||VM based Segregation|Namespace based Segregation|Virtual Clusters|
|-|-|-|-|
|Isolation|Hard|Soft|Hard|
|Effective Resource Consumption|Less|High|High|
|Tenants can use all Native Kubernetes objects|Yes|No. Cluster scoped resources can’t be used|No. Resources that require underlying node information like DaemonSets can't be used|
|Availability|Ready|Still waiting for General Availability but production-ready. |Some solutions are available like vCluster but some are still waiting for General Availability like VirtualCluster|
|Additional overhead on Kubernetes|None|Very Little |Little to medium as it spins up a new control plane for each mini cluster. |

## Some use-cases for multi-tenancy in Kubernetes

1. **SaaS Applications**

   Implementation of multi-tenancy can enable organizations to centrally manage the infrastructure for their multiple customers. This makes it easy for SaaS organizations to manage their infrastructure shared among different tenants.

2. **Better Resource Utilization**

   Fewer clusters will be needed as multiple teams can share a single cluster. Thus, utilizing cluster resources more efficiently. 

## Conclusion

To conclude, multi-tenancy is an important aspect of Kubernetes which does not come out of the box, but can be implemented via various strategies. It can extend the usability of Kubernetes, helps to achieve better resource utilization, can save billing costs, and can also be important for the cluster administrators for managing various microservices in an efficient manner.

That's it folks. Hope you found this article helpful for getting started with multi-tenancy in Kubernetes. Do ask your queries and share your experience via [Twitter](https://twitter.com/_DeepankurSingh).

## References 
1. [Slide Deck: Deep Dive: Kubernetes WG for Multitenancy - KubeCon EU 2019](https://static.sched.com/hosted_files/kccnceu19/74/kubecon-eu-multitenancy-wg-deepdive.pdf)
2. [Deep Dive: Kubernetes WG for Multitenancy - KubeCon EU 2019](https://www.youtube.com/watch?v=SUW54Wlx6Po)
3. [Project HNC](https://github.com/kubernetes-sigs/hierarchical-namespaces)
4. [Project VirtualCLuster](https://github.com/kubernetes-sigs/cluster-api-provider-nested/tree/main/virtualcluster)
5. [VirtualCLuster Framework](https://github.com/kubernetes-sigs/cluster-api-provider-nested/blob/main/virtualcluster/doc/vc-icdcs.pdf)

<a href= "https://www.infracloud.io/blogs/multi-tenancy-kubernetes/">This blog was originally posted here.</a> 