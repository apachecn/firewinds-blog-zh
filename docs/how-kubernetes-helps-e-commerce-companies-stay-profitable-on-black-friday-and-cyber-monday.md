# Kubernetes 如何帮助电子商务公司在黑色星期五和网络星期一保持盈利

> 原文：<https://www.fairwinds.com/blog/how-kubernetes-helps-e-commerce-companies-stay-profitable-on-black-friday-and-cyber-monday>

 对零售和电子商务公司来说，成功运营黑色星期五和网络星期一是一个重大胜利。对于一些企业来说，这一天产生的交易数量相当于一个月或更长时间的销售额。然而恐怖故事比比皆是。去年，由于网站崩溃， [J. Crew 在黑色星期五的销售额中损失了大约 70 万美元](https://www.businessinsider.com/jcrew-website-crashes-on-black-friday-2018-11) 。

幸运的是，云计算使电子商务企业能够通过弹性计算和按需供应基础设施资源来满足需求。在本帖中，我们讨论一些不同的架构和技术考虑，电子商务公司可以追求运行一个有效和可靠的黑色星期五/网络星期一活动。

**微服务架构**

微服务架构为电子商务平台提供了许多好处。通过将应用程序分成更小的部分，开发团队可以逻辑地分割功能——这有助于使开发和测试过程更加高效。从开发的角度来看，团队可以在代码库的不同部分工作，而不会互相影响。例如，产品搜索、产品详情和购物车功能都可以构建为自己的微服务。

从测试的角度来看，微服务强调定义输入和输出。服务通过 API 调用相互交互，为数据和事务如何通过整个系统建立契约。

**集装箱**

容器是打包微服务并使它们准备好部署在任何计算平台或云上的好方法。这种可移植性很重要，尤其是对于可能需要更换云提供商的电子商务公司。这种避免“供应商锁定”的能力非常重要，尤其是当云提供商可能拥有与电子商务公司直接竞争的子公司或相邻企业时。

容器还提供了运行应用程序的一致方式。通过抽象出底层操作系统，开发人员可以避免故障排除，并调试特定于环境或特定于运行时的问题。

最后，容器是不可变的。容器在运行时不会改变；相反，如果它遇到错误或需要更新，就必须删除它，并部署新的容器来替换它。

您可以想象一个场景，在黑色星期五期间，在产品搜索页面上发现了一个 bug。如果功能在自己的微服务和容器中，工程师可以简单地推出一个新的容器版本，修复错误，而不必关闭整个网站，也不必中断数百或数千个有价值的用户会话。

**Kubernetes**

Kubernetes 不仅是事实上的容器编排，也是根据需要扩展和缩减计算资源的有效解决方案。Kubernetes 提供了一些不同的自动扩展功能，允许智能复制容器组(称为 pod)，以及增加和减少运行站点所需的计算实例的数量。

虽然 Kubernetes 自动处理许多后台缩放活动，但掌握这些配置需要一个学习过程。有时，工程团队忽略了提供这些配置，当出现不可预测的流量时，会带来停机风险。

Fairwinds 最近推出了一款新的开源工具，名为[fair winds Goldilocks](https://github.com/FairwindsOps/goldilocks)，帮助工程师设置正确的资源请求和限制。这些设置通知 Kubernetes 所需的 CPU 和内存范围，帮助 Kubernetes 知道何时向外扩展。

**Framebridge，Kubernetes 前后**

为了深入了解，我们采访了世界领先的定制镜架零售商和 Fairwinds 的客户, [Framebridge](https://www.framebridge.com/lp/take15?utm_source=bing&utm_medium=cpc&utm_campaign=Bing_Search_Alpha_Brand&utm_term=Framebridge&matchtype=e&msclkid=db950b7030791434664856ad930827c3&utm_content=Framebridge) 的工程副总裁 Brock Wilcox。

布洛克估计，在黑色星期五和网络星期一期间，网络流量有时会增加两倍。在实施 Kubernetes 之前，团队会通过先发制人的过度供应来解决这个问题，这会使生产成本翻倍。

Brock 注意到的一个关键改进是，他的工程师们能够对应用程序进行改进，为黑色星期五做准备。Framebridge 能够在试运行环境中隔离和测试新功能。不仅部署时间缩短，而且部署完全自动化。如果在部署新功能后出现问题，回滚只需要 60 秒，这样团队就不那么厌恶风险了。

**完全托管的 Kubernetes**

Kubernetes 提供了可靠和高效生产操作的双重优势。对于像黑色星期五这样的活动，电子商务公司保持“盈利”是很重要的。可靠也很重要。两者兼顾需要团队中有合适的专家。

全面管理的 Kubernetes 产品有助于在一个完整的订阅包中提供专业知识、监控、升级和安全补丁。像黑色星期五和网络星期一这样的事件通常意味着“所有人都在甲板上”，这可能会使开发人员远离有价值的路线图功能和创新。同类最佳的完全受管 Kubernetes 解决方案，如[fair winds cluster ops](/clusterops)，集成了 24x7 自动分页，因此您的开发人员无需在凌晨 3 点起床查看基础架构警报。

在选择 Kubernetes 时，您还需要考虑让您的工程师使用正确的开源工具。Fairwinds 提供了一套用于管理 Kubernetes 的开源软件[——帮助您部署、运营和优化您的基础设施，以实现安全性、可靠性和效率。让我们知道你的想法和](/open-source-software)[fair winds 如何帮助你](/how-we-can-help) ！