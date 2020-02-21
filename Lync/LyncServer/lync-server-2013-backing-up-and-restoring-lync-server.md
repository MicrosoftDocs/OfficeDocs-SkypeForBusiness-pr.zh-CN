---
title: Lync Server 2013：备份和还原 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f2f907c8efb663816ca50152643cea70fcc2ff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>备份和还原 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

在本节中，您将找到备份 Lync Server 2013 数据的最佳做法，并在遇到故障时将其还原。 这些最佳实践适用于以下情况：

  - 所有类型（前端服务器、边缘服务器、中介服务器、持久聊天服务器或控制器）的完整 Lync Server 池，或其中一个池中的单个服务器。

  - 中央管理服务器

  - Standard Edition 服务器

  - 企业版后端服务器

  - 文件存储

  - 存档数据库、监控数据库或持久聊天数据库

本部分不包括有关还原整个网站或开发备用网站的信息。 有关开发具有成对前端池的灾难恢复解决方案的详细信息，请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。 这是规划灾难恢复的推荐方法。

如果已部署配对的前端池，如果其中一个池发生故障且无法恢复，则可以使用其配对的池中的新完全限定的域名（FQDN）还原此池。 有关执行此恢复的步骤的详细信息，请参阅[在 Lync Server 2013 中对池进行故障转移](lync-server-2013-failing-over-a-pool.md)。 此外，如果您稍后要重新创建属于前端对的故障和不可恢复的池，则可以使用在[Lync Server 2013 中执行 ABC 前端池故障转移](lync-server-2013-performing-an-abc-front-end-pool-failover.md)中的步骤。

本文档介绍的方法包括规划阶段的特殊注意事项。 有关详细信息，请参阅为[Lync Server 2013 建立备份和还原计划](lync-server-2013-establishing-a-backup-and-restoration-plan.md)。

<div>

## <a name="in-this-section"></a>本部分内容

  - [准备 Lync Server 2013 备份和还原](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [在 Lync Server 2013 中备份数据和设置](lync-server-2013-backing-up-data-and-settings.md)

  - [在 Lync Server 2013 中还原数据和设置](lync-server-2013-restoring-data-and-settings.md)

  - [Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

