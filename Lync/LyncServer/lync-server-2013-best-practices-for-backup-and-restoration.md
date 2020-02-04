---
title: Lync Server 2013：备份和还原的最佳做法
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
ms.openlocfilehash: e51f846d92f5d8cfecbbface31df6543c5c9ac23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Lync Server 2013 的备份和还原的最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

本部分包含两种类型的最佳做法：

  - 备份和还原的最佳做法。

  - 最大程度降低灾难影响的最佳做法。

<div>

## <a name="best-practices-for-backup-and-restoration"></a>备份和还原的最佳做法

为了帮助你的备份和还原过程，请在备份或还原数据时应用以下最佳做法：

  - 按适当的时间间隔执行定期备份。 最简单、最常用的备份类型和旋转计划是整个 SQL Server 数据库的晚上完整备份。 然后，如果需要还原，还原过程只需要一个备份，不会丢失一天的数据。

  - 如果你使用 cmdlet 或 Lync Server 控制面板进行配置更改，请使用**CsConfiguration** cmdlet 在进行更改后获取拓扑配置文件（Xds）的快照备份，以便你不会丢失所做的更改（如果你需要还原数据库）。 请注意，此配置以 XML 格式进行备份并压缩为 ZIP 文件。

  - 请确保计划用于备份 Lync 服务器的共享文件夹有足够的磁盘空间来容纳所有备份的数据。

  - 在 Lync 服务器使用率通常较低时安排备份，以改善服务器性能和用户体验。

  - 请确保备份数据的位置是安全的（我们建议远程位置）。

  - 将备份文件保留为可用，以防需要还原数据。

  - 计划和安排定期测试你的组织支持的还原过程。

  - 事先验证你的备份和还原过程，以确保它们按预期工作。

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>最大程度降低灾难影响的最佳做法

处理灾难性服务中断（由无法管理的事件（如断电或突然硬件故障）导致的最佳策略是假设它们将发生，并进行相应规划。

如果 Lync 服务的中断和中断最少，对你的组织而言是业务关键型的，则应考虑实现前端服务器的配对池，如在[Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)中所述。 然后，如果其中一个池有灾难，管理员可以将该池的用户切换为由另一个池提供服务，最少停机时间。

作为备份和还原策略的一部分开发的灾难管理计划应包括以下内容：

  - 让你的软件媒体和你的软件和固件更新随时可用。

  - 维护硬件和软件记录。

  - 定期备份数据并监视备份的完整性。

  - 在灾难恢复、记录过程和实施灾难恢复模拟训练中培训您的员工。

  - 让备用硬件可用，或者，如果您有服务级别协议（SLA），请与硬件供应商和供应商一起进行提示更换。

  - 分隔事务日志文件（.ldf 文件）和数据库文件（.mdf 文件）的位置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

