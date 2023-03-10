# Kubernetes 的一份概述称，正确的配置是省钱的关键

> 原文：<https://www.fairwinds.com/blog/a-kubernetes-overview-says-proper-configuration-is-key-to-saving-money>

 在我们最近的白皮书《优化 Kubernetes 所有权的 5 种方法》中，我们讨论了与强大的服务所有权模型相关的众多好处。除了授权开发人员对其应用的质量负责，Kubernetes 服务所有权模型还优化了业务成功的五个关键因素，包括[安全性](https://www.fairwinds.com/blog/may-the-fair-winds-of-better-k8s-service-ownership-blow-you-safely-home)、[合规性](https://www.fairwinds.com/blog/compliance)、可靠性、可扩展性，当然还有成本优化。

当你停下来考虑 Kubernetes 服务所有权如何影响整体成本管理时，你必须考虑配置。它们之间有着千丝万缕的联系，因为 Kubernetes 的正确配置在组织花费的金额中起着重要作用。错误配置会导致额外的、完全可以避免的成本。这就是为什么服务所有者在建立资源分配之前必须了解应用程序的最终成本。然后他们必须确定金额是否符合他们的预算。

阅读我们最新的白皮书:

[优化 Kubernetes 所有权的 5 种方法](/benefits-kubernetes-service-ownership)

## 分配成本

那么，Kubernetes 工作负载的实际成本是多少？答案不是特别简单。事实上，这可能非常困难，因为节点(您最终为其付费的对象)并不完全对应于您运行它们的工作负载。

首先，节点是短暂的，可以随着集群规模的扩大和缩小而创建和销毁，也可以在升级或出现故障时更换。为了增加复杂性，Kubernetes bin 根据它认为最有效地利用这些资源的方式将工作负载打包到节点中，就像俄罗斯方块游戏一样。因此，将特定的工作负载映射到特定的计算实例仍然具有挑战性。Kubernetes 中的高效 bin 打包是一个很好的成本节约方法，但是当一个给定节点上的资源被许多应用程序共享时，很难找到一个好的方法来分配成本。

## 合理调整资源

当团队将他们的应用程序部署到 Kubernetes 时，他们负责精确地设置应该为他们的应用程序分配多少内存和 CPU。这是经常出错的地方——团队要么没有指定这些设置，要么将它们设置得太高。

开发人员的工作是编写代码并快速发布，所以当他们面对可选的配置时——比如 CPU 和内存请求和限制——他们通常会简单地忽略它。这可能会导致可靠性问题，包括延迟增加甚至停机。此外，即使他们花时间指定内存和 CPU 设置，他们也倾向于分配过多的数量，因为他们知道自己的应用程序在有额外资源的情况下也能正常运行。从开发人员的角度来看，计算越多越好。

如果没有 Kubernetes 的成本控制和可见性，以及将这些信息提供给开发团队的可靠的反馈回路，Kubernetes 将只是尊重开发人员的 CPU 和内存设置，您会发现自己面临着一大笔云计算账单。尽管 Kubernetes 会通过以优化资源的方式将所有工作负载放在一起，尽最大努力与所有工作负载“玩俄罗斯方块”，但当团队不告诉它需要多少内存和 CPU，或者要求太多时，它只能做这么多。就像打败俄罗斯方块游戏一样，你需要做出明智的、充分知情的选择才能获胜。

### 看腻了？

观看我们的网络研讨会，了解 Kubernetes 中最常见的错误配置以及如何避免它们！

## 解决过去的问题

在 Kubernetes 之前，组织可以依靠云成本工具来提供对底层云基础架构的可见性。如今，Kubernetes 提供了一个新的云资源管理层，几乎就像传统云成本监控工具的一个黑匣子。因此，组织需要在 Kubernetes 的“引擎盖”下找到一种方法，在应用程序、产品和团队之间进行适当的成本分配。

云资源的这种清晰程度，通常是通过成本监控解决方案发现的，允许团队围绕 Kubernetes 所有权的财务做出更好的决策。没有它，组织很难在 Kubernetes 这样的动态环境中优化计算和工作负载。当试图做出明智的实时业务决策时，多个团队、多个集群和大量的复杂性会转化为大量的信息来审查和评估。

## 授权团队

采用服务所有权模型的组织使开发团队能够在生产中拥有和运行他们的应用程序，从而使 Ops 能够专注于构建一个出色的平台。这种转变要求团队在继续实施最佳实践时做出有效的决策。Kubernetes 服务所有权通过自动化、警报、主动建议和工具链集成等方式直接向工程团队提供必要的反馈，从而有助于提高效率和可靠性。

> 寻找一个完整的 Kubernetes 治理平台？Fairwinds Insights 是免费的。今天就开始吧。

这不仅仅是提高运输速度和降低风险。优化 Kubernetes 配置，使集群具有正确的 CPU 和内存请求和限制，有助于确保应用程序高效运行和扩展，从而避免资金浪费。

当团队可以构建、部署和运行他们的应用程序和服务时，他们拥有更大的自主权，与其他团队的交接更少。服务所有权带来的完整体验有助于开发团队更深入地理解他们编写的软件的客户影响和操作开销。服务所有权极大地改善了成本管理和协作，同时也降低了运行 Kubernetes 的复杂性。

[![Use Fairwinds Insights for Free Security, Cost and Developer Enablement In One](img/7c86296320eb01b215d8e2755e9c5b9d.png)](https://cta-redirect.hubspot.com/cta/redirect/2184645/34aa4987-a1f9-438a-a145-d7d82d5c479a)