# Kubernetes 配置验证:了解为什么它不是一个和完成

> 原文：<https://www.fairwinds.com/blog/kubernetes-configuration-validation>

 如果您在生产中使用 Kubernetes，那么验证每个工作负载的配置是至关重要的。最小的变化或遗漏都可能导致停机、成本超支，甚至更糟的是安全漏洞。那么，对于 Kubernetes 配置验证，您需要寻找什么呢？

具体来说，您至少应该检查*:*

*   针对 [**安全**](/kubernetes-security) 问题，包括超权限容器和常见漏洞与暴露(CVEs)
*   对于 [**效率**](/blog/3-kubernetes-efficiency-mistakes) 问题，如未设置 CPU 限制或请求过多内存
*   对于[](/blog/6-kubernetes-reliability-mistakes)**可靠性问题，例如，不设置活跃度和就绪度探针**

 **但是在进行代码审查时仅仅寻找这些东西是不够的——您应该在部署生命周期的每一步自动检查它们。如果没有一个完整的程序来验证 Kubernetes 的配置，错误肯定会被遗漏。

要保持集群健康，您需要确保检查配置:

*   在针对每个拉取请求和合并运行的 CI 流程中
*   在接纳时，随着新资源进入集群
*   作为对集群内资源的连续扫描

## 步骤 1 -通过 CI 保持健康

如果您的公司已经实施了一个成熟的 DevOps 计划，那么您将把所有的配置存储为代码形式的基础架构(IaC)。所以对你的基础设施的每一个改变都(理想地)在 Git 中被跟踪，并且通过一个代码审查过程。

代码审查是捕捉高层次问题的好方法，比如实际上不会实现业务目标的变更，或者会引入微妙的安全问题的变更。但是有很多常见的问题，查找起来很繁琐，而且很容易被忽略，比如错误配置的安全设置或缺少健康探测。

在 CI 中拥有自动化验证是补充代码审查并确保新的变更坚持一致的质量水平的一个很好的方式。通过自动完成代码审查人员的大部分死记硬背的任务，您给了他们挖掘逻辑和深入思考其影响的空间。

## 步骤 2 -集群的保镖

一旦拉请求(PR)被批准并且测试通过，您就可以安全地部署了。但是，如果部署做的事情与 CI 中测试的略有不同，该怎么办呢？或者更糟糕的是，如果有人通过强制推送到 Git，或者通过直接与您的 Kubernetes 集群交互，从而绕过了审查过程，该怎么办？

添加一个[准入控制器](https://kubernetes.io/docs/reference/access-authn-authz/admission-controllers/)是保持集群健康的重要保障。它就像是集群前门的保镖，任何不遵守策略的东西都进不去。

通常，组织会将其准入控制器配置为没有 CI 严格，以便在审查过程中可以对非关键规则进行例外处理。相反，它们只会在准入控制器中实施最严格的策略。

在完美的世界中，问题总是在开发周期的早期被发现，在它们被发送到 Kubernetes API 之前。但是即使是最严密的 DevOps 程序也有漏洞，准入控制器可以堵住。

## 步骤 3 -当好的工作负载变坏时

所以您的工作负载通过了 CI 流程，准入控制器也让它通过了。您的应用正在生产中运行，每个人都很高兴。你应该完成了，对吗？

不完全是。在一些情况下，以前健康的部署可能会开始恶化:

*   **随着时间的推移，工作负载可能会发生微妙的变化**。例如，如果您正在使用一个可变的 image 标记，那么您的工作负载所使用的 docker 映像可能会得到更新，而不会对您的 IaC 存储库或准入控制器进行任何更改。或者像 [VerticalPodAutoscaler](https://www.civo.com/learn/fairwinds-goldilocks-kubernetes-resource-recommendation-tool) 这样的 Kubernetes 控制器可能会改变它的配置。
*   **每天都有新的漏洞(CVE)公布**。在进入群集之前被认为是健康的映像现在可能存在已知的可利用漏洞。
*   随着你的成长和成熟，你的团队将采用新的政策。这些策略需要应用于[现有的工作负载以及新的工作负载](/enforce-kubernetes-policy)。

扫描 Kubernetes 环境中已经存在的资源是确保集群长期健康的重要一步。这是您最真实地了解群集的运行状况、安全状况和策略合规性的方式。

## Kubernetes 充满信心

安装这种护栏可能看起来像是一件苦差事，或者是对生产力的一种风险。我们都知道我们的工作被过分热心的 CI 系统或安全政策拒绝的痛苦。

但是当你知道你不会弄坏东西的时候，快速移动会容易得多。改变 Kubernetes 集群中的资源是很可怕的，简单的错误会导致用户愤怒、收入损失和声誉受损。合适的护栏将帮助您自信地运输，平静地睡觉。

## 费尔温德见解

如果您正在寻求在整个 Kubernetes 生命周期中实现策略和最佳实践的帮助，请联系我们！ [Fairwinds Insights](/insights) 可以帮助您在 CI、准入控制和实时扫描方面运行 Kubernetes 的最佳开源验证工具。

Fairwinds Insights 可供免费使用。你可以在这里报名。

[![Use Fairwinds Insights for Free Security, Cost and Developer Enablement In One](img/7c86296320eb01b215d8e2755e9c5b9d.png)](https://cta-redirect.hubspot.com/cta/redirect/2184645/34aa4987-a1f9-438a-a145-d7d82d5c479a)**