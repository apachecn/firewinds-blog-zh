# 容器编排要点

> 原文：<https://www.fairwinds.com/blog/container-orchestration-essentials>

 因此，您认为 Kubernetes 作为一个容器编排系统是您的应用程序的正确选择。祝贺和欢迎。你做出了正确的决定，加入了许多成功公司的行列，拥有令人印象深刻的应用程序。

您可能知道，容器编排很难。有无数的变量，不同的配置参数和每月的漏洞，这不是在公园散步。一些公司甚至最终陷入了云原生状态，从未真正发布过应用程序。但那不会是你。你来对地方了。

以下是实现 Kubernetes 容器编排系统的一些要点:

## **集装箱化**

你要做的第一件事是确保你的每个应用程序都有一个 Docker 映像。这将使您的代码具有高度的可移植性。如果您有无状态的应用程序，将它们封装在 Docker 映像中应该不会太难。但是，如果您的应用程序跟踪内存或磁盘上的长期状态，您可能需要重新架构。这是困难的部分；将应用程序状态与应用程序逻辑分离开来。

然而，Kubernetes 的供应商可以提供帮助。(有一个专家团队在你这边也无妨。)

## **定义架构和规则**

接下来，您需要设置您的编排架构。这也将是困难的，因为你将不得不盲目地做出一些决定。在这里，您当然应该从经过实战检验的堆栈开始，而不是尝试实施定制的解决方案。请记住，您正在开始走向成功的容器编排之路——您将想要为此进行规划。

您应该为以下方面准备一个策略:

*   进入
*   证书管理
*   网络策略
*   RBAC
*   监控和警报
*   部署
*   版本和更新

这样，当变量出现时，你就准备好了。

既然您已经将应用程序容器化并部署了集群，那么您将需要定义您的编排规则。这些规则应指定 CPU 和内存要求、入口规则和扩展策略。这应该让您为横向扩展和外部访问集群等变量做好准备。此外，您需要指定访问机密和环境变量的规则。所有这些都可以在 Kubernetes 的 YAML 文件中完成，但你也会想看看[舵图](https://helm.sh/)。

## **部署应用程序**

接下来，您需要一个部署应用程序的过程。您应该设置一个通过 CD 管道自动部署的策略(每当有人在 GitHub 中标记一个分支时)。最初，每当您想要进行更改时，让运营工程师进行手动部署可能没什么问题，但是随着时间的推移，策略将被证明是值得的。

为了确保一切都很好地啮合并一起工作，您将需要一个容器注册中心来保存容器映像，一个 CI 管道来测试、构建和推送映像，以及一个 CD 过程来将它们部署到您的集群。

## **监控一切**

最后，您需要监控您的应用程序。您的集群是一个不断变化的环境，这意味着您需要密切关注它以确保其健康。设置像 Prometheus 和 Datadog 这样的通知，让您知道您的应用程序是否有伸缩性问题或出现故障。但是，请注意，这些通知需要自己的规则，否则它们会在半夜把你吵醒。这里需要注意的是，Kubernetes 的供应商，比如 Fairwinds，可以为您处理这种监控[(以及更多)](https://www.fairwinds.com/how-we-can-help)。

要了解关于容器编排的更多信息，请查看如何在 Kubernetes 中创建、查看和销毁 Pod。

[![Use Fairwinds Insights for Free Security, Cost and Developer Enablement In One](img/7c86296320eb01b215d8e2755e9c5b9d.png)](https://cta-redirect.hubspot.com/cta/redirect/2184645/34aa4987-a1f9-438a-a145-d7d82d5c479a)