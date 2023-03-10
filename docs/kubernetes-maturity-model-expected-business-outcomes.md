# Kubernetes 成熟度模型:预期业务成果

> 原文：<https://www.fairwinds.com/blog/kubernetes-maturity-model-expected-business-outcomes>

 当你搬到 Kubernetes，你必须显示出明确的业务优势。随着时间的推移，预期的业务成果将包括成本节约，因为您可以更好地利用基础架构，通过减少故障点和提高安全性来提高性能。

效率、可靠性和安全性优势可以通过许多不同的方式实现。考虑效率:你的团队可能会更快地发布特性，或者你会停止在过度配置的资源上浪费金钱。你的可靠性可能会提高，因为你可以更容易地扩展-所以当你的应用程序看到强大的需求，没有停机时间。当然，这一切都是以 [了解您的集群配置](//www.fairwinds.com/insights) 为代价的。

几个月前我们发表了 Kubernetes 成熟度模型[](https://www.fairwinds.com/kubernetes-maturity-model)。由七个阶段组成，每个阶段都着眼于工程师在从 Kubernetes 准备到优化的过程中应该期待什么。

在这里，我们专门讨论你应该期待什么样的业务成果。虽然在几个阶段可能会重复，但在第一阶段花足够的时间概述云原生、容器和 Kubernetes 采用的目标和优势是很重要的。

## **第一阶段:准备**

决定对您的应用或服务采用云原生方法通常是由业务原因驱动的。在第 1 阶段，您的业务成果将是有限的，但绝对必须包括为成功设置试验或迁移。这意味着你应该有文件证明你的商业目标是什么，以及 Kubernetes 如何帮助你实现这些目标。一些例子可能包括:

| **业务目标** | 【Kubernetes 如何帮助 |
| 扩展到 100 万用户 | 在任何给定时间提供基于用户的灵活、可扩展的基础架构，并在出现问题时配备快速故障切换功能。 |
| 提供卓越的客户体验 | 确保应用程序是可靠的，不会让用户感到沮丧 |
| 更快地将功能推向市场 | 添加启用微服务方法来构建应用程序。较小的团队更敏捷，因为每个团队都有一个专注的功能。API 最大限度地减少了构建和部署所需的跨团队交流 |

## **阶段 2:转换**

Kubernetes 成熟的第二阶段主要集中在技术改造上。但是，在此阶段，您的技术团队应该已经完成了一次成功的概念验证。基于那次试验，你应该对 Kubernetes 如何帮助改进你的应用有了一些初步的发现。例如，在开发环境中，您可能会看到:

*   应用程序使用更少的资源(节省成本)

*   更快推出新功能(更快上市，从而增加收入)

*   没有停机时间(提高了客户的可靠性)

| **业务目标** | 【Kubernetes 如何帮助 |
| 无线一键通 | 你应该有一些关于 Kubernetes 如何帮助的初步发现 |

## **第三阶段:部署**

一旦您的开发团队将一个应用程序部署到生产环境中，业务成果应该开始显现。你应该使用你记录的业务目标来跟踪 Kubernetes 的进展，但是记住它不会在第一天就立即实现。业务成果可能包括:

*   减少在应用基础设施上的支出

*   减少团队对应用基础设施的关注(注意:随着团队对他们的技能越来越有信心，这将在这个阶段随着时间的推移而发生)

*   提高了应用程序的安全性

*   提高合规性，因为您可以限制和跟踪对应用程序的访问

*   加速开发生命周期，因为您实现了 CI/CD 管道，从而更快地向客户提供特性

在这个阶段，检查业务成果并向业务涉众解释是很重要的。这应该是与工程领导、应用程序所有者(财务、营销等)、CEO 甚至董事会的讨论。没有这些讨论和协调，下一个阶段的成熟将会很少被欣赏，甚至可能被怀疑。

| **业务目标** | 【Kubernetes 如何帮助 |
| 减少在应用基础设施上的支出 | 提高资源利用率 |
| 减少团队对应用基础设施的关注 | 快速故障转移 |
| 增强安全性 | 通过限制、RBAC、Kubernetes 秘密和加密降低 DDoS 影响 |
| 提高合规性 | 访问控制 |
| 船舶功能更快(加速开发生命周期) | 滚动更新 |

## **第四阶段:树立信心**

建立对 Kubernetes 的信心需要经验。在这个阶段，你的业务成果取决于你的团队的经验。他们将尝试新的附加功能来提高安全性、效率和可靠性。随着团队的改进，所有这些都会影响您的服务和应用程序。

随着 Kubernetes 的推出，您的团队可能需要重新考虑之前做出的一些决定。这可能会让您稍有退步，但目标是确保没有功能缺失、没有单点故障或令人失望的性能。

在第四阶段，将实施监测。这将有助于企业获得关于哪些有效、哪些无效的报告。虽然监测可能非常具体，但它也将提供以下方面的见解:

获得对您的 Kubernetes 基础设施是生产级的信心是至关重要的。如果你对自己的进展不确定，Kubernetes 的[](https://www.fairwinds.com/kubernetes-audit-improve)审计是对照你的业务目标检查你的成就的好方法，这样你就可以改进。

| **业务目标** | 【Kubernetes 如何帮助 |
| 目标签到 | 根据业务目标实施监控 |

**第五阶段:改善运营**

Kubernetes 成熟度模型的第五阶段是您应该期望在安全性、效率和可靠性方面获得巨大收益的阶段。到目前为止，你们的团队一直专注于学习 Kubernetes。现在是时候利用这些知识，并将其更彻底地应用到您的业务目标中了。

*   安全性——如果你的主要目标是提高安全性，那么你将在访问控制上花费时间。

*   效率——如果降低成本是你的主要目标，在这里你将放置 [工具来测量 CPU 和内存使用](https://www.fairwinds.com/blog/kubernetes-best-practice-efficient-resource-utilization) ，并记录云使用是如何增加或减少的。在这里，你应该能够证明为你的基线测量提供资金。

*   可靠性——如果提高性能/减少停机时间是主要目标，在这里您将检查 Kubernetes 的所有功能是否都已实现。您将花时间学习集群配置来解决这个问题。

| **业务目标** | 【Kubernetes 如何帮助 |
| 安全性 | 围绕容器配置(根)、权限等实施控制。 |
| 效率 | 测量 CPU 和内存使用情况 |
| 可靠性 | 活性/就绪性探测、复制 |

## **第六阶段:测量&控制**

进入第六阶段将会看到对你所做的更多的衡量。这很重要，因为它将用于展示业务成果。企业应该期望看到:

*   在 Kubernetes 建立协议和程序

*   合规标准的策略实施

*   基于 Kubernetes 与非基于 Kubernetes 的应用对比

在这一阶段，企业应该会收到更多的报告。报告应涵盖合规性、安全性、性能和成本。一个 [单一仪表板视图](//www.fairwinds.com/insights) 进入您的集群可以帮助技术和业务领导看到进展。这些应该很容易与第一阶段建立的业务目标保持一致。

| **业务目标** | 【Kubernetes 如何帮助 |
| 根据指标增加报告 | 在这个阶段，你可能需要第三方工具[](//www.fairwinds.com/insights) |
| 基于 K8S 和非 K8S 的应用对比 | 比较将有助于展示价值，显示是否应该迁移所有或哪些应用程序 |

## **第 7 阶段:优化&自动化**

到 Kubernetes 成熟度模型的最后阶段，您应该已经取得了业务成果。你应该有可衡量的结果来展示你的领导团队，从首席执行官到首席财务官和董事会。

与此同时，第七阶段会看到你做进一步的改进。这包括根据更高级的成本和性能指标优化您的 Kubernetes 工作负载。您将永远不会停止优化您的 Kubernetes 集群。在这里，预期的业务成果是跟踪优化如何继续朝着既定目标前进的能力。

你也可以在这一点上重新审视你的目标，根据已经实现的目标和你未来想要实现的目标进行调整。对于一些人来说，在这一点上，您可能开始迁移您的其他应用程序，并对您想要实现的目标有了更好的理解。

同样在第 7 阶段，您将根据 Kubernetes 的最佳实践尽可能多地实现自动化，以消除人为错误，从而避免安全性和性能问题。这种自动化将包括针对您的集群配置实施策略实施。 [策略执行](https://www.fairwinds.com/blog/why-kubernetes-policy-enforcement) 在成熟的每个阶段都应该考虑，但肯定是在阶段 7。成熟的 Kubernetes 用户知道，错误的配置会导致组织完全偏离他们的业务目标——使他们面临安全漏洞的风险，扩展问题和成本超支。

| **业务目标** | 【Kubernetes 如何帮助 |
| 实现业务目标 | 实现 Kubernetes 成熟度的显著成果 |
| 自动化 | 减少人为错误 |
| 最佳化 | 您将调整 Kubernetes 以继续实现业务目标 |

| **业务目标** | 【Kubernetes 如何帮助 |
| 实现业务目标 | 实现 Kubernetes 成熟度的显著成果 |
| 减少人为错误 | 自动化 |
| 持续改进 | 优化，因为你将调整 Kubernetes 继续实现业务目标 |

## **Kubernetes 成熟度模型**

成熟度模型应该用于检查您的技术和业务成果。如果你不确定你是否在每个阶段都取得了进展，或者不知道你的确切位置，请联系我们。我们很高兴在贵公司讨论 Kubernetes。

[![Use Fairwinds Insights for Free Security, Cost and Developer Enablement In One](img/7c86296320eb01b215d8e2755e9c5b9d.png)](https://cta-redirect.hubspot.com/cta/redirect/2184645/34aa4987-a1f9-438a-a145-d7d82d5c479a)