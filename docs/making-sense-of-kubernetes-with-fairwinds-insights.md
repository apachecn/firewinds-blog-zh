# 利用 Fairwinds Insights 了解 Kubernetes

> 原文：<https://www.fairwinds.com/blog/making-sense-of-kubernetes-with-fairwinds-insights>

 当我开始与 Kubernetes 合作时，我认为这是一个相当简单的转变。我在 AWS 工作了很多年，在那之前我也在 Linux 上工作了很多年。我知道如何构建容器、配置虚拟机、联网、管理内存和 CPU，以及在云中运行工作负载所需的一切。在谷歌，我甚至与 Kubernetes 的前任博格共事过。学习另一个计算框架有多难？

事实证明，非常困难。尽管我已经在一家专门从事 Kubernetes 支持的公司工作了一年多，但我仍然每天都在学习。Kubernetes 不仅仅是一种新的语法——它是一种全新的思考分布式计算的方式。

到目前为止，最困难的是生态系统的深度。核心项目有超过 200 万行代码，并附带了[大量文档](https://kubernetes.io/docs/home/)。再加上几十个 SIG 和数百个第三方插件，既有开源的也有专有的，很容易让人不知所措。

这种复杂性使得 Kubernetes 成为一个非常强大和灵活的计算管理平台，这也是为什么超过一半的财富 500 强企业采用了它。但是随着建立一个集群的方法的爆炸式增长，错误几乎是不可避免的。保持 Kubernetes 集群的安全性、高效性和可靠性需要大量的知识和经验。

社区已经建立了一些令人惊讶的开源工具来审计 Kubernetes 基础设施，这有可能极大地缓解这些问题。但是审计生态系统是复杂的、支离破碎的，并且是不断变化的。因此，我们在一套开源审计工具的基础上构建了一个抽象层, [Fairwinds Insights](/insights) 。Fairwinds Insights 帮助组织轻松了解他们做得对的地方，以及他们需要关注的地方。

## **一个庞大的开源生态系统**

我很幸运能在老兵面前了解到 Kubernetes。我们有一个出色的 sre 团队，他们已经为几十个组织管理了数百个集群。他们已经看到 Kubernetes 在各种可能的情况下出错，我非常幸运能够从他们的经验中学习，而不是从我自己的错误中学习(尽管也有很多这样的错误！)

甚至在我到达之前，他们已经开始组装一个名为 Polaris 的开源仪表板，用来扫描 Kubernetes 的工作负载，查找常见的配置错误。它检查从安全性(比如以 root 用户身份运行容器)、效率(比如不请求特定数量的内存/CPU)到可靠性(比如无法设置活性和就绪性探测)的各种问题。如果没有像 Polaris 这样的项目来告诉我我错过了什么，我在将工作负载部署到 Kubernetes 时可能需要更多的指导。

该团队还指出，开源社区已经建立了几十个类似的工具。集装箱扫描有[繁琐](https://github.com/aquasecurity/trivy)； [kube-bench](https://github.com/aquasecurity/kube-bench/) 用于测试您与 [CIS 基准](https://www.cisecurity.org/cis-benchmarks/)的对准情况；或者我们自己的 [Goldilocks](https://github.com/FairwindsOps/goldilocks/) 来调整 CPU 和内存设置。我们最终仅编目了 30 多种开源安全工具！

外界审计工具的数量和种类之多很快就让人应接不暇。这些工具有些运行在集群中，有些运行在本地机器上。其中一些查看正在运行的工作负载，另一些查看上游的 YAML 文件。它们都不能跨多个集群核对数据，随着时间的推移跟踪结果，或者在新问题出现时发出警报。它们都有不同的输出格式，用不同的方式表示严重性和工作负载身份。

我们无法继续手动运行所有这些审核，从这些审核中寻找新的发现，并手动创建票证。我们需要一种方法来操作所有这些数据。

## 构建解决方案

为了让我们的生活——以及我们的客户的生活——更轻松，我们创建了一个基于插件的系统来整理和跟踪审计数据。这包括四个主要部分:

*   后端存储
*   翻译层
*   集群内代理
*   图形用户界面仪表板

### 后端

首先，我们构建了一些公共基础设施——即 JSON 存储和 PostgreSQL 数据库——任何报告工具都可以链接到其中。每个单独报告的输出在 S3 保存为 JSON，更多的结构化数据被提取并存储在数据库中。

我们数据库模式的核心是一个被称为[行动项目](https://insights.docs.fairwinds.com/features/action-items)的概念——由任何审计生成的发现——它捕获安全性、效率或可靠性的潜在问题。

### 翻译层

在此基础上，我们构建了一个瘦翻译层:基本上，一些 Go 代码将每个报告的独特输出转换成行动项目。在这里，我们提取资源名称、严重性级别、人类可读的描述和补救建议。其中一些包含在基础报告中，而一些我们需要用自己的知识和研究来补充。

翻译层是代码库中最难维护的部分，因为每当报告添加新功能或更改其输出结构时，都需要对其进行更新。但是它非常有价值。他们可以利用洞察力以一种格式自动查看所有审计数据，而不是每个组织都试图在许多不同的审计工具上构建自己的抽象。

### **代理人**

接下来，我们构建了一个代理来运行每一个开源审计——目前总共有 9 个——并将结果发送回我们的服务器，在那里它们被转换成操作项。这些报告都按照可配置的时间表运行，通常每小时一次，因此我们始终可以了解集群内部的最新情况。当某个问题得到解决时，我们也会选择它，并且可以自动关闭相应的行动项。

这比典型的方法要简单和健壮得多，典型的方法是在特定的基础上手动运行每个工具，而不参考以前的运行。

### 仪表板

最后，我们在[insights.fairwinds.com](https://insights.fairwinds.com/auth/login)建立了一个用户界面，用户可以登录并查看他们的结果。我们有一个用于查看所有行动项目的单一表格，以及一些用于深入研究单个报告的定制界面。这使得我们的用户可以享受两个世界的精华——他们可以看到统一格式的所有内容，或者进入一个专为他们当前工作定制的视图。

## **作用于数据**

现在我们把所有的数据都放在一个地方，我们可以做很多令人惊奇的事情！

我们做的第一件事是建立一些基本的跟踪。我们希望能够将行动项分配给特定的人，并查看行动项何时被发现或修复。还有一些误报(例如，kube 系统工作负载确实需要 root 访问权限)，我们开始将其标记为“不会修复”或“按预期工作”。

更好的是，我们开始将标准化的数据推到我们花费时间的不同地方。我们已经将它链接到 Datadog，因此团队可以跟踪一段时间的趋势，并在资源使用和正常运行时间等核心指标上覆盖行动项目事件。我们已经开始向 Slack 发送警报——包括实时的和每日摘要的，以确保团队对任何意想不到的变化保持警惕。沿着这条线，我们正在研究 GitHub 和吉拉的集成，以确保适当的团队能够修复他们引入的任何问题。

不过，我最感兴趣的是 CI/CD 集成。目前，我们的代理只是查看集群中已经存在的内容——但是，如果我们能够在问题合并到主代理之前就检测到它们，会怎么样呢？只有部分报告能够在 CI 环境中运行，但是能够阻止引入新漏洞的 PR，或者将操作项追溯到特定的基础架构代码文件，将会节省我们大量的时间、痛苦，最重要的是，降低风险。

## 你验证 Kubernetes 配置的策略是什么？

如果您已经在审计您的 Kubernetes 基础设施的安全性、效率和可靠性问题，我们很想听听您正在使用什么工具以及您最关心的问题在哪里。我们正在积极寻求对 Fairwinds Insights 的反馈，它是免费的！[拿到这里。](/coming-soon)

[![Managing Kubernetes Configuration Read the Whitepaper](img/34937a5ae51bc0ceb94a21b3fd2382d0.png)](https://cta-redirect.hubspot.com/cta/redirect/2184645/1ccd0525-c794-4194-8aad-fc9663bb9c5a)