---
title: Lync Server 2013：后端服务器高可用性
description: Lync Server 2013：后端服务器高可用性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805cbf96e107329aa5c374cfa1e2d01234d360a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543768"
---
# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Lync Server 2013 中的后端服务器高可用性

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-08-12_

若要确保后端服务器具有高可用性，可以使用同步 SQL 镜像或 SQL 群集。 使用其中一种解决方案是可选的，但建议维护贵组织的业务连续性。 Lync Server 2013 中的后端服务器高可用性不支持异步 SQL 镜像。 在本文档剩下的部分中，除非另外明确规定，否则 SQL 镜像是指同步的 SQL 镜像。

您可以使用拓扑生成器轻松设置 SQL 镜像。 对于 SQL 故障转移群集，必须使用 SQL Server 进行安装。

如果在与用于灾难恢复的另一个前端池配对的池中使用 SQL 镜像或 SQL 群集，则应在两个池中使用相同的后端高可用性解决方案。 不应使用 sql 群集将 SQL 镜像与池进行配对。

在部署 SQL 镜像时，池中的所有 Lync Server 数据库都将进行镜像，其中包括中央管理存储（如果位于此池中）以及响应组应用程序数据库和呼叫寄存应用程序数据库（如果这些应用程序在池中运行）。

通过使用 SQL 镜像，您无需对服务器使用共享存储。每台服务器将其数据库副本保留在本地存储上。

您可选择使用或不使用见证服务器部署 SQL 镜像。我们建议使用见证服务器，因为见证服务器可实现后端服务器的故障转移的自动化。否则，管理员必须手动调用故障转移。请注意，即使部署了见证服务器，管理员也可手动调用后端服务器故障转移（如有必要）。

如果您使用见证服务器，则可对多对后端服务器使用一个见证服务器。见证服务器和后端服务器对之间没有严格的 1:1 对应关系。对多对后端服务器使用一个见证服务器的部署不如为每对后端服务器使用单独的见证服务器的拓扑有弹性。

有关 SQL 群集支持的详细信息，请参阅 [Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。 有关部署 SQL 群集的详细信息，请参阅 [CONFIGURE SQL Server 集群 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)。

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>使用 SQL 镜像自动后端服务器故障转移的恢复时间

对于 SQL 镜像的自动后端故障转移，在恢复时间目标 (RTO) 的工程目标为5分钟。 由于使用了同步的 SQL 镜像，我们在后端服务器失败期间无需考虑数据丢失（除了在服务器间移动数据期间前端服务器和后端服务器同时宕机的罕见情况）。 恢复点目标 (RPO) 的设计目标为 5 分钟。

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>在后端服务器出现故障时使用 SQL 镜像的用户体验

失败期间的用户体验取决于失败的性质和拓扑。

如果使用 SQL 镜像并配置了见证服务器，并且主体发生故障，后端服务器故障转移会自动快速地进行。 活动用户应该不太会注意到正在进行的会话出现中断。

如果未配置见证服务器，则管理员手动调用故障转移需要一些时间。 在这段时间内，活动用户可能会受到影响。 他们将继续大约 30 分钟的正常会话。 如果仍未还原主主服务器，或者管理员尚未故障转移到备份，则用户将切换到 "恢复模式"，这意味着他们无法在 Lync Server (（如添加联系人) ）上执行需要永久更改的任务。

如果主体和镜像后端服务器均失败，或者其中一台服务器和见证服务器失败，则后端服务器将变得不可用（即使它是仍在工作的主体）。在此情况下，活动用户将在一段时间之后切换至恢复能力模式。

</div>

</div>

<span> </span>

</div>

</div>

</div>

