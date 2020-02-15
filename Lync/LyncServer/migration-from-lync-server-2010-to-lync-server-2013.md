---
title: 从 Lync Server 2010 迁移到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cab7ac790d08a848cb90a609720c237c4c20062
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>从 Lync Server 2010 迁移到 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

本节中的主题将指导您完成从 Lync Server 2010 迁移到 Lync Server 2013 的过程。

<div>


> [!IMPORTANT]  
> 本文档介绍完成迁移的每个阶段通常需要执行的步骤。它并非适用于每种可能的旧部署拓扑或每种可能的迁移方案。因此，您可能不需要执行所述的每个步骤，也可能需要执行额外步骤，具体取决于您的部署。本文档还提供了验证步骤的示例。提供这些验证步骤是为了帮助您了解需要查看哪些内容，以确保执行迁移时每个阶段都成功完成。请根据您的特定迁移过程定制这些验证步骤。



</div>

本指南提供专用于升级现有部署的信息。它未解释如何更改现有拓扑。本指南不涉及新功能的实现。如果本指南中的某个过程已在其他文档中得到详细说明，本指南将为您指出相应的文档名称或文档章节。

在本文档中，术语的定义如以下列表所示。

  - *迁移*  
    将你的生产部署从以前版本的 Lync Server 2010 迁移到 Lync Server 2013。

<!-- end list -->

  - *升级*  
    在服务器或客户端计算机上安装软件的更高版本。

<!-- end list -->

  - *共存*  
    在迁移过程中，如果将某些功能迁移到 Lync Server 2013，并且其他功能仍保留在以前版本的 Lync Server 2010 中，则在迁移过程中存在的临时环境。

<!-- end list -->

  - *相互*  
    在共存阶段部署能够正常运行的能力。

<div>

## <a name="in-this-section"></a>本节内容

  - [开始迁移之前的准备工作](before-you-begin-the-migration.md)

  - [第1阶段：从 Lync Server 2010 规划迁移](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [第2阶段：准备迁移](phase-2-prepare-for-migration.md)

  - [第3阶段：部署 Lync Server 2013 试点池](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [第4阶段：将测试用户移动到引导池](phase-4-move-test-users-to-the-pilot-pool.md)

  - [第5阶段：将 Lync Server 2013 边缘服务器添加到引导池](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [第6阶段：从试点部署移动到生产环境](phase-6-move-from-pilot-deployment-into-production.md)

  - [第7阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)

  - [第8阶段：停止旧版池](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

