---
title: 迁移阶段
TOCTitle: 迁移阶段
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205336(v=OCS.15)
ms:contentKeyID: 49314255
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移阶段

 

_**上一次修改主题：** 2012-09-17_

在 Lync Server 2013 中，可以在包含 Lync Server 2013 组件的网络上定义站点。站点是一组通过高速度、低延迟网络（例如单个局域网 (LAN) 或由高速光纤网络连接的两个网络）正确连接的计算机。

*前端池* 是一组配置相同的前端服务器，这些服务器协同工作来为公用组用户提供服务。池为用户提供可伸缩性和故障转移功能。池中的每台服务器必须运行一个或多个相同的服务器角色。 Standard Edition Server 是为小型组织设计的，也定义一个池并在单个服务器上运行。这样可使 Lync Server 2013 功能的成本更低，但不提供实际的高可用性解决方案。

以下阶段介绍将池从 Lync Server 2010 迁移到 Lync Server 2013 的过程。对于包含多个池的多个站点，每个池都应遵循此分阶段方法。

1.  [第 1 阶段：规划 Lync Server 2010 的迁移](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [第 2 阶段：准备迁移](phase-2-prepare-for-migration.md)

3.  [第 3 阶段：部署 Lync Server 2013 试点池](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [第 4 阶段：将测试用户移至试点池中](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [第 5 阶段：向试点池中添加 Lync Server 2013 边缘服务器](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [第 6 阶段：从试点部署移动到生产中](phase-6-move-from-pilot-deployment-into-production.md)

7.  [第 7 阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)

8.  [第 8 阶段：停用旧池](phase-8-decommission-legacy-pools.md)

