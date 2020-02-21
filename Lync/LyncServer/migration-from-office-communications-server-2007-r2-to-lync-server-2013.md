---
title: 从 Office Communications Server 2007 R2 迁移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344f15589e113a54b539d351ed8d4745e1fd3a5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>从 Office Communications Server 2007 R2 迁移至 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

本节中的主题将指导您完成从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013 的过程

<div>


> [!IMPORTANT]  
> 本文档介绍完成迁移的每个阶段通常需要执行的步骤。它并非适用于每种可能的旧部署拓扑或每种可能的迁移方案。因此，您可能不需要执行所述的每个步骤，也可能需要执行额外步骤，具体取决于您的部署。本文档还提供了验证步骤的示例。提供这些验证步骤是为了帮助您了解需要查看哪些内容，以确保执行迁移时每个阶段都成功完成。请根据您的特定迁移过程定制这些验证步骤。



</div>

本指南提供专用于升级现有部署的信息。它未解释如何更改现有拓扑。本指南不涉及新功能的实现。如果本指南中的某个过程已在其他文档中得到详细说明，本指南将为您指出相应的文档名称或文档章节。

在本文档中，术语的定义如以下列表所示。

  - *迁移*  
    将生产部署从 Office 通信服务器 2007 R2 的早期版本移动到 Lync Server 2013。

<!-- end list -->

  - *升级*  
    在服务器或客户端计算机上安装软件的更高版本。

<!-- end list -->

  - *共存*  
    在迁移过程中，如果将某些功能迁移到 Lync Server 2013，并且其他功能仍保留在以前版本的 Office 通信服务器 2007 R2 中，则迁移过程中存在的临时环境。

<!-- end list -->

  - *相互*  
    在共存阶段部署能够正常运行的能力。

<div>

## <a name="in-this-section"></a>本节内容

  - [开始迁移之前的准备工作](before-you-begin-the-migration_1.md)

  - [迁移阶段](migration-phases_1.md)

  - [第1阶段：规划从 Office 通信服务器 2007 R2 迁移](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [第2阶段：准备迁移](phase-2-prepare-for-migration_1.md)

  - [第3阶段：部署 Lync Server 2013 试点池](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [第4阶段：合并拓扑](phase-4-merge-topologies.md)

  - [第5阶段：配置引导池](phase-5-configure-the-pilot-pool.md)

  - [第6阶段：将用户移动到引导池](phase-6-move-users-to-the-pilot-pool.md)

  - [第7阶段：将 Lync Server 2013 边缘服务器添加到引导池](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [第8阶段：从试点部署移动到生产环境](phase-8-move-from-pilot-deployment-into-production.md)

  - [第9阶段：完成迁移后任务](phase-9-complete-post-migration-tasks.md)

  - [阶段10：停止旧版网站](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

