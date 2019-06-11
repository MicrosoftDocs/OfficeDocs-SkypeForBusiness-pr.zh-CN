---
title: 从 Office Communications Server 2007 R2 迁移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43064d265bc08cab3721d0f19fd7f89184871f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>从 Office Communications Server 2007 R2 迁移至 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

本部分中的主题将指导你完成从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013 的过程

<div>


> [!IMPORTANT]  
> 本文档介绍了完成迁移的每个阶段通常需要执行的步骤。 它不能解决每个可能的旧部署拓扑或每种可能的迁移方案。 因此, 你可能不需要执行所述的每个步骤, 或者你可能需要执行其他步骤, 具体取决于你的部署。 本文档还提供了验证步骤的示例。 提供这些验证步骤旨在帮助你了解需要查找的内容, 以确保每个阶段在你的迁移过程中成功完成。 将这些验证步骤定制到特定迁移过程。



</div>

本指南提供有关升级现有部署的特定信息。 它不介绍如何更改现有拓扑。 本指南不介绍新功能的实现。 当详细过程记录在其他位置时, 本指南将指导你使用相应的文档或文档部分。

此文档定义了下表中指定的术语。

  - *移植*  
    将生产部署从早期版本的 Office 通信服务器 2007 R2 迁移到 Lync Server 2013。

<!-- end list -->

  - *升级*  
    在服务器或客户端计算机上安装较新版本的软件。

<!-- end list -->

  - *既*  
    在迁移过程中, 如果将某些功能迁移到 Lync Server 2013 且其他功能仍保留在以前版本的 Office 通信服务器 2007 R2 中, 则迁移期间存在的临时环境。

<!-- end list -->

  - *交互性*  
    部署在共存期间成功运行的能力。

<div>

## <a name="in-this-section"></a>本节内容

  - [开始迁移之前的准备工作](before-you-begin-the-migration_1.md)

  - [迁移阶段](migration-phases_1.md)

  - [第1阶段: 规划从 Office 通信服务器 2007 R2 迁移](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [第 2 阶段：准备迁移](phase-2-prepare-for-migration_1.md)

  - [第3阶段: 部署 Lync Server 2013 试验池](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [第4阶段: 合并拓扑](phase-4-merge-topologies.md)

  - [第5阶段: 配置试行池](phase-5-configure-the-pilot-pool.md)

  - [第6阶段: 将用户移动到 "引导" 池](phase-6-move-users-to-the-pilot-pool.md)

  - [第7阶段: 将 Lync Server 2013 边缘服务器添加到试验池](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [第8阶段: 从试验部署迁移到生产环境](phase-8-move-from-pilot-deployment-into-production.md)

  - [第9阶段: 完成迁移后任务](phase-9-complete-post-migration-tasks.md)

  - [第10阶段: 停止旧版网站](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

