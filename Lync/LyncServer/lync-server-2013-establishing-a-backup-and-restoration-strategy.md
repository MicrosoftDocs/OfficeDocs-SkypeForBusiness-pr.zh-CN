---
title: 'Lync Server 2013: 建立备份和还原策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d378c66ae820ef0be7b7b3b0492b023863e977ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>为 Lync Server 2013 建立备份和还原策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-26_

在你可以为 Lync Server 开发备份和还原计划之前, 你需要开发符合你组织的目标的策略。 若要制定有效的备份和还原策略, 您需要:

  - 建立业务优先级。

  - 确定备份和还原要求。

<div>

## <a name="establishing-business-priorities"></a>建立业务优先级

评估你的组织的业务优先级。 通常, 影响你的备份和还原策略的主要业务优先级如下所示:

  - 业务连续性要求

  - 数据完整性

  - 数据重要程度

  - 可移植性要求

  - 成本限制

业务需求 (如这些帮助) 确定你与客户一起开发的服务级别协议 (Sla)。 服务级别协议极大地影响你的备份和恢复策略。

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>确定备份和还原要求

你的企业优先级和服务级别协议在确定你的组织的备份和还原 Lync 服务器的要求方面起作用。 确定并记录以下各项的要求:

  - **备份频率有关**   备份频率的最佳做法的详细信息, 请参阅[Lync Server 2013 备份和还原的最佳做法](lync-server-2013-best-practices-for-backup-and-restoration.md)。

  - **备份和还原工具**   包括谁在哪些计算机上使用这些工具。 有关本主题中讨论的工具和必要权限的详细信息, 请参阅[Lync Server 2013 中的备份和还原要求: 工具和权限](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。

  - **备份位置**   确定备份是否保留在本地或远程, 以使安全和辅助功能可供考虑。 指定要用于备份的媒体。

  - **硬件和软件要求**   识别并记录你的特定硬件和软件要求, 包括用于备份存储的硬件和特定组件的还原以及任何软件和网络连接支持备份和还原。 在开发硬件和软件要求时, 请记住下面的各种还原方案。

  - **还原方案**   下面是针对以下方案的还原过程:
    
      - Lync 服务器池失败。 此方案要求在池中重建每台服务器。
    
      - 标准版服务器失败。 此方案要求在新计算机或全新计算机上重建服务器并还原数据库。
    
      - 缺少中央管理存储。 此方案至少需要还原和发布中央管理存储。
    
      - 当中央管理存储仍正常工作时, 后端服务器的丢失。 此方案要求在新计算机或全新计算机上重建服务器并还原数据库。
    
      - 作为 Lync 服务器池成员的服务器失败。 此方案要求在新计算机或全新计算机上重建服务器。
    
      - 文件存储失败。 此方案需要还原文件服务器或文件群集。
    
      - 存档、监视或持久聊天数据库失败。 此方案需要重新创建数据库, 并且如果数据对你的组织非常重要, 请还原数据。 无需使用 "存档"、"监视" 和 "持久聊天" 数据即可恢复和运行 Lync 服务器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

