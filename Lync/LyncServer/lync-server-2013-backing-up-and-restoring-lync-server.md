---
title: Lync Server 2013：备份和还原 Lync 服务器
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
ms.openlocfilehash: 43a96f47bfe9d28fdbc37eea0ae62ef6cd763098
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a>备份和还原 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

在本部分中，你将找到备份 Lync Server 2013 数据的最佳做法，以及在遇到故障时还原它的最佳做法。 这些最佳做法适用于以下情况：

  - 任何类型（前端服务器、边缘服务器、中介服务器、持久聊天服务器或控制器）的整个 Lync 服务器池，或者其中一个池中的单个服务器。

  - 中央管理服务器

  - 标准版服务器

  - 企业版后端服务器

  - 文件存储

  - 存档数据库、监视数据库或持久聊天数据库

本部分不包括有关还原整个网站或开发备用网站的信息。 有关使用配对的前端池开发灾难恢复解决方案的详细信息，请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。 这是规划灾难恢复的推荐方法。

如果你已部署成对的前端池，并且其中一个池失败且无法恢复，则可以使用其配对的池中的新完全限定的域名（FQDN）还原此池。 有关执行此恢复的步骤的详细信息，请参阅[在 Lync Server 2013 中故障转移池](lync-server-2013-failing-over-a-pool.md)。 此外，如果你稍后想要重新创建属于前端对的失败和不可恢复的池，你可以使用在[Lync Server 2013 中执行 ABC 前端池故障转移](lync-server-2013-performing-an-abc-front-end-pool-failover.md)的步骤。

本文档中所述的方法涉及规划阶段中的特殊注意事项。 有关详细信息，请参阅为[Lync Server 2013 建立备份和还原计划](lync-server-2013-establishing-a-backup-and-restoration-plan.md)。

<div>

## <a name="in-this-section"></a>本节内容

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

