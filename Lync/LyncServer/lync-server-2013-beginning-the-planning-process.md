---
title: Lync Server 2013：开始规划过程
TOCTitle: 开始规划过程
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398986(v=OCS.15)
ms:contentKeyID: 49314501
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 开始 Lync Server 2013 的规划过程

 

_**上一次修改主题：** 2016-12-08_

尽管规划内部统一通信部署看似很有难度，但 Lync Server 提供了两种有价值的工具可以帮助您：

  - **规划工具**是一个向导，它会提出有关您的组织、您想要启用的 Lync Server 功能以及您的容量规划需求等一系列问题。然后，该向导会基于您的答案创建一个推荐的部署拓扑，并生成该部署的 Microsoft Visio 图。

  - **拓扑生成器**是 Lync Server 的一个安装组件。使用 拓扑生成器可以创建、调整和发布您所规划的拓扑。该工具还可以在开始安装服务器之前验证您的拓扑。在各个服务器上安装 Lync Server 时，这些服务器会在安装过程中读取发布的拓扑，而安装程序会根据拓扑中的指示部署服务器。

## Lync Server 规划工具

规划工具可获取工具中问题的答案并基于 Lync Server 准则和最佳做法生成一个拓扑。该工具还可以基于您的答案提供部署的多个视图。该工具可显示所有站点（即包括中央站点和分支站点）的全局视图，还可以显示包含每个站点的服务器和其他组件的详细视图。

运行 规划工具不会向您保证执行任何特定的部署或启动任何过程。实际上，在您拥有明确的计划之前运行 规划工具是了解规划过程中需要考虑的各种问题的一种有效方法。

可以多次运行 规划工具（以不同的方式回答问题）并比较结果。如果您有较为满意但需要进行更改的设计，可以返回到 规划工具、加载该设计并进行更改。完成一次 规划工具大约需要 15 分钟的时间。

在您满意后，可以使用 规划工具创建会话部署的图。在 拓扑生成器中创建部署时可以使用该图。

> [!NOTE]  
> 此版本的 Lync Server 2013 包含的规划工具是预发行版本。请注意，规划工具中的容量规划数字是初步数据，最终版本不支持这些数据。



## Lync Server 拓扑生成器

决定部署规划后，使用 拓扑生成器开始部署。完成后，使用 拓扑生成器验证拓扑，如果验证通过，则可以发布拓扑。发布拓扑后， Lync Server 会将拓扑置于 中央管理存储（如果尚不存在，此时将创建）中。在部署中的每台服务器上安装 Lync Server 时，服务器会从 中央管理存储中读取拓扑并安装其自身以适合其在部署中的角色。

或者，如果非常熟悉 Lync Server 且需要较少的规范性指导，则可以跳过 规划工具，使用 拓扑生成器中的向导执行部署的初始设计以及验证和发布步骤。

使用 拓扑生成器规划和发布拓扑是必需的步骤。不能绕过 拓扑生成器，也不能在部署中的服务器上单独安装 Lync Server。每台服务器都必须从 中央管理存储中的已验证且已发布的拓扑读取拓扑。

## 高级规划过程

建议按照以下常规过程使用文档和 规划工具来规划 Lync Server 部署。

1.  如果您熟悉早期版本的 Lync Server，请阅读 [Lync Server 2013 中的新功能](lync-server-2013-new-features.md)以熟悉 Lync Server 2013 中的新增功能和要求。

2.  阅读本节文档中的其他主题： [规划 Lync Server 2013 之前必须知道的拓扑基础知识](lync-server-2013-topology-basics-you-must-know-before-planning.md)、 [Lync Server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)、 [Lync Server 2013 的初始规划决策](lync-server-2013-initial-planning-decisions.md)和 [Lync Server 2013 的客户端](lync-server-2013-clients.md)。注意 [Lync Server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)中给出的规划决策。

3.  更好地熟悉 Lync Server 功能和必须回答的各种问题后，运行 规划工具并查看生成的拓扑及其详细信息。确保该拓扑满足您的组织的独特要求。

4.  如果您对特定的工作负荷或功能感兴趣或者需要了解这些内容，请阅读 [规划 Lync Server 2013](lync-server-2013-planning.md) 中的相关章节。

5.  再次运行 规划工具。可以从步骤 3 中创建的部署开始，然后修改结果，或者从头开始。
    
    如有必要，第三次运行 规划工具并重复相关步骤，直到对输出满意为止。

6.  最终确定拓扑计划后，使用 规划工具创建并打印拓扑的 Visio 图。在使用 拓扑生成器输入部署时可以用到该打印输出。

7.  开始部署之前，请阅读 [确定 Lync Server 2013 的系统要求](lync-server-2013-determining-your-system-requirements.md)和 [确定 Lync Server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md)以熟悉 Lync Server 的先决条件和必要基础结构。此外，请务必阅读 [规划 Lync Server 2013](lync-server-2013-planning.md) 中适用于计划部署的工作负荷和功能的所有章节。

## 从早期版本迁移

如果要从早期版本迁移到 Lync Server，请参阅 [迁移](migration.md)文档中有关迁移和部署的具体说明。

