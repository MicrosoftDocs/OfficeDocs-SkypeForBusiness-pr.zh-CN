---
title: Lync Server 2013：后端服务器高可用性
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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a>Lync Server 2013 中的后端服务器高可用性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-08-12_

为确保后端服务器的高可用性，可以使用同步 SQL 镜像或 SQL 群集。 使用其中一个解决方案是可选的，但建议保持组织的业务连续性。 Lync Server 2013 中的后端服务器高可用性不支持异步 SQL 镜像。 在本文档的其余部分中，SQL 镜像意味着同步 SQL 镜像，除非另有明确声明。

你可以通过拓扑生成器轻松设置 SQL 镜像。 对于 SQL 故障转移群集，您必须使用 SQL Server 进行设置。

如果在与用于灾难恢复的另一前端池配对的池中使用 SQL 镜像或 SQL 群集，则应在两个池中使用相同的后端高可用性解决方案。 不应使用 sql 群集和池将 SQL 镜像与池配对。

当你部署 SQL 镜像时，池中的所有 Lync Server 数据库都将被镜像，包括中央管理存储（如果它位于此池中）以及响应组应用数据库和调用寄存应用程序数据库（如果这些应用程序正在池中运行。

使用 SQL 镜像，无需为服务器使用共享存储。 每台服务器将其数据库副本保留在本地存储上。

你可以选择使用或不使用见证部署 SQL 镜像。 我们建议使用见证服务器，因为见证服务器可实现后端服务器的故障转移的自动化。 否则，管理员必须手动调用故障转移。 请注意，即使部署了见证服务器，管理员也可手动调用后端服务器故障转移（如有必要）。

如果您使用见证服务器，则可对多对后端服务器使用一个见证服务器。见证服务器和后端服务器对之间没有严格的 1:1 对应关系。对多对后端服务器使用一个见证服务器的部署不如为每对后端服务器使用单独的见证服务器的拓扑有弹性。

有关 SQL 群集支持的详细信息，请参阅[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。 有关部署 SQL 群集的详细信息，请参阅[配置 Lync server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)。

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a>利用 SQL 镜像自动后端服务器故障转移的恢复时间

对于具有 SQL 镜像的自动后端故障切换，针对恢复时间目标（RTO）的工程目标是5分钟。 由于同步 SQL 镜像，我们不会在回退服务器故障期间预计数据丢失，但当前端服务器和后端服务器在服务器之间移动数据时，很少发生这种情况。 恢复点目标 (RPO) 的设计目标为 5 分钟。

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a>SQL 镜像后端服务器出现故障期间的用户体验

失败期间的用户体验取决于失败的性质和拓扑。

如果你使用 SQL 镜像并配置了见证，则主体失败，后端服务器故障转移会自动快速进行。 活动用户应该不太会注意到正在进行的会话出现中断。

如果未配置见证服务器，则管理员手动调用故障转移需要一些时间。 在这段时间内，活动用户可能会受到影响。 他们将继续大约 30 分钟的正常会话。 如果主服务器仍未还原，或者管理员未故障转移到备份，则用户将切换到复原模式，这意味着他们无法执行需要在 Lync Server 上永久更改的任务（如添加联系人）。

如果主体和镜像后端服务器均失败，或者其中一台服务器和见证服务器失败，则后端服务器将变得不可用（即使它是仍在工作的主体）。在此情况下，活动用户将在一段时间之后切换至恢复能力模式。

</div>

</div>

<span> </span>

</div>

</div>

</div>

