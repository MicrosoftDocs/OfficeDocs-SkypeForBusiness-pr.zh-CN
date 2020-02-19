---
title: Lync Server 2013：建立备份和还原策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcdfbb6b51a966149451e8f396b345b0383947e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>为 Lync Server 2013 建立备份和还原策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-26_

在您可以为 Lync Server 开发备份和还原计划之前，您需要制定符合组织目标的策略。 若要制定有效的备份和还原策略，您将需要：

  - 建立业务优先级。

  - 确定备份和还原要求。

<div>

## <a name="establishing-business-priorities"></a>建立业务优先级

评估组织的业务优先级。通常情况下，影响您的备份和还原策略的主要业务优先级包括以下内容：

  - 业务连续性要求

  - 数据完整性

  - 数据关键程度

  - 可移植性要求

  - 成本约束

这些业务需求（如以下帮助）可确定您与客户一起开发的服务级别协议（Sla）。 服务级别协议极大地影响了备份和恢复策略。

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>确定备份和还原要求

你的业务优先级和服务级别协议在确定组织对备份和还原 Lync Server 的要求时起作用。 请确定和记录您对以下项的要求：

  - **备份频率有关**   备份频率的最佳实践的详细信息，请参阅[Lync Server 2013 的备份和还原最佳实践](lync-server-2013-best-practices-for-backup-and-restoration.md)。

  - **备份和还原工具**   包括谁是使用工具，以及在哪些计算机上。 有关本主题中讨论的工具和必要权限的详细信息，请参阅[Lync Server 2013 中的备份和还原要求：工具和权限](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。

  - **备份位置**   确定是否在本地或远程保存备份，并考虑安全性和可访问性。 指定用于备份的介质。

  - **硬件和软件要求**   确定并记录特定的硬件和软件要求，包括备份存储的硬件和特定组件的还原以及支持备份和还原所需的任何软件和网络连接。 在确定硬件和软件要求时，请记住下面的各种还原方案。

  - **还原方案**   下面是针对以下方案的还原过程：
    
      - Lync Server 池失败。 此方案要求重新构建池中的每台服务器。
    
      - Standard Edition server 失败。 此方案要求在新的或干净的计算机上重新构建服务器和还原数据库。
    
      - 中央管理存储丢失。 此方案至少需要还原和发布中央管理存储。
    
      - 中央管理存储仍正常运行时，失去后端服务器。 此方案要求在新的或干净的计算机上重新构建服务器和还原数据库。
    
      - 作为 Lync Server 池成员的服务器出现故障。 此方案要求在新的或干净的计算机上重新构建服务器。
    
      - 文件存储失败。 此方案要求还原文件服务器或文件群集。
    
      - 存档、监视或持久聊天数据库失败。 此方案要求重新创建数据库和还原数据（如果该数据对贵组织十分重要）。 无需存档、监视和持久聊天数据即可恢复并运行 Lync Server。

</div>

</div>

<span> </span>

</div>

</div>

</div>

