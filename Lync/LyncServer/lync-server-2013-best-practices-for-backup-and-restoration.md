---
title: Lync Server 2013：备份和还原的最佳实践
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dd3345545ae8c77c4ebfcece7154e91059f9aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Lync Server 2013 备份和还原的最佳实践

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

本节包括两种类型的最佳实践：

  - 备份和还原的最佳实践。

  - 最大程度降低灾难影响的最佳做法。

<div>

## <a name="best-practices-for-backup-and-restoration"></a>备份和还原最佳做法

为了便于执行备份和还原过程，请在备份或还原数据时应用以下最佳做法：

  - 按适当的时间间隔执行定期备份。 最简单、最常用的备份类型和轮换计划是整个 SQL Server 数据库的夜间完整备份。 然后，如果需要还原，则还原过程只需要一个备份，且不会丢失超过一天的数据。

  - 如果使用 cmdlet 或 Lync Server 控制面板进行配置更改，请使用**CsConfiguration** cmdlet 在进行更改后拍摄拓扑配置文件（Xds）的快照备份，这样，如果需要还原数据库，则不会丢失所做的更改。 请注意，将以 XML 格式备份此配置并将其压缩为 ZIP 文件。

  - 请确保计划用于备份 Lync Server 的共享文件夹有足够的磁盘空间来容纳所有备份的数据。

  - 在 Lync Server 使用率通常较低时安排备份，以改善服务器性能和用户体验。

  - 请确保备份数据的位置是安全的（我们建议远程位置）。

  - 将备份文件保留在其中，以便在需要还原数据时使用。

  - 规划和安排对组织支持的还原过程的定期测试。

  - 提前验证备份和还原过程以确保它们按预期工作。

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>最大程度降低灾难影响的最佳做法

处理灾难性服务中断的最佳策略（因断电或突然出现硬件故障等事件而引起）是假设它们将会发生，并进行相应的规划。

如果至少中断和停机的 Lync 服务对您的组织至关重要，应考虑实施前端服务器的配对池，如在[Lync Server 2013 中规划高可用性和灾难恢复中](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。 然后，如果其中一个池发生灾难，管理员可以将该池的用户切换为由另一个池提供服务，最少停机时间。

作为备份和还原策略的一部分开发的灾难管理计划应包括以下各项：

  - 保持软件媒体以及软件和固件更新可随时使用。

  - 维护硬件和软件记录。

  - 定期备份数据并监视备份的完整性。

  - 在灾难恢复中培训你的员工，记录过程，并实施灾难恢复模拟训练。

  - 保留备用硬件，或者如果你有服务级别协议（SLA），请与硬件供应商和供应商签订以进行提示替换。

  - 分隔事务日志文件（.ldf 文件）和数据库文件（.mdf 文件）的位置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

