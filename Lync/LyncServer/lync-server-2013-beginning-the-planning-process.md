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
ms.openlocfilehash: dd0a83042415cd2cf919d0fd66fe5309a4cae9e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>开始 Lync Server 2013 的规划过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-24_

尽管在规划本地统一通信部署可能看起来 intimidating，Lync Server 提供了两个有用的工具来帮助您：

  - **规划工具**是一个向导，它提供有关您的组织、您要启用的 Lync Server 功能以及容量规划需求的一系列问题。 然后，它根据你的回答创建建议的部署拓扑，并生成此部署的 Microsoft Visio 关系图。

  - **拓扑生成器**是 Lync Server 的安装组件。 您可以使用拓扑生成器来创建、调整和发布规划的拓扑。 该工具还可以在开始安装服务器之前验证您的拓扑。 在单独的服务器上安装 Lync Server 时，服务器会在安装过程中读取已发布的拓扑，并且安装程序将在拓扑中按照指示的方式部署服务器。

<div>

## <a name="lync-server-planning-tool"></a>Lync Server 规划工具

规划工具将获取工具中问题的答案，并根据 Lync Server 指南和最佳实践生成拓扑。 它还根据您的回答提供了多个部署视图。 它同时显示了所有网站的全局视图（即，包括中央网站和分支网站），以及显示每个网站上的服务器和其他组件的详细视图。

运行规划工具不会向您提交任何特定部署，也不会启动任何进程。 事实上，即使在您有一个固定计划之前运行规划工具，也可能是了解您在规划过程中需要考虑的问题种类的一种非常有益的方法。

您可以多次运行规划工具，以不同的方式回答问题，并比较结果。 如果你的设计最常用，但你需要对进行更改，则可以返回到规划工具，加载设计，然后进行更改。 完成规划工具一次大约需要15分钟时间。

在您满意后，您可以使用规划工具创建规划的部署的关系图。 在拓扑生成器中创建部署时，可以使用此关系图。

<div>


> [!NOTE]  
> 此版本的 Lync Server 2013 中包含的规划工具是预发布版本。 请注意，规划工具中的容量规划数量是初步的，并且在最终版本中不受支持。



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Lync Server 拓扑生成器

在确定了部署计划后，使用拓扑生成器开始部署。 完成后，使用拓扑生成器验证拓扑，然后，如果它通过，则可以发布拓扑。 发布拓扑时，Lync Server 会将拓扑放到中央管理存储中，如果目前尚不存在，则会创建该拓扑。 当您在部署中的每台服务器上安装 Lync Server 时，服务器将从中央管理存储读取拓扑，并自行安装以适应其在您的部署中的角色。

或者，如果您非常熟悉 Lync Server，并且需要更少的说明性指导，则可以跳过规划工具并使用拓扑生成器中的向导进行部署的初始设计，还可以使用验证和发布步骤。

使用拓扑生成器来规划和发布拓扑是必需的步骤。 您不能绕过拓扑生成器并在部署中的服务器上单独安装 Lync Server。 每台服务器必须从中央管理存储中已验证的已发布拓扑中读取拓扑。

</div>

<div>

## <a name="high-level-planning-process"></a>高级别规划过程

我们建议使用以下常规过程来规划 Lync Server 部署，同时使用文档和规划工具。

1.  如果您熟悉 Lync Server 的早期版本，请阅读[lync server 2013 中的新功能](lync-server-2013-new-features.md)，以熟悉 lync server 2013 中的新功能和要求。

2.  阅读本文档的本部分中的其他主题：[规划 Lync server 2013 之前必须了解的拓扑基础知识](lync-server-2013-topology-basics-you-must-know-before-planning.md)、 [lync server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)、 [lync server 2013 的初始规划决定](lync-server-2013-initial-planning-decisions.md)以及[lync server 2013 的客户端](lync-server-2013-clients.md)。 请注意[Lync Server 2013 中的参考拓扑中](lync-server-2013-reference-topologies.md)所示的规划决策。

3.  现在，您更熟悉 Lync Server 功能以及必须回答的问题种类，请运行规划工具并查看生成的拓扑及其详细信息。 确保拓扑符合组织的独特要求。

4.  如果有您感兴趣或需要了解的特定工作负荷或功能，请阅读[规划 Lync Server 2013](lync-server-2013-planning.md)的相应部分。

5.  再次运行规划工具。 您可以从在步骤3中创建的部署开始，并修改结果，也可以从头开始。
    
    如果需要，请第三次运行规划工具并重复此操作，直到您对输出结果感到满意。

6.  完成拓扑计划后，请使用规划工具创建并打印您的拓扑的 Visio 图表。 在使用拓扑生成器来输入拓扑时，可以使用此打印输出。

7.  在开始部署之前，请阅读[确定 Lync server 2013 的系统要求](lync-server-2013-determining-your-system-requirements.md)，并[确定 lync server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md)，以熟悉 lync server 的先决条件和必要的基础结构。 此外，请务必阅读适用于计划部署的工作负荷和功能的所有[规划的 Lync Server 2013](lync-server-2013-planning.md)部分。

</div>

<div>

## <a name="migrating-from-previous-versions"></a>从以前的版本迁移

如果要从以前的版本迁移到 Lync Server，请参阅[迁移](migration.md)文档以获取有关迁移和部署的特定说明。

</div>

</div>

<span> </span>

</div>

</div>

</div>

