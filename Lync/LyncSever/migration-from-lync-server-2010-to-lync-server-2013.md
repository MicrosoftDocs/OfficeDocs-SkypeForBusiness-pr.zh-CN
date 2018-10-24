---
title: 从 Lync Server 2010 迁移到 Lync Server 2013
TOCTitle: 从 Lync Server 2010 迁移到 Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205369(v=OCS.15)
ms:contentKeyID: 49314682
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从 Lync Server 2010 迁移到 Lync Server 2013

 

_**上一次修改主题：** 2012-09-17_

本节中的主题引导您完成从 Lync Server 2010 迁移到 Lync Server 2013 的过程。

> [!IMPORTANT]
> 本文档介绍完成迁移的每个阶段通常需要执行的步骤。它并非适用于每种可能的旧部署拓扑或每种可能的迁移方案。因此，您可能不需要执行所述的每个步骤，也可能需要执行额外步骤，具体取决于您的部署。本文档还提供了验证步骤的示例。提供这些验证步骤是为了帮助您了解需要查看哪些内容，以确保执行迁移时每个阶段都成功完成。请根据您的特定迁移过程定制这些验证步骤。


本指南提供专用于升级现有部署的信息。它未解释如何更改现有拓扑。本指南不涉及新功能的实现。如果本指南中的某个过程已在其他文档中得到详细说明，本指南将为您指出相应的文档名称或文档章节。

在本文档中，术语的定义如以下列表所示。

  - *迁移*   
    将生产部署从早期版本 Lync Server 2010 移至 Lync Server 2013。

<!-- end list -->

  - *升级*   
    在服务器或客户端计算机上安装软件的更高版本。

<!-- end list -->

  - *共存*   
    迁移过程中一些功能已迁移到 Lync Server 2013、其他功能仍保留在 Lync Server 2010 的早期版本上时存在的临时环境。

<!-- end list -->

  - *互操作性*   
    在共存阶段部署能够正常运行的能力。

## 本节内容

  - [开始迁移之前的准备工作](before-you-begin-the-migration.md)

  - [第 1 阶段：规划 Lync Server 2010 的迁移](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [第 2 阶段：准备迁移](phase-2-prepare-for-migration.md)

  - [第 3 阶段：部署 Lync Server 2013 试点池](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [第 4 阶段：将测试用户移至试点池中](phase-4-move-test-users-to-the-pilot-pool.md)

  - [第 5 阶段：向试点池中添加 Lync Server 2013 边缘服务器](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [第 6 阶段：从试点部署移动到生产中](phase-6-move-from-pilot-deployment-into-production.md)

  - [第 7 阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)

  - [第 8 阶段：停用旧池](phase-8-decommission-legacy-pools.md)

