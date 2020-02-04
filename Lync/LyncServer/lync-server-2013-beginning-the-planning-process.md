---
title: Lync Server 2013：开始规划过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9da1c5535f190a6f57aa76b78a04845d4a073e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>开始 Lync Server 2013 的规划过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-24_

在规划内部部署统一通信部署可能看起来生畏时，Lync Server 提供了两个有用的工具来帮助你：

  - **规划工具**是一个向导，提供一系列有关您的组织的问题、要启用的 Lync 服务器功能以及您的容量规划需求。 然后，它根据你的答案创建推荐的部署拓扑，并生成此部署的 Microsoft Visio 图表。

  - **拓扑生成器**是 Lync Server 的安装组件。 使用拓扑生成器创建、调整和发布规划的拓扑。 它还会在您开始服务器安装之前验证您的拓扑。 在单个服务器上安装 Lync Server 时，服务器会将已发布的拓扑作为安装过程的一部分进行读取，安装程序将按照拓扑中的指示部署服务器。

<div>

## <a name="lync-server-planning-tool"></a>Lync Server 计划工具

规划工具将获取有关工具中的问题的答案，并基于 Lync Server 指南和最佳做法生成拓扑。 它还根据你的回答提供了多个部署视图。 它同时显示了所有网站的全局视图（即，包括中央网站和分支网站），以及每个网站上显示服务器和其他组件的详细视图。

运行计划工具不会将你提交到任何特定部署或启动任何进程。 事实上，即使在您有固定的计划之前运行计划工具，也是了解你在规划过程中需要考虑的问题的一种非常有益的方式。

你可以多次运行计划工具，以不同的方式回答问题，并比较结果。 如果你有一个最满意的设计，但你需要对进行更改，则可以返回到计划工具、加载设计并进行更改。 完成计划工具一次大约需要15分钟。

在满意后，您可以使用计划工具来创建规划部署的图表。 在拓扑生成器中创建部署时，可以使用此关系图。

<div>


> [!NOTE]  
> 此版本的 Lync Server 2013 附带的计划工具是预发布版本。 请注意，规划工具中的容量规划数字是初步数据，最终版本不支持这些数据。



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Lync Server 拓扑生成器

确定部署计划后，使用拓扑生成器开始部署。 完成后，使用拓扑生成器验证拓扑，然后，如果它通过，你可以发布拓扑。 当你发布拓扑时，Lync Server 会将拓扑放入中央管理存储中，如果该存储尚不存在，则会在此处创建。 在部署中的每台服务器上安装 Lync Server 时，服务器将从中央管理存储读取拓扑，并自行安装以适合其在你的部署中的角色。

或者，如果你非常熟悉 Lync Server，并且需要更少的说明性指导，则可以跳过规划工具并使用拓扑生成器中的向导进行部署的初始设计，还可以使用验证和发布步骤。

使用拓扑生成器规划和发布拓扑是必需的步骤。 无法绕过拓扑生成器并在部署中的服务器上单独安装 Lync Server。 每台服务器必须从中央管理存储中已验证的已发布拓扑中读取拓扑。

</div>

<div>

## <a name="high-level-planning-process"></a>高级别规划流程

我们建议在使用文档和规划工具规划 Lync Server 部署时使用以下常规过程。

1.  如果你熟悉 Lync Server 的早期版本，请阅读[Lync server 2013 中的新功能](lync-server-2013-new-features.md)，以熟悉 lync server 2013 中的新功能和要求。

2.  阅读本文档的本部分中的其他主题：[规划 Lync server 2013 之前必须了解的拓扑结构基础知识](lync-server-2013-topology-basics-you-must-know-before-planning.md)、 [lync server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)、lync [server 2013 的初始规划决策](lync-server-2013-initial-planning-decisions.md)以及[lync server 2013 的客户端](lync-server-2013-clients.md)。 请注意[Lync Server 2013 中的参考拓扑中](lync-server-2013-reference-topologies.md)所示的规划决策。

3.  既然您更熟悉 Lync 服务器功能和必须回答的问题类型，请运行规划工具并查看生成的拓扑及其详细信息。 确保拓扑符合你的组织的独特要求。

4.  如果存在你感兴趣或需要了解的特定工作负荷或功能，请阅读[规划 Lync Server 2013](lync-server-2013-planning.md)的相应部分。

5.  再次运行计划工具。 你可以从步骤3中创建的部署开始，并修改结果，或者从头开始。
    
    如果需要，请在第三次运行 "规划" 工具并重复操作，直到对输出满意为止。

6.  完成拓扑计划后，使用规划工具创建和打印拓扑的 Visio 图表。 在使用拓扑生成器输入拓扑时，可以使用此打印输出。

7.  开始部署之前，请阅读[确定 lync server 2013 的系统要求](lync-server-2013-determining-your-system-requirements.md)，并[确定 lync server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md)，以熟悉 lync 服务器的先决条件和必要的基础结构。 此外，请确保已阅读适用于你计划部署的工作负荷和功能的所有适用于[Lync Server 2013 的计划](lync-server-2013-planning.md)部分。

</div>

<div>

## <a name="migrating-from-previous-versions"></a>从以前的版本迁移

如果您从以前的版本迁移到 Lync Server，请参阅[迁移](migration.md)文档，了解有关迁移和部署的特定说明。

</div>

</div>

<span> </span>

</div>

</div>

</div>

